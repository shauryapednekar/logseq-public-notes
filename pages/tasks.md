- Next
	- {{query (property :status "next")}}
	  query-table:: true
	  query-properties:: [:page]
- Future
	- {{query (property :status "todo")}}
	  query-table:: true
	  query-properties:: [:page]
	- #+BEGIN_QUERY
	  {:title "TODO tasks"
	   :query [:find (pull ?b [*])
	           :where
	           (task ?b #{"TODO"})]}
	  #+END_QUERY
	- #+BEGIN_QUERY
	  {:title ["Pages"]
	   :query (and (AND (page-property status Next) (page-property area Arbeit)) (page-property :status "#inBearbeitung")) }
	  #+END_QUERY
	-