Use '$search' URL parameter can do a query operation in IBM Domino API.

The query uses the FIELD keyword to specify the name of the field to search, followd by the operator CONTAINS adn the value to search for. Multiple search can be combined using the AND operator.
%20 is a URL encoding for a space character in URL.

An Example:
Search data where DocID = 'Fcd5e7e8f-e3dd-4aee-a4b4-580cc7b25561' AND DocRevision = '2'
The url search part should be like this:
search=FIELD%20DocID%20CONTAINS%20Fcd5e7e8f-e3dd-4aee-a4b4-580cc7b25561%20AND%20FIELD%20DocRevision%20CONTAINS%202
