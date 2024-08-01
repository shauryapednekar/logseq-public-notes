- #+BEGIN_QUERY
  {:title ["Next"]
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
- #+BEGIN_QUERY
  {:title ["Future"]
   :query (page-property status todo) 
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