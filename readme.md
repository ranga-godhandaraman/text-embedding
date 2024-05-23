##  PDF Text Embedding with Sentence Transformers

This Python code extracts text from PDFs, splits it into chunks, and generates sentence embeddings for those chunks using the Sentence Transformer library.

**Functionality:**

1. **Extract Text:**
    - Uses `PyMuPDF` library (`fitz`) to open and process PDFs.
    - Iterates through each page and extracts text using `page.get_text()`.
    - Concatenates all page text into a single string.
2. **Chunk Text:**
    - Uses `nltk` library to tokenize the extracted text into sentences.
    - Defines a chunk size (default 100 words).
    - Iterates through sentences, adding them to a chunk until the chunk reaches the size limit.
    - Creates a list of text chunks.
3. **Generate Embeddings:**
    - Loads a pre-trained sentence transformer model (`all-MiniLM-L6-v2` by default).
    - Encodes each text chunk into a dense vector representation (embedding) using the model.
    - Returns a list of embeddings corresponding to the text chunks. 

**Example Usage:**

The provided example demonstrates how to use the functions with two PDFs: `path_to_your_first_pdf.pdf` and `path_to_your_second_pdf.pdf`.  

**Requirements:**

- Python 3.x
- `PyMuPDF` library: `pip install fitz`
- `nltk` library: `pip install nltk`
- `sentence-transformers` library: `pip install sentence-transformers`

**How to Use:**

1. Install the required libraries.
2. Replace the placeholder paths (`path_to_your_first_pdf.pdf` and `path_to_your_second_pdf.pdf`) with the actual paths to your PDFs.
3. Run the script. The script will generate sentence embeddings for each text chunk in the PDFs and store them in `pdf1_embeddings` and `pdf2_embeddings`.

**Further Customization:**

- You can modify the `chunk_size` parameter in the `chunk_text` function to control the size of the text chunks.
- You can experiment with different pre-trained sentence transformer models available from the Sentence Transformers library [https://huggingface.co/sentence-transformers](https://huggingface.co/sentence-transformers).

**Note:**

- This is a basic example. You'll likely need to integrate this functionality into your larger application and perform additional processing on the generated embeddings based on your specific needs.

