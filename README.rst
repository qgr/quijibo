=======
quijibo
=======


*Dude, that's not how you spell "kwijibo"*

Quijibo - it has a "Q" and a "J", and so a good name for a JSON representation
for query trees.  A Quijibo Query Tree is JSON object that is analagous
to a `query tree`_ constructed from parsing SQL.
So, in your language of choice, you can build a Query Tree out of simple lists
and maps, serialize it to JSON, and a Quijibo Executor will take your JSON and
execute it in the environment and dataset of your choice - be it a JavaScript
array, an SQL database, or the client-side `IndexedDB`_.

.. _IndexedDB: https://developer.mozilla.org/en-US/docs/IndexedDB/Basic_Concepts_Behind_IndexedDB

.. _query tree: http://www.postgresql.org/docs/devel/static/querytree.html

Example
=======

.. code-block:: javascript

   {
     select: {
      cols: [
       'name',
       'cost'
      ],
      from: 'projects',
      where: {
       or: [
         {
          eq: [
          'start_year',
          1977
          ]
         },
         {
          eq: [
          'start_year',
          1966
          ]
         }
       ]
      }
     }
   }

