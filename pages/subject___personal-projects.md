- #+BEGIN_QUERY
  {:title ["Pages"]
   :query (page-property subject [[subject/personal-projects]]) 
  :view (fn [rows] [:table 
   [:tbody 
  (for [r rows] [:tr 
     [:td [:a {:href (str "#/page/" (get r :block/name))} (clojure.string/capitalize (get r :block/name))]]])
     ]]
  )
  :query-table true
  }
  #+END_QUERY
-