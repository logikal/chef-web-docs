.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.


If the ``config.json`` file specifies:

.. code-block:: javascript

   "delivery-truck": {
     "deploy": {
       "search": {
         "index": :node,
         "query": 'SEARCH_QUERY'
       }
     }
   }

then the search against all node objects on the |chef server| for that query.
