# Database exercises: IN PERSON EXERCISE

Now that we have explored each database, we are going to access data from each one, and answer a few questions. We are also going to make use of Nextclade to do some 'spot checking' of the data that we download.

## NCBI

A really nice feature of NCBI is the fact that unlike GISAID and Pathoplexus, which are focused more on viral pathogens, NCBI has data for ALL organisms. Let's practice navigating NCBI.

1. Go to the NCBI homepage: https://www.ncbi.nlm.nih.gov/
2. Navigate to the Taxonomy portal and enter the Taxonomy database.
3. Let's find the taxonomy page for Mycobacterium tuberculosis. Hint: Remember you need to use the scientific name here. As a test, just try searching tuberculosis and see what happens when you do not provide specific search results.
4. Rather than looking at a specific strain/isolate, let's just broadly look at all M. tuberculosis data.

❓**Questions regarding the taxonomy data**
- How many nucleotide sequences are available for Mycobacterium tuberculosis?
- Are all these nucleotide sequences complete genomes?
- How many Dataset Genomes are available (rememember to look at the Subtree links)?

6. Let's take a look at the nucleotide sequences.
7. We just want to look at complete genomes. Provide the additional keyword filter "Complete" to only display complete genomes. Hint: Remember it will be added to the search bar in addition to the taxonomic ID

❓**Questions regarding the complete genome data**
- How many complete genome sequences are available for Mycobacterium tuberculosis?
- How many of these are Refseq genomes?

8. Navigate to show only complete, Refseq genomes.
9. Find Accession NZ_CP025593.1. Open it up to take a look at the metadata.

❓**Questions regarding the complete genome data**
- What year was this isolate collected?
- Where was the isolate collected?
- What was the name of the first author?
- Although they may not link it to a publication, they give a dataset title and this can sometimes be used to find the (now) published data. Can you find the article?

Despite having data for all organisms, NCBI does have the NCBI Virus database which curates viral sequences. Let's explore the NCBI Virus portal and answer some questions.

1. Go to NCBI Virus (Hint: I find Google search is the best/fastest way to navigate here)
2. Let's find data for mpox virus. Note: Not all virus taxonomy is currently up to date so you may see outdated nomenclature
3. Let's do some filtering to find specific sequences:

- Filter to only include B.1 lineage
- Filter to have the **release date** be from Jan 1, 2025 to May 26, 2025

❓**Questions regarding the filtered MPXV data**
- How many B.1 lineage sequences have been released in 2025?
- Do any of the sequence collection dates match the release dates? If not, what outbreak of MPXV does these appear to be associated with?
  
4. Let's clear those filters.

❓**Questions regarding the *unfiltered* MPXV data**
- How many MPXV sequences are available on NCBI Virus?
- What is the Taxonomic ID of MPXV?
- What is the earliest release date of a MPXV genome for NCBI Virus?
- Where was geographic location of the most recent genome?

## GISAID

Let's explore some GISAID data. As we discussed, GISAID is very popular with SARS-CoV2 sequencing data. They were originally designed for influenza data but unfortunately there are some restrictions that they place for this data. They also have some data for mpox virus and a few arboviruses. However, today we will leverage what it is most often used for: SARS-CoV2.

1. Login to your GISAID account. If you did not create an account prior to this workshop, please find a partner to pair with during this section of the tutorial.
2. Under EpiCoV, you can find the SARS-CoV2 data as we discussed in the introduction to databases.
3. Let's download a very specific set of data that's geographically relevant (Uganda).
4. For the data we are going to refine our search. Please refine the data to:
- Sequences that were *collected* from Jan 1 2025 to May 31 2025
- Sequences that are found in Uganda
- Complete sequences
- Sequences with completed collection dates

❓**Questions regarding the Uganda SARS-CoV2 data**
- How many sequences match this search?
- How many sequences (complete or not) are found for Uganda?
- How many complete sequences are found for Uganda?
- How many sequences (complete or not) were described for Uganda in 2025?

