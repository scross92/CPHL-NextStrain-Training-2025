# Database exercises: IN PERSON EXERCISE

Now that we have explored each database, we are going to access data from each one, and answer a few questions. We are also going to make use of Nextclade to do some 'spot checking' of the data that we download.

## NCBI

## GISAID

Let's explore some GISAID data. As we discussed, GISAID is very popular with SARS-CoV2 sequencing data. They were originally designed for influenza data but unfortunately there are some restrictions that they place for this data. They also have some data for mpox virus and a few arboviruses. However, today we will leverage what it is most often used for: SARS-CoV2.

1. Login to your GISAID account. If you did not create an account prior to this workshop, please find a partner to pair with during this section of the tutorial.
2. Under EpiCoV, you can find the SARS-CoV2 data as we discussed in the introduction to databases.
3. Let's download a very specific set of data that's geographically relevant (Uganda).
4. For the data we are going to refine our search. Please refine the data to:
- Sequences that were generated/posted from Jan 1 2025 to May 31 2025
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

