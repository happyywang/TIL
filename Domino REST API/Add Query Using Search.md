Add a query by search in IBM Domino API, use ‘$search’ URL parameter.
Example:
Search data in NotesDB where DocID = 'Fcd5e7e8f-e3dd-4aee-a4b4-580cc7b25561' AND DocRevision = '2', then search part url should be look like this:
search=FIELD%20DocID%20CONTAINS%20Fcd5e7e8f-e3dd-4aee-a4b4-580cc7b25561%20AND%20FIELD%20DocRevision%20CONTAINS%202

The query uses the FIELD keyword to specify the name of the field to search, followed by the operator CONTAINS and the value to search for. Multiple search criteria can be combined using the AND operator.
%20 is a URL encoding for a space character in URL. In URLs, spaces are not allowed and must be replaced with a special code, which is %20.
