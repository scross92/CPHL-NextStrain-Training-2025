# Geneious Exercises
Now that we have covered the basics of Geneious, let's perform a few exercises to help us remember some useful tools that can be utilized in Geneious

# Mapping Reads to Reference Genome
We have performed some prior sequencing to West Nile virus (WNV) in contrived mosquito samples. We had used hybrid capture enrichment sequencing to try and capture as much WNV as possible. (Not sure what hybrid capture sequencing is? Here is a good primer on it: ). We have already previously trimmed the reads to remove adapter sequences and have removed poor quality reads. Let's use this data to practice analyzing mapped reads in Geneious.

1. First let's make a new directory/folder for doing this exercise. Create a new folder and name it "Geneious Exercises." In that folder make a new subfolder and call it "Mapping Exercise."
2. Now download an appropriate reference genome for WNV. Download the file directly into Geneious, using the NCBI->Nucleotide interface (search for PP445211.1). Once downloaded, drag from the NCBI download folder into the "Mapping Exercise" folder in Geneious.
3. Let's download the practice dataset. It can be found in this Google Drive link:
4. After you download the data--Remember to download both Read 1 and Read 2 (R1, R2)--go ahead and drop it into Geneious. It will ask about if this should be paired data, select yes, and you can keep default settings for the insert length; we will check if this was the best choice later.
5. Now let's map the reads to the reference. We can just use the Geneious aligner with default settings. Make sure you choose the appropriate file for the reference genome! Hint: Look at the Toolbar and identify the the Align/Assemble toolkits.
6. It should take a couple minutes to run, but then it will spit out both a report and the alignment file. Let's dig in and answer some questions.

:question: **Questions to consider when viewing the alignment:**
- What is the average coverage depth across the WNV genome?
- What is the total coverage across the WNV reference genome?
- Is the coverage *even* across the genome?
- Would you expect coverage to be even across the genome?  (Recall that this data is derived from hybrid capture enrichment specific to the WNV genome)
- Are there any variants between this sequenced WNV genome sequence and the WNV reference sequence?
- Is it expected that there are variants between these reads and this reference sequence?  Explain your answer.
- Let's look at position 5,976 in the consensus sequence. Does this match the reference genome? If not, does this seem like a true variant/SNP?
- Can you distinguish true variants from sequencing errors?
- In general, how can you distinguish true variants from sequencing errors?
- Can you identify mapped read pairs?

Actually, turns out we could have chosen a better reference genome because we know exactly which WNV strain was used in this experiment. Let's go ahead and repeat these steps using a strain specific reference genome.
7. Let's find the new reference genome using the NCBI->Nucleotide interface (search for MH170227). Once downloaded, drag from the NCBI folder and into the "Mapping Exercise" folder.
8. Now let's map the reads to the new reference. Again, let's stick with default Geneious settings.
9. Let's take a look again at the new alignment and answer some questions.

:question: **Questions to consider when viewing the _NEW_ alignment:**
- What is the average coverage depth across the WNV genome?
- What is the total coverage across the WNV reference genome?
- Do you see any variants this time in the consensus sequence? Does this make sense?
- How does this new mapping emphasize the importance of picking an appropriate reference genome?
- How many reads **did not** map to WNV? What do you think these reads could align to? Hint: Go back to the beginning of this section and look at what we were sequencing.
