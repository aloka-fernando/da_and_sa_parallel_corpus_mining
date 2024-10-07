# Document Alignment for News Source: Hiru

This repository contains scripts for aligning documents from the Hiru news source, using embedding-based methods like LASER or XLMR. The alignment process compares English and Sinhala document embeddings to find the closest matches, allowing for language pair analysis.

## File Structure

- **Embedding Filepaths**  
  - English Embeddings:  
    `embeddingPathA = "/path/to/folder/p2_parallel_corpus_mining/embeddings_laser/hiru/en/"`
  - Sinhala Embeddings:  
    `embeddingPathB = "/path/to/folder/p2_parallel_corpus_mining/embeddings_laser/hiru/si/"`

- **Text Files (Readable)**  
  - English Text Files:  
    `readbleDataPathA = "/path/to/folder/p2_parallel_corpus_mining/textfiles/hiru/en/"`
  - Sinhala Text Files:  
    `readbleDataPathB = "/path/to/folder/p2_parallel_corpus_mining/textfiles/hiru/si/"`

- **Alignment File**  
  - Golden Alignment Path:  
    `goldenAlignmentPath = "comparable-corpus/comparable_documents_with_golden_alignment_v2/hiru/hiru_english_sinhala.txt"`

## Model and Configuration

- **Machine Learning Model**:  
  The alignment process uses a pre-trained model stored at:  
  `mlModelPath = "cerebrex_code_B/model2_itm2.sav"`

- **Options**:
  - Embedding Option:  
    `option = "laser"`  
    (Choose between `laser` or `xlmr`)

  - Embedding Dimension:  
    `dimension = 1024`  
    (For LASER embeddings, use 1024; for XLMR or LaBSE, use 768)

  - Metric for Comparison:  
    `metric = "euclidean"`  
    (Options include `cosine`, `euclidean`)

## Running the Alignment Script

You can execute the alignment script using the following command:

```bash
echo "Document Alignment for $newsSource"

python3 document_alignment/main.py \
  embeddingPathA \
  embeddingPathB \
  readbleDataPathA \
  readbleDataPathB \
  goldenAlignmentPath \
  mlModelPath \
  option \
  dimension \
  metric
