# File upload

* Never allow users to upload executable files. Use a whitelist of allowed file types.
* Check file type AND file extension. Verify file type against the whitelist.
* Use input validation to prevent the whitelist from being bypassed using the filename.
* Use input validation to prevent the metadata from being exploited. For example, remove any unnecessary metadata such as exif data from images and remove control characters from filenames and extensions. 
* Remove any unnecessary file evaluation.
* Limit the size of the filename.
* Limit the size of the file (unexpectedly small files and large files can both be used in denial of service attacks). 
* Limit the directory to which files are uploaded.
* Scan all files with antivirus software.
* Name the files randomly or using a hash instead of by the user's input. This will prevent an adversary from scripting access to uploaded files using the filename as an attack vector. 
* Simplify error messages. Remove any directory paths and server configurations from error messages that adversaries could use. 
* Check the uploaded directory to make sure the read/write/execute user permissions are correct.

## Related attack trees

* [Exploit file upload vulnerabilities](attack-trees:docs/application/File-upload)
* [Denial of Service (DoS)](attack-trees:docs/network/DoS)