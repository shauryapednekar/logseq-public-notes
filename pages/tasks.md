- 📝 Topics to write about.
	- #+BEGIN_QUERY
	  {:title ["In Progress"]
	   :query (page-property status active) 
	  :view (fn [rows] [:table 
	   [:tbody 
	  (for [r rows] [:tr 
	     [:td [:a {:href (str "#/page/" (get r :block/name))} (clojure.string/capitalize (get r :block/name))]]])
	     ]]
	  )
	  :query-table true
	  }
	  #+END_QUERY
	- #+BEGIN_QUERY
	  {:title ["Next"]
	   :query (page-property status next) 
	  :view (fn [rows] [:table 
	   [:tbody 
	  (for [r rows] [:tr 
	     [:td [:a {:href (str "#/page/" (get r :block/name))} (clojure.string/capitalize (get r :block/name))]]])
	     ]]
	  )
	  :query-table true
	  }
	  #+END_QUERY
	- #+BEGIN_QUERY
	  {:title ["Future"]
	   :query (page-property status todo) 
	  :view (fn [rows] [:table 
	   [:tbody 
	  (for [r rows] [:tr 
	     [:td [:a {:href (str "#/page/" (get r :block/name))} (clojure.string/capitalize (get r :block/name))]]])
	     ]]
	  )
	  :query-table true
	  }
	  #+END_QUERY
- #+BEGIN_QUERY
  {:title [:h3  "TODOs"]
   :query [:find (pull ?b [*])
   :where
    [?b :block/marker ?marker]
    [(contains? #{"TODO" "LATER"} ?marker)]
   ]
   :result-transform (fn [result] (sort-by (fn [r] (get-in r [:block/scheduled])) result)) ; sort the result by the scheduled date
   :table-view? false
   :breadcrumb-show? false  ; don't show the parent blocks in the result !important, due to result-transform the grouping is lost, and so you will be left with a simple list of TODO items. having those parents blocks mixed in may make the list more confusing. (setting this to true won't show the page btw!)
   :collapsed? false
  }
  #+END_QUERY
-