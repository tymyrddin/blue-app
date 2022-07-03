# Remote file inclusion (RFI)

* Scanning to detect RFI takes less time and resources than detecting such vulnerabilities through manual penetration testing.
* [Input validation](Input.md) is a much less effective method in this case because adversaries can go around it using clever tricks.
* Never trust user input. If files must be included in the website or web application code, use a whitelist of allowed file names and locations.
* In the case of PHP applications, most current installations are configured with `allow_url_include` set to `off` in `php.ini`. This makes it impossible for malicious users to include remote files. However, [Local File Inclusion (LFI)](Local-file-inclusion.md) is still possible in such a case.


## Related attack trees

* [Shell from remote file inclusion vulnerabilities](attack-trees:docs/application/Remote-file-inclusion)