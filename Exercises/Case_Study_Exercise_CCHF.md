# Crimean-Congo Hemorrhagic Fever Virus (CCHFV) Nextstrain Build

If you are working on this case study exercise, you will be downloading CCHFV data from Pathoplexus and making a Nextstrain build. Take some good notes as you will pair with the other team working on this exercise and then together the groups will present the build.

## Let's go data hunting!

The first thing that we need to do is to actually find the data. Navigate to the CCHFV dataset with Pathoplexus. If you notice, there are quite a few sequences readily available. However, we want to be particular about what sequences we are using (plus this will make our lives significantly better when we run the build itself). If you notice, in the default settings there are 3 pieces of metadata that are seemingly unique--Length L, Length M, Length S. What do you think these correspond to? Hint: CCHFV is a bunyavirus which has a unique genome structure (https://viralzone.expasy.org/250?outline=all_by_species).
<details>
  <summary><b>Click here for the answer</b></summary>
  Bunyavirus genomes are tripartite. They are composed of an L, M, and S genome (Large, Medium, Small)
</details>

We are going to explore just one of these viral proteins, the L protein which encodes the RNA-Dependent RNA polymerase. If you just look at the first 4 sequences, what is something major that just will not work for our analysis? Hint: Look at those same unique column headers.
<details>
  <summary><b>Click here for the answer</b></summary>
  The length of the L segment sequences vary drastically in size. Some are near complete while others are just fractions of the genome.
</details>

Let's go ahead and restrict our search to only complete (or near complete) L segment sequences. We can do this by making the 'From' length for the L segment to be 12,000 (Hint: Look over to the search fields on the left hand side of the screen).

Now that we've done this, how many sequences do we have left?

<details>
  <summary><b>Click here for the answer</b></summary>
  Only 318 sequences remain.
</details>

Ok, so we are making some good progress in reducing the number of sequences for this analysis. Let's spend some time leveraging the power of Pathoplexus. Pathoplexus is neat because it provides an already generated mafft alignment (remember this is the same alignment tool Nextstrain will use). We can do this by now selecting "Download all entries" in the top right. We are going to select "Aligned nucleotide sequences" and select the L segment. Agree to the data use terms and then go ahead and download this to a new folder for this exercise. It gives a default naming mechanism, which is generally ok as it contains helpful information--what the file is (alignment), the segment (L), and date. 

Ok, remember, what tool is useful for doing manual spot checking of files?
<details>
  <summary><b>Click here for the answer</b></summary>
  Geneious Prime
</details>

So let's go ahead and open up Geneious. Make a new folder for this specific exercise (e.g. name the folder CCHFV_Exercise). Drop in the alignment file--select nucleotide. Take a look at the alignment. Consider the following:

- How does the alignment look overall?
- Are there any areas of concern?
- Is every nucleotide different or do you see identical spots? (Hint: remember to zoom in to get a better view)
- What is the overall pairwise identity?

I'd say this alignment looks good. No massive spots of red suggesting that this alignment overall is pretty good. So now that we know these sequences are doing a pretty good job, let's go ahead and dig a bit more into the sequence metadata.

Pathoplexus has LOTS of different metadata fields. Let's look at a few that are important. Select the "Customize Columns" and look at your options. Some things to consider:

- We are just going to look at these sequences from a country level, so you can unselect the Collection Subdivision Level 1
- What things are ESSENTIAL for Nextstrain? (https://docs.nextstrain.org/en/latest/tutorials/creating-a-phylogenetic-workflow.html). Also look to see what is helpful information to have. Go ahead and make sure that you select those!
- We do want to know the host species so make sure Host Name-Scientific is selected.

<details>
  <summary><b>Click here for the boxes that should be selected</b></summary>
  
  - Length L
  
  - Author Affiliations
  
  - Author
  
  - Host Name-Scientific
  
  - Is Lab Host (This is to known if it was a cultured virus in the lab)
  
  - INSDC accesssion L
  
  - Collection Country
  
  - Collection Date
  
  - Isolate Name (this is the strain name)
</details>

Ok, let's take a closer look again with this "critical" metadata. Play around with reorganizing the data by clicking the column headers. Uh oh, looks like some metadata may be missing. However, what is one REALLY important Nextstrain metadata field that has a clear problem here that doesn't have a workaround?

<details>
  <summary><b>Click here for the answer</b></summary>
  The Collection Date field. Not all samples have a collection date recorded!
</details>

Ok, this is critical because Nextstrain has date as one of the 3 essential metadata fields in builds. So we need to address this. Filter the Collection date to start at the earliest *known* date. How many samples do we have now?

<details>
  <summary><b>Click here for the answer</b></summary>
  The earliest date is 1956. You can filter with the collection date on the search fields. We now have 302 sequences.
</details>

Well, we are also going into another problem if we look at the isolate name. What's the issue here?

<details>
  <summary><b>Click here for the answer</b></summary>
  Some of the strain names (Isolate Name) are blank. This is another key piece of information for Nextstrain.
</details>

So we could resolve this if we wanted to get fancy with some bioinformatics but Pathoplexus does just this already in one way. It will automatically use the Pathoplexus accession number and collection country (where available) rather than the actual strain name. Honestly, this isn't the optimal format, but it would take some more tweaking and coding to fix this. Therefore, we are going to just go with the new 'Pathoplexus strain' name for the remainder of this exercise. 

So let's start digging into the metadata file. Go ahead and download the metadata file. Select 'Download all entries', except this time we are going to download the Metadata TSV file. You will see it automatically fills in selections for the metadata, but we know which fields we already want (see above). So let's only select those again. With our 9 choices plus the *required* Pathoplexus accession, we should have 10 total fields. Agree to the terms and download the metadata file. Go ahead and drag and drop the TSV file with excel to open it that way.

One thing you should notice is the naming of the column headers is not exactly the same match as the 'filters' we selected. It still has the same information, but you just need to be careful about what each header is. For example, look at the "specimenCollectorSampleId". Can you figure out or decipher what this column is actually showing?

<details>
  <summary><b>Click here for the answer</b></summary>
  This is the strain names (Isolate Name).
</details>

If we dig into the "specimenCollectorSampleId" column you notice the same issue as before. These are the blank strain names. When we download the fasta file, this isn't problematic as the strain names are captured, but we need these strain names in BOTH the metadata file and the FASTA file. Let's go ahead and downlad the FASTA file and then we can extract the strain names. Download the FASTA file for the L segment and select the "Display Name" as it will keep the appropriate strain name vs the Pathoplexus Accession number. Save the FASTA file in the same location as the metadata file. Save it as the default naming or choose a new name (we will switch the name regardless later)

Let's go ahead and look at the first line of the FASTA file with 'head'. Make sure from the terminal window (WSL or Terminal) to be in the right directory. Adjust with the appropriate FASTA file name.

```
# look at only the first line--this is the first header
head -n 1 [FASTA_FILE]
```

Looking at the first header, you can see it should (hopefully) be an example of a strain that was named after location, Pathoplexus accession number, and collection date. Can you find the respective file in the metadata TSV file?

Let's go ahead and pull out all the strain names that we will need to add to the metadata file. This one liner of code should do the trick. Adjust with the appropriate file names.

```
# Extract strain names from FASTA
grep ">" [FASTA_FILE] | sed 's/>//' > CCHFV_strains.txt
```
This now has created a text file of all the Pathoplexus associated strain names. This can now be added to the metadata file. We are going to make a new metadata file. Typically, in best practice, this is done in a CLI format. However, for ease of this training, we will go ahead and do this in a new excel file. However, we want to be **very** careful in how it is being named. 

1. Make a new excel file, but then "Save As" as a tab delimited file. This by default uses .txt but we want .tsv
2. Rename the file in your Finder window as metadata.tsv. If it asks to override the extension, just select yes
3. Close the old file just to be safe and reopen the new metadata.tsv file

Now that we have a new metadata.tsv file open, we are going to transfer over metadata from the Pathoplexus metadata file. It has some great information, but just named in a way that doesn't totally match what we would expect to use for Nextstrain.

Make the following column headers:
1. strain
2. date
3. region
4. country
5. is_lab_host
6. host
7. genbank_accession
8. authors

In each of these columns, migrate over the appropriate metadata. You'll find that one of these columns doesn't have associated metadata for one of these columns. Which one is it?

<details>
  <summary><b>Click here for the answer</b></summary>
  Region
</details>

However, I have taken the time to go through and label all the regions. I have a metadata.tsv file saved in the 'Exercises' folder that you can download. First, rename your saved metadata.tsv file (e.g. metadata_generated.tsv). Compare your metadata_generated.tsv file against mine and see if it matches (with the exception of the filled in Regions column).

Let's go ahead and rename our sequences file at this time as well. Rename it as sequences.fasta. We are now getting ready to move into the Nextstrain build steps.

# Run some Nextstrain on the files you collected!

We now have a list of 302 sequences and a metadata file for these sequences. It is time to move into the Nextstrain portion. We have walked through the steps of a Nextstrain build multiple times now (both remote learning and earlier in this in person training). We will dig in and really flesh out the steps of a specialized config file for the pathogens of interest for CPHL. So to save time and energy, I have pulled together the necessary files and folders for running the Nexstrain build. Go ahead and copy these files by running this command:

```
git clone XXXX
```
After it clones, it should 





