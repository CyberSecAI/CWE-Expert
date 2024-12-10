# Questions

## Check for grounding
1. what is a dog?

## what cwe ids

1. What cwe ids are associated with buffer overflow?
2. What cwe ids are associated with xss?
3. What cwe ids are associated with path traversal?

## A topic

### XSS
1. What cwe ids are associated with xss?
2. How does the OWASP Top Ten 2021 categorise XSS?
3. What are the types of XSS?
4. What is XSS an acronym for?
5. What is the parent weakness or cwe for xss and csrf?
6. What weaknesses are related to XSS?

## What is the best CWE for

1. What is the best CWE for CVE-2021-27104 "Accellion FTA OS Command Injection Vulnerability"
2. What is the best CWE for CVE-2019-1653 "Cisco Small Business RV320 and RV325 Routers Information Disclosure Vulnerability"


## Detailed Instructions


### CVE-2021-27104
````
What is the best CWE for "Accellion FTA OS Command Injection Vulnerability"

STEPS
Before recommending any CWE as the root cause of a vulnerability, or one of several weaknesses in a Chain leading to a vulnerability, consider these points in this order of priority:
1. similar CVE Descriptions from the ObservedExamples or Top25Examples and their CWEs
2. the CWE mapping "Usage" order of preference
3. the CWE mapping "Abstraction" order of preference
4. the CWE alternate terms
5. there can be more than one CWE

OUTPUT INSTRUCTIONS
Provide a table with the following to support your suggested CWEs
1. ID and title of the CWE
2. the vulnerability mapping "Usage" in order of preference: Allowed, Allowed-with-Review, Discouraged
3. the vulnerability mapping "Abstraction" in order of preference: Base, Variant, Class, Pillar, Compound 
4. CWE alternate terms
5. similar CVE Descriptions from the ObservedExamples or Top25Examples
6. a confidence level for your response.

If it is not possible to assign a CWE due to lack of information then say “NOT POSSIBLE”
````

### CVE

````

what is the best CWE to describe the root cause weakness in CVE "ProductX contains a default SSH public key in the authorized_keys file. A remote attacker could use this key to gain root privileges."

STEPS
Before recommending any CWE as the root cause of a vulnerability, or one of several weaknesses in a Chain leading to a vulnerability, consider these points in this order of priority:
1. similar CVE Descriptions for the root cause CWE from the ObservedExamples or Top25Examples 
2. the CWE mapping "Usage" order of preference
3. the CWE mapping "Abstraction" order of preference
4. the CWE alternate terms
5. there can be more than one CWE

OUTPUT INSTRUCTIONS
Provide a table with the top 3 best matching CWE to support your suggested CWEs with 
1. ID and title of the CWE
2. the vulnerability mapping "Usage" in order of preference: Allowed, Allowed-with-Review, Discouraged
3. the vulnerability mapping "Abstraction" in order of preference: Base, Variant, Class, Pillar, Compound 
4. CWE alternate terms
5. If this CWE is part of View 1003 not
5. similar CVE Descriptions from the ObservedExamples or Top25Examples
6. a confidence level for your response.

If it is not possible to assign a CWE due to lack of information then say “NOT POSSIBLE”
Review your proposed answer and iterate if required until you are satisfied 

````