- Hierarchy
	- {{namespace subject}}
- rough
	- #+BEGIN_QUERY
	  {:title [:h3 "Subject"]
	   :query [:find ?subject
	    :kesys ubject
	    :where
	     [?b :block/properties-text-values ?prop]
	     [(get ?prop :subject) ?subject]
	   ]
	   :result-transform (fn [r] (sort r))
	   :view (fn [result] (for [r result] 
	    [:div [:a 
	      {:href (str "#/page/" (get-in r [:subject]))} 
	      (get-in r [:subject])
	    ] ]
	   ) )
	  }
	  #+END_QUERY
	- #+BEGIN_QUERY
	  {
	  :query [
	      :find ?prop
	      :where
	        [?b :block/properties ?prop]
	  ]
	  :view(fn [rows] (for
	      [prop (sort (distinct (flatten (map keys rows))))]
	      [:div (clojure.string/replace-first (str prop) ":" "") ]))
	  }
	  #+END_QUERY
	-
-