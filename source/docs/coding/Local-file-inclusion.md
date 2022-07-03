# Local file inclusion (LFI)

When trying to detect file inclusion vulnerabilities in code while it is being developed, or before the software is 
deployed, usually code analysis tools are used. These miss about half of all vulnerabilities and give a lot of false 
positives, making the process tedious, lengthy and expensive. As a result many developers skip it.

Try to avoid passing user-supplied input to the filesystem APIs. Many of the functions that do that can be rewritten to 
deliver the same behaviour, without the exposure. 

* [Validate user input](Input.md) before processing it. Either compare the input against a whitelist of permitted values or verify that the input contains only permitted content – for example, alphanumeric characters.
* After validation, verify that the canonicalised path starts with the expected base directory.
* Save file paths in a secure database and give an ID for every single one, this way users only get to see their ID without viewing or altering the path.
* Use verified and secured whitelist files and ignore everything else.
* Do not include files on a web server that can be compromised, use a database instead.
* Make the server send download headers automatically instead of executing files in a specified directory.
* Do not use dynamic file inclusion. Use static file inclusion.

## Related attack trees

* [Shell from local file inclusion vulnerabilities](attack-trees:docs/application/Local-file-inclusion)