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
	   :query (page-property status next) 
	  :view (fn [rows] [:table 
	   [:thead 
	    [:tr 
	     [:th "Page"]  ] ] 
	   [:tbody 
	  (for [r rows] [:tr 
	     [:td [:a {:href (str "#/page/" (get r :block/name))} (clojure.string/capitalize (get r :block/name))]]])
	     ]]
	  )
	  :query-table true
	   
	  }
	  #+END_QUERY
	-