Textbites
=========
Textbites is a Python library for representing textual resources. It provides a
interface for browsing and searching along with several implementations and
unit tests.

Textbites is used in [Nutritious][1], a Django-based web application for
browsing and tagging textual content.

[1]: http://github.com/jplehmann/nutritious

Details
-------
Textbites' API includes two primary classes: Resource and Reference.

*Resources* are containers of textual content which provide a top-most
reference to that resource as well a "reference locator" service which parses a
string reference and returns the associated reference object.  A resource could
contain additional meta-data such as the type of resource.

*References* represent an iterator-like pointer into the resource. They provide
methods to:

* Retrieve the text at that location.
* Retrieve a human-readable version of the reference string.
* Navigate by traversing to the parent or child references.
* Search over the textual content at that location returning matching references.

Data
----
The Library class can dynamically load resources from a directory by detecting
type by extension (e.g. JSON or TSV). Several resources are included in the
project and are located in the "data" directory. 

Implementations
---------------
Several implementations of the API are included. See comments in source code
for more details.

* SimpleBooks
  * Book, Chapter, ChapterRange, Line, LineRange
  * Bible (collection of SimpleBooks)
  * Quotes
* ViewBooks (alternate design)

Tests
-----
Over 100 unit tests can be run with `bin/run_tests.sh`.

Future
------
Currently, all implementations are static, in-memory resources. This is a big
limitation for many kinds of resources (e.g. web bookmarks), and will most
likely be addressed by subclassing it within a framework which provides ORM
like Django.

