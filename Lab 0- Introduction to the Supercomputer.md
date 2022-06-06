## Lab 0: Introduction to the Supercomputer
### Logging into the Supercomputer
Fill out the first three boxes with [your netID]@ssh.rc.byu.edu, and hit enter.

<img width="1105" alt="Pic1" src="https://user-images.githubusercontent.com/70609417/171961146-3fba64e8-f05b-46e2-bcd5-3d102129e8e0.png">

Enter the same password you use for the Fulton supercomputing lab and the authentication code. No letters will appear on the screen - don't worry, it's still receiving the input.

<img width="791" alt="Pic2" src="https://user-images.githubusercontent.com/70609417/171961156-9ae74527-e17c-45cb-bf23-4d12a68ec68a.png">

### Importing CONDA

#### Step 1: Get miniconda
Google miniconda and click on the conda documentation.

<img width="585" alt="Pic3" src="https://user-images.githubusercontent.com/70609417/171961192-ecb7d278-7797-4ed7-a548-5d6826aa341c.png">

Scroll down to 'Linux Installers' and right-click on Miniconda3-Linux64-bit to copy the link.

<img width="894" alt="Pic4" src="https://user-images.githubusercontent.com/70609417/171961207-144d8b7b-4ce3-481a-b9aa-971a05fc2aac.png">

Make sure you're in the compute directory: `cd ~/compute`

Then use `wget` with the copied url:

<img width="1020" alt="Pic5" src="https://user-images.githubusercontent.com/70609417/171961222-a8438128-f1ea-47b7-b556-4b0c628c41e6.png">

Your screen should look something like this:

<img width="839" alt="Pic6" src="https://user-images.githubusercontent.com/70609417/171961238-6320e55a-f9de-4a0a-aed9-a55133d4fb38.png">

#### Step 2: Initialize CONDA

Type in `bash Miniconda3-latest-Linux-x86_64.sh` and hit enter. When prompted, accept any
terms and conditions / questions (say yes by hitting the `Y` key or hit enter). 
\* the easiest thing to do is use tab complete: type `bash Mi`, then hit tab, and the rest should fill in.

<img width="809" alt="Pic7" src="https://user-images.githubusercontent.com/70609417/171961258-e8f74445-372f-460c-b90b-110824a371a0.png">

When you're done, the command line will appear with a (base) after typing in
`source ~/.bashrc`.

<img width="363" alt="Pic8" src="https://user-images.githubusercontent.com/70609417/171961286-0b93c9a6-40c0-4c94-a015-5d012125454a.png">

### Writing a Job File

We'll be using the Job Script Generator.
(https://rc.byu.edu/documentation/slurm/script-generator).

<img width="836" alt="Pic9" src="https://user-images.githubusercontent.com/70609417/171961299-72e8d32f-b960-4664-9680-06d42af25a1d.png">

To get here, go to Documentation > Job Submission > Job Script Generator .

By default, mine looks something like this:

<img width="634" alt="Pic10" src="https://user-images.githubusercontent.com/70609417/171961312-3a2bcf25-1e98-4a2a-9ab6-7869aa02b852.png">

If you would like to enter your email, you can opt to receive an email when the job has begun,
ended, or if it aborted. It can be nice to get these kinds of alerts instead of checking the job
status every few minutes from the command line.
Most labs will specify ranges for the number of processors, memory per processor, and
wall-time.

For practice, since we're submitting a very small job, you can just say 1 processor core with 1
GB memory and 10 minutes for simple practice code. If it aborts, you can modify these
numbers. It's also helpful to name your job. In this case, I named mine "hello_there".

<img width="576" alt="Pic11" src="https://user-images.githubusercontent.com/70609417/171961323-a0ca0372-92ec-45a7-91d0-a6ad6c675a0e.png">

When you're satisfied with the settings, scroll down to where it says ‘Job Script’ and click "copy
script to clipboard" (you can also highlight and copy).

<img width="676" alt="Pic12" src="https://user-images.githubusercontent.com/70609417/171961334-05388ce4-88ca-4e3f-8842-fb02117726c8.png">

In the command line, create a text file called "hello_there.job" using the `nano` command:
```
nano hello_there.job
```
You'll be brought to a screen that looks like this:

<img width="321" alt="Pic13" src="https://user-images.githubusercontent.com/70609417/171961348-491c8175-d486-48be-aef3-074b9bede0e1.png">

Paste in the job script you just copied, then type in the commands: 

```
echo "hello there!"
sleep 75
echo "You're finished!"
```

This will tell the computer to print out "hello there!", wait 75 seconds, then print out "you're finished!".

<img width="835" alt="Pic14" src="https://user-images.githubusercontent.com/70609417/171961392-0a572524-606d-4f91-8f3d-811bd413ce32.png">

Use `^O` to save or rename your text file, and `^X` to exit. After hitting `^X`, be sure to hit `Y` and enter to save the changes you've made.

<img width="798" alt="Pic15" src="https://user-images.githubusercontent.com/70609417/171961403-eb708614-4daf-43f4-b680-ae4040d8ca09.png">

You can check that it saved by using the `cat` command to view the text file:
```
cat hello_there.job
```

<img width="835" alt="Pic16" src="https://user-images.githubusercontent.com/70609417/171961426-24deaebf-2145-492b-b289-0f87fdeb5903.png">

### Submitting a Job

Once you have the job file created, use the `sbatch` command to submit your job:

```
sbatch hello_there.job
```

<img width="567" alt="Pic17" src="https://user-images.githubusercontent.com/70609417/171961449-b9759a5e-ef9f-4a70-8965-16a926c5fac2.png">

### Checking the Job Status

Use the `squeue` command to check job status:

```
squeue -u [your netID or username]
```
<img width="833" alt="Pic18" src="https://user-images.githubusercontent.com/70609417/171961466-b4cadd37-1c1c-4b75-a99e-81f7c77e0d9b.png">

You can do this as much as you'd like:

<img width="834" alt="Pic19" src="https://user-images.githubusercontent.com/70609417/171961474-c27ae3be-e3c2-4817-80cb-16a0291ce98e.png">

If you signed up for email alerts, you'll be notified if the job is begun, finished, or aborted.

Remember to properly exit out of the super computer by typing in `exit`.

<img width="613" alt="Pic20" src="https://user-images.githubusercontent.com/70609417/171961485-939b22fe-41a3-4c47-affb-0f2796369d7b.png">
