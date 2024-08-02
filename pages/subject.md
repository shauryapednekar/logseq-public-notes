- Hierarchy
	- {{namespace subject}}
- rough
	- #+BEGIN_QUERY
	  {:title [:h3 "Subjects"]
	   :query [:find ?subject
	    :kesys ubject
	    :where
	     [?b :block/properties-text-values ?prop]
	     [(get ?prop :subject) ?subject]
	   ]
	   :result-transform (fn [r] (sort r))
	  }
	  #+END_QUERY
	-
-