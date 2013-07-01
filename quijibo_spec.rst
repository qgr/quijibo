================================
Quijibo Query Tree Specification
================================

A Quijibo Query Tree is a JSON object that may contain one and only one key,
representing the query type, limited to the following values:

 - select
 - insert
 - update
 - delete

This key maps to another object which has a structure specific to that query
type.

select
======

`select` Objects may contain the following keys:

 - select_list
 - distinct
 - from
 - where
 - group_by
 - order_by
 - limit

select_list
===========

`select_list` is an Array that represents the expressions that will form
the output rows. In the simple case, this is just a list of columns.

distinct
========

`distinct` may be an empty Array, as a shortcut to mean "distinct on all
output expressions", or a list of output expressions in the `select_list`.

from
====

`from` is a single String value representing a tabular dataset to be
queried.

where
=====

`where` must have a single key pointing to a clause object.

TODO: Specify order by clause objects.

group_by
========

`group_by` is an Array that contains the expressions to group the output
rows by for aggregrations. The expressions must be present in the `select_list`.

order_by
========

`order_by` is an Array that contains the order objects to sort the
output rows by. The expressions must be present in the `select_list`.

TODO: Specify order expressions.

limit
=====

`limit` is a Number that represents the number of rows to be returned, after
sorting.

TODO: Specify insert, update, delete objects.
