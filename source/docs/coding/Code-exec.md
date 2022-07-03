# Arbitrary code execution

* Imposing strict control of outgoing connections is only possible for very specialized servers. And even then, there is nothing to stop an adversary from opening a listener on a common port such as 80. All connections would have to be monitored for content.
* Disabling most tools that make it possible to create a reverse shell is also only possible for specialized servers. Reverse shells can be created using different tools and languages. This would make it more difficult for the adversary, but not impossible.
* Avoiding or dangerous functions such as Python `eval()` or `passthru()` and [input validation](Input.md) of dangerous functions (if they have to be used) may help some.

Even if succeeding in avoiding reverse shells, there are other methods that an adversary can use to establish control 
over a system. For example, by using web shells. And reverse shells are always a result of some other kind of attack 
because the system needs to be compromised first.

The best way to avoid reverse shells is to protect against attacks that allow impostors to gain shell access in the 
first place.

## Related attack trees

* [Exploit code execution vulnerabilities](attack-trees:docs/application/Remote-code-execution)
