# atomspace-js
JavaScript bindings to the AtomSpace

## Status
Version 0.0.0 - there is nothing here yet.

## Motivation and General Plan
There is a recurring desire to access the AtomSpace contents from a
web-browser. There are three different ways in which this can be done,
listed below. The first way is the worst, the last way is the best.

* Create a RESTful AtomSpace server, and send selected AtomSpace data to
  the browser. This is a bad design for two reasons: (1) it places a
  large CPU burden on the server to create the formats that the browser
  wants. (2) It forces the browser to remember a large number of Atoms,
  effectively re-creating the concept of the AtomSpace, but badly,
  inside the browser.

* Use the existing [CogServer](https://github.com/opencog/cogserver) for
  network communications. This solves problem (1) above: it's fast, it's
  easy, it works, it's maintained.  It does NOT solve (2).

* Create JavaScript interfaces to the AtomSpace. This avoids problem (1)
  and solves problem (2).  The browser now has complete access to a full
  AtomSpace, with all the bells and whistles and features and functions.
  In order to access remote AtomSpaces, a browser or a JS app can use the
  [CogStorageNode](https://wiki.opencog.org/w/CogStorageNode) to connect
  to other AtomSpaces over the network.

## The API
What should the JavaScript API to the AtomSpace look like? There are two
parts to the API: a representation for Atoms and Values, and a small
handful of **ad hoc** function calls.
