- Here is the basic principle for RAGs:
	- 1. Break down context into smaller "chunks".
	- 2. Embed each chunk into a high dimensional vector representation (see [[transformers]] for more on how exactly this works).
	  3. For each query, find the `n` most similar chunks.
	  	1. The dot product of two vectors (in this case, the embedding for the query and the embedding for a chunk) quantifies how similar the two vectors are. (See [[dot product]] for more.)
	  4. Include the result from Step 3 into the prompt in some way.
-
-