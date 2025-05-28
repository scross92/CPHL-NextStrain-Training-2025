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

So we could resolve this if we wanted to get fancy with some bioinformatics but Pathoplexus does just this already. If the Isolate Name is blank, then in the metadata file, it will automatically use the Pathoplexus accession number and collection country (where available). So let's start digging into that next portion. Go ahead and download the metadata file. Select 'Download all entries', except this time we are going to download the Metadata TSV file. You will see it automatically fills in selections for the metadata, but we know which fields we already want (see above). So let's only select those again. With our 9 choices plus the *required* Pathoplexus accession, we should have 10 total fields. Agree to the terms and download the metadata file. Go ahead and drag and drop the TSV file with excel to open it that way.




