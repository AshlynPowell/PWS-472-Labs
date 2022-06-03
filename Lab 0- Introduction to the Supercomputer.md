## Introduction to the Supercomputer
### Logging into the Supercomputer
Fill out the first three boxes with [your netID]@ssh.rc.byu.edu, and hit enter

![Pic1](https://www.dropbox.com/s/spc2wcthyzivfy5/Pic1.png?dl=0)

Enter the same password you use for the fulton supercomputing lab and the authentication code. No letters will appear on the screen - don’t worry, it’s still receiving the input.

![Pic2](https://www.dropbox.com/s/sr0ab1ije5owm3s/Pic2.png?dl=0)

### Importing CONDA

#### Step 1: Get miniconda
Google miniconda and click on the conda documentation.

![Pic3](https://www.dropbox.com/s/cv7vt1deupeiv3j/Pic3.png?dl=0)

Scroll down to ‘Linux Installers’ and right-click on Miniconda3-Linux64-bit to copy the link.

![Pic4](https://www.dropbox.com/s/lnr075ala5wy5rj/Pic4.png?dl=0)

Make sure you’re in the compute directory: `cd ~/compute`

Then use wget with the copied url:

![Pic5](https://www.dropbox.com/s/fc65c67507ztnch/Pic5.png?dl=0)

Your screen should look something like this:

![Pic6](https://www.dropbox.com/s/bx4tiw3ifdkxois/Pic6.png?dl=0)

#### Step 2: Initialize CONDA

Type in `bash Miniconda3-latest-Linux-x86_64.sh` and hit enter. When prompted, accept any
terms and conditions / questions (say yes by hitting the Y key or hit enter). * the easiest thing to do is use tab complete: type `bash Mi`, then hit tab, and the rest should fill in.

![Pic7](https://www.dropbox.com/s/ky3skntrxy9f1u0/Pic7.png?dl=0)

When you’re done, the command line will appear with a (base) after typing in
`source ~/.bashrc`.

![Pic8](https://www.dropbox.com/s/3as2mks2b3cxt7h/Pic8.png?dl=0)

### Writing a Job File

We’ll be using the Job Script Generator.
(https://rc.byu.edu/documentation/slurm/script-generator).

![Pic9](https://www.dropbox.com/s/9yqz6yl553l21m8/Pic9.png?dl=0)

To get here, go to Documentation > Job Submission > Job Script Generator

By default, mine looks something like this:

![Pic10](https://www.dropbox.com/s/3ip4ukv6lqbq4w3/Pic10.png?dl=0)

If you would like to enter your email, you can opt to receive an email when the job has begun,
ended, or if it aborted. It can be nice to get these kinds of alerts instead of checking the job
status every few minutes from the command line.
Most labs will specify ranges for the number of processors, memory per processor, and
walltime.

For practice, since we’re submitting a very small job, you can just say 1 processor core with 1
GB memory and 10 minutes for simple practice code. If it aborts, you can modify these
numbers. It’s also helpful to name your job. In this case, I named mine “hello_there”

![Pic11](https://www.dropbox.com/s/1ry8sajmhbndp8t/Pic11.png?dl=0)

When you’re satisfied with the settings, scroll down to where it says ‘Job Script’ and click “copy
script to clipboard” (you can also highlight and copy - it doesn’t really matter).

![Pic12](https://www.dropbox.com/s/dsyi9i2vtecl1io/Pic12.png?dl=0)

In the command line, create a text file called “hello_there.job” using the ‘nano’ command:
nano hello_there.job
(hit enter)
You’ll be brought to a screen that looks like this:

![Pic13](https://www.dropbox.com/s/7eqzxujz6fikw4a/Pic13.png?dl=0)

Paste in the job script you just copied, then type in the commands: 

```
echo “hello there!”
sleep 75
echo “You’re finished!”
```

This will tell the computer to
print out ‘hello there!’, wait 75 seconds, then print
out “you’re finished!”

![Pic14](https://www.dropbox.com/s/lj0b46n4spmz1ff/Pic14.png?dl=0)

Use `^O` to save or rename your text file, and `^X` to exit. After hitting `^X`, be sure to hit `Y` and
enter to save the changes you’ve made.

![Pic15](https://www.dropbox.com/s/mgjtwyjl741hzal/Pic15.png?dl=0)

You can check that it saved by using the cat command to view the text file:

![Pic16](https://www.dropbox.com/s/by91vbtwv1helgp/Pic16.png?dl=0)

### Submitting a Job

Once you have the job file created, use the `sbatch` command to submit your job.

```
sbatch hello_there.job
```

![Pic17](https://www.dropbox.com/s/tm9rbzbv7fg1ls8/Pic17.png?dl=0)

### Checking the Job Status

Use the `squeue` command to check job status:

```
squeue -u [your netID or username]
```
![Pic18](https://www.dropbox.com/s/4h3ih6hhpth5htp/Pic18.png?dl=0)

You can do this as much as you'd like:

![Pic19](https://www.dropbox.com/s/s3zqzzsccz3ansl/Pic19.png?dl=0)

If you signed up for email alerts, you’ll be notified if the job is begun, finished, or aborted.

Remember to properly exit out of the super computer by typing in `exit`:

![Pic20](https://www.dropbox.com/s/tolie8j48buyijw/Pic20.png?dl=0)
