## Lab 6: Phylogenetics Tutorial using MEGA

In this tutorial you will make a phylogenetic tree using a program called MEGA with sequences
downloaded from BOLD systems.
1. Download MEGA on your computer by going to https://www.megasoftware.net/. Download this on to the machine you are going to use for the analysis, make sure to select the correct system (Windows, macOS, Ubuntu, etc.), Graphical (GUI) and MEGA X (64-bit). Click download, go through the user agreements and user profile, indicating that you are a student at a university. <img width="794" alt="Screen Shot 2022-06-06 at 11 18 57 AM" src="https://user-images.githubusercontent.com/70609417/172213618-2cbbf489-bffe-4869-92d5-495d6fbbcac9.png">
2. Click on the MEGA… _setup.exe file in your downloads folder. There will be several set up options such as letting the program have access to your computer, setup language, licensing agreement as well as a location to install the program. For this location, direct it to your desktop as that will be the easiest place to run it from. You can do that using the browse tab and then select Users, your username, and then Desktop.
3. Once the program has been installed, it should be launched.
4. At this point we are going to leave MEGA to find the sequences to use for the phylogeny.
5. Navigate to BOLD systems http://www.boldsystems.org/index.php. Click on ‘Databases’, found along the top bar. Click on ‘Public Data Portal’. 
6. Search for sequences of interest, ideally several genera within a family. To do this you can look up any family you are interested in and find several genera within that family. For example, if your family was Felidae you could search for Panthera, Neofelis, Lynx and Puma. This can be found from a simple google search. You should also choose an “outgroup” or a taxon that fall just outside your organism of interest. For example, in the case of Felidae, this could be a Hyena.
7. Download 9-10 sequences representing multiple genera into a fasta file by selecting them and clicking the blue fasta button in the upper right-hand corner. You might have to download the fasta files separately and then manually move sequences into a single file. <img width="555" alt="Screen Shot 2022-06-06 at 11 19 15 AM" src="https://user-images.githubusercontent.com/70609417/172214832-cb4ee564-119c-4ee5-b10b-abb815faa515.png">
8. Once you have a single fasta file with 9-10 sequences open MEGA.<img width="851" alt="Screen Shot 2022-06-06 at 11 19 56 AM" src="https://user-images.githubusercontent.com/70609417/172214950-abb456b5-4c2c-4bd6-8669-b13510fe7b24.png">
9. In MEGA, go to ‘File’, ‘Open a new session’, select the fasta file you just created from the browse tab, click ‘Align’.
10. A separate window should open with the names and sequences of each species in your fasta file. Select ‘Align’, then ‘Align by MUSCLE’, then ‘OK’, then ‘OK’.
11. Once your data is aligned, select ‘Data’, then export alignment and ‘Export as MEGA’. Choose a location where you want the .MEG file to go. You will use this file to create your phylogenetic tree so be sure you know where it is saved.
12. Go back to your original MEGA window and make trees. You will make two phylogenetic trees using different computational methods. First, select the circle labeled ‘PHYLOGENY’ and then ‘Construct/Test Maximum Likelihood Tree’. You will have to direct the program to the .meg file you saved from the alignment. Change the rates and patterns to Has Invariant Sites in the ‘Rates among Sites’ dropdown. Make sure the number of threads is 2. Click ‘OK’ and MEGA will generate your tree for you. You can then export your tree under the file tab.<img width="481" alt="Screen Shot 2022-06-06 at 11 20 21 AM" src="https://user-images.githubusercontent.com/70609417/172215014-d088c751-2a46-466c-bcca-8d3d9e0bf248.png">
13. Repeat this process by selecting the circle labeled ‘PHYLOGENY’ and then Construct/Test Maximum Parsimony Tree’ **This is different from the Maximum likelihood tree**. Specify the same parameters and export the tree when you are finished.
14. Things to keep in mind for the write-up:
a. What organism did you decide to study (if you so something like this for your
final project, you need to make sure you choose a different organism each time)?
b. How did you retrieve the data and from where?
c. What do you notice about the tree? Are the relationships as expected?
d. Are there any evolutionary insights that you can make based on that tree?