5. Let's take a look at these sequences using Nextclade. First, let's download the sequences that matched our search. Download the sequences in a way that would be useful for Nextstrain analyses.
6. Visit the Nextclade website. Drop in the fasta file that contains the downloaded sequences. Make sure the dataset is automatically suggested. Run the analysis with the default dataset sugggestion.
   
❓**Questions regarding the downloaded Uganda SARS-CoV2 data**
- How many files were downloaded for Nextstrain analyses? What is the purpose of these files?
- What was the suggested Nextclade reference dataset? How many sequences matched as a "fit" for this dataset?
- What sample had the lowest coverage? What was the coverage %?
- All samples had a single nucleotide polymorphism at position 5239. What was the nucleotide change? Hint: You will likely need to change the view of which genetic feature is highlighted.
  
8. Now let's take a look at the other file that was generated when downloading the sequences.

❓**Questions regarding the downloaded Uganda SARS-CoV2 data**
- Are any of the key metadata missing? What are the key metadata again that Nextstrain requires? Hint: If you need a refresher visit https://docs.nextstrain.org/en/latest/tutorials/creating-a-phylogenetic-workflow.html ("Prepare the Sequences" section)
- What was the sex of the patient that was **not** from the Central region?
- Referring back to the sample that had the lowest coverage as determined by Nextclade, what was the age of this patient?
- Which sequence was the most recently acquired sequence?
  
## Pathoplexus

Great news! Pathoplexus just recently added in 3 new pathogens to their portfolio: Respiratory Syncytial Virus-A, Respiratory Syncytial Virus-B, and Human Metapneumovirus. Let's do some exploring with one of these datasets. Let's start with human metapneumovirus.

1. Login to your Pathoplexus account. If you did not create an account prior to this workshop, please find a partner to pair with during this section of the tutorial. **Note:** We will be using this for the case studies, so take a moment to request an account as it has, in our experience, the quickest turn around for creating an account.
2. Navigate to the appropriate repository. Hint: Human metapneumovirus is HMPV
3. Let's download a very specific set of data that's geographically relevant (Uganda).
4. For the data we are going to refine our search. Please refine the data to:
- Sequences that are found in Uganda

5. A really nice thing again about Pathoplexus is the robust array of metadata fields that can be used. Let's add some features to get more information (Hint: Customize Columns):
- Host name (scientific)
- Completeness
- Total Unknown Nucleotides (nucs)
- Sequencing Date

6. Now that we added in a variety of additional metadata, let's take a look and answer some questions:

❓**Questions regarding the refined Uganda HMPV data**
- How many HMPV sequences are available for Uganda?
- How many of these sequences are whole genome (or nearly whole genome)?
- How many different host species are noted in these sequences? What are the common names of these hosts?
- Do any of the sequences have a known sequencing date? Why is it important to track the metadata choices and the results of said choices?
- What is highest completeness (%) of the sequences? How many ambiguous nucleotides are found in that sequence?
- How many lineages are captured by these sequences? 

7. Now that we have manually looked through some of the metadata (here it is convenient since there isn't a large number of sequences to view), let's go ahead and use Nextclade to give us some more information.
8. Refine your search to only have sequences that are near-complete. Do this by filtering for sequences that have a minimum length of >12,000 nucleotides. Download **only** these sequences in FASTA format.
9. Go back to Nextclade. Note: You may need to clear the prior SARS-CoV2 data
10. Add in your data, let it suggest a dataset (may need to hit the "Re-suggest" button) and then run Nextclade.

❓**Questions regarding the refined Uganda HMPV data with Nextclade**
- Was there an appropriate Nextclade dataset? Will there *always* be an appropriate dataset?
- How many mutations relative to the reference were noted?
- In the L protein, there is an amino acid change at position 390. What was the amino acid change? The nucleotide change?
- In the N protein, there is a large stretch of ambiguous nucleotides. How long (number of nucleotides) is this stretch?

