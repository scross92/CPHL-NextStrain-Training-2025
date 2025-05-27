# Geneious Exercises: IN PERSON EXERCISE
Now that we have covered the basics of Geneious, let's perform a few exercises to help us remember some useful tools that can be utilized in Geneious

## Mapping Reads to Reference Genome
We have performed some prior sequencing to West Nile virus (WNV) in contrived mosquito samples. We had used hybrid capture enrichment sequencing to try and capture as much WNV as possible. (Not sure what hybrid capture sequencing is? Here is a good primer on it: ). We have already previously trimmed the reads to remove adapter sequences and have removed poor quality reads. Let's use this data to practice analyzing mapped reads in Geneious.

1. First let's make a new directory/folder for doing this exercise. Create a new folder and name it "Geneious Exercises." In that folder make a new subfolder and call it "Mapping Exercise."
2. Now download an appropriate reference genome for WNV. Download the file directly into Geneious, using the NCBI->Nucleotide interface (search for NC_009942). Once downloaded, drag from the NCBI download folder into the "Mapping Exercise" folder in Geneious. It will likely only download a portion, select the genome and click the "Download" button in the Document Viewer section.
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
- Let's look at position 8,242 in the consensus sequence. Does this match the reference genome? If not, does this seem like a true variant/SNP?
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

## Multiple Sequence Alignment Exercise
Now we have aligned our reads to multiple reference genomes and have identified that one of the two references appears to be a better choice. However, we also want understand the diversity of this reference in context of other WNV genomes. Let's go ahead and do some comparisons by genetic diversity. In order to this, we need to do some alignments. 

1. Let's start small with comparing our generated consensus sequences based on the references used. First, extract out the consensus sequences for each alignment. Make sure you name them appropriately that you know what you working with. I often find the default naming scheme for Geneious isn't optimal. Instead let's name it something like [REF_GENOME]_consensus_sequence.fasta
2. Go ahead and make a new folder for the alignment exercise. Under the same parent directory/folder "Geneious Exercises", make a new subfolder called "Geneious Alignment". Move the consensus sequences generated in the previous step to this folder. At the same, _copy_ the two reference genomes we used for the mapping exercise. By the end of this step, if done correctly your "Geneious Alignment" folder should have 2 consensus sequences and 2 reference genomes. The "Geneious Mapping" folder should still have the 2 reference genomes, but will not have the consensus sequences.
3. Make sure you are in the "Geneious Alignment" folder. We will do a **mafft** alignment with just the two consensus sequences. We can use default settings. Hint: Look at the Toolbar and identify the the Align/Assemble toolkits.
4. Examine the mafft alignment and answer the following questions:

:question: **Questions to consider when viewing the mafft alignment of consensus sequences:**

- What is the pairwise identity? What does this percentage mean?
- Did the reference genome chosen impact the outcome of the consensus sequences? Is this always the case? 

5. Now let's compare the consensus sequences to the WNV reference genome NC_009942. Perform another **mafft** alignment with just one of the consensus sequences (let's choose the MH170227 consensus sequence) and NC_009942. Let's answer some questions now on this:

:question: **Questions to consider when viewing the mafft MH170227 alignment of consensus sequence with NC_009942:**

- What is the pairwise identity?
- How can you easily identify which spots across the genomes that differ?

7. Let's give this a little bit more diversity in here. Go ahead and download NC_001563 from the NCBI Nucleotide interface. Similar as before, this likely will only download a portion. Select NC_001563 and click the "Download" button in the Document Viewer section.
8. Now let's do a **mafft** alignment with MH170227 consensus sequence, NC_009942, and NC_001563. Let's answer some questions:

:question: **Questions to consider when viewing the mafft alignment with NC_001563 added:**

- What is the *overall* pairwise identity now?
- What is the pairwise identity at nucleotide position 630?
- What is the pairwise identity from position 1,427 through 1,438? What is something that you notice about this section of nucleotides for NC_001563?
- In the Document Viewer window, there are the different tabs. One of them is labeled "Distances". This shows a chart that shows the pairwise identity between each sequence. What is the *overall* pairwise identity from our generated consensus sequence and NC_001563?

10. Ok, so adding in that sequence added quite a bit of variation. Let's try to decipher *why* there was such a change. Let's examine metadata for NC_009942 and NC_001563. What is something major that appears to stick out that likely explains this large variation?

## Summary
Geneious is a powerful tool that allows for quick identification and quality control of consensus sequences, alignments, and more. However, remember that Geneious runs off the laptop's computational power/infrastructure, therefore it often will use little memory and only a single thread. As such, large analyses become bogged down easily. Leveraging the computational infrastructure on computing clusters to perform things like alignments can be helpful. Then you can still import those files into Geneious for manual inspection. 

Manually inspecting your data is often essential. Having an understanding of *what* your data is showing gives you a better understanding what can happen in subsequent analyses/steps (e.g. Nextstrain). 

Always look for documentation as much as possible for tools. Geneious offers a fairly robust manual for their default toolkits. See here: https://manual.geneious.com/en/latest/index.html 

