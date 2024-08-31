# Fashion_E-Commerce_Recommendor
using a two-tower approach for creating query and product embeddings using SBERT and spotify's ANNOY for clustering embeddings.


## Requirements

SentenceTransformer('distilbert-base-uncased')

* Annoy

* Numpy 

* Pandas

* Seaborn

* Matplotlib

  

# Step-by-Step Breakdown:-

Generating Raw Query Embeddings:

1. Convert the desired column you want to embed into a List.

2. Generate embeddings using Sentence Transformers
    retreiving chunks of 10000 at a time (orignal dataset has 47000 rows)

3. Reshape 768D array => 32D array (having 32 columns),
    using reshape.array

4. np.concatenate along columns(axis = 1) these Sentence Embeddings to df_tmp

5. df_tmp.to_csv to query_counter (counter = 0 to 31)

6. Generate 32 files query_0 .... query_31

7. Create a df dfQCnct, Concatenate all these files
