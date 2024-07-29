subject:: [[subject/ai]]

- Here is the basic principle for RAGs:
	- Break down context into smaller "chunks".
	  logseq.order-list-type:: number
	- Embed each chunk into a high dimensional vector representation (see [[transformers]] for more on how exactly this works).
	  logseq.order-list-type:: number
	- For each query, find the `n` most similar chunks.
	  logseq.order-list-type:: number
		- logseq.order-list-type:: number
		  1. The dot product of two vectors (in this case, the embedding for the query and the embedding for a chunk) quantifies how similar the two vectors are. (See [[dot product]] for more.)
	- Include the result from Step 3 into the prompt in some way.
	  logseq.order-list-type:: number
-