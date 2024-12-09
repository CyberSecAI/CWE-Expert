# CWE-Expert

A CWE-Expert can be built for free in a browser in less than 5 minutes using the CWE Corpus files provided here in different formats.

This repo contains
1. Example prompts to be used with the CWE Expert.
2. How to build a CWE Expert
3. The MITRE CWE specification stripped down to the minimum required for CWE mapping as the corpus for the CWE Expert.

> [!NOTE]
> The code that creates the CWE Specification Corpus is [cwe_json.ipynb](./cwe_json.ipynb).



## Table of Contents
- [CWE-Expert](#cwe-expert)
  - [Table of Contents](#table-of-contents)
  - [Example Prompts](#example-prompts)
  - [LLM Tool NotebookLM](#llm-tool-notebooklm)
  - [CWE Specification Corpus](#cwe-specification-corpus)
    - [Mapping](#mapping)
    - [Unstructured text: markdown](#unstructured-text-markdown)
    - [Structured text: jsonl](#structured-text-jsonl)
    - [Unstructured text: pdf](#unstructured-text-pdf)



## Example Prompts

[questions.md](prompts/questions.md) contains example prompts or questions.

This gives an idea of the types of questions that can be asked of the CWE Expert. **Ask whatever you want!**

## LLM Tool NotebookLM

NoteBookLM is used in this example.

> [!TIP]
> The notebook can be shared with other users via email (using the share button top right) to allow them to use the notebook. See https://support.google.com/notebooklm/answer/14276471?hl=en.
> 
> Sharing is via a user's email.



## CWE Specification Corpus

A [CWE mapping file](CWE_corpus/markdown/cwe_mappings.md.txt) is provided to make it easy for an LLM to find CWE Mapping info. 


The stripped MITRE CWE specification corpus is available as
1. Structured text: [jsonl](./CWE_corpus/jsonl)
2. Unstructured text: [markdown](./CWE_corpus/markdown)
3. Unstructured text: [pdf](.CWE_corpus/pdf)


### Mapping

[CWE mapping file](CWE_corpus/markdown/cwe_mappings.md.txt) contains CWE Mapping info e.g. 
````
- Usage: Allowed
- Abstraction: Base
- 1003 view: Yes
````

> [!TIP]
> This [CWE mapping file](CWE_corpus/markdown/cwe_mappings.md.txt) can be used with any RAG corpus.


The version of the CWE specification used contains a total of 964 CWE entries.

The mapping values for these CWEs are given here.

Abstraction values frequency:
- Base: 536 (55.6%)
- Variant: 299 (31.0%)
- Class: 112 (11.6%)
- Pillar: 10 (1.0%)
- Compound: 7 (0.7%)

Usage values frequency:
- Allowed: 752 (78.0%)
- Allowed-with-Review: 86 (8.9%)
- Prohibited: 84 (8.7%) (these are removed from the RAG corpus)
- Discouraged: 42 (4.4%)

 A "Compound" weakness is a meaningful aggregation of several weaknesses, currently known as either a Chain or Composite per https://cwe.mitre.org/documents/schema/#AbstractionEnumeration


View is 1003 "CWE Simplified Mapping" per https://cwe.mitre.org/data/downloads.html
- it contains 130 CWEs
- as used by NVD https://nvd.nist.gov/vuln/categories
- This is not in the CWE JSON file i.e. the CWE specification does not say all the views a CWE is in.



### Unstructured text: [markdown](./CWE_corpus/markdown)

markdown version of the stripped CWE specification.

A .txt is added to the files as NotebookLM does not support files with md extension.


### Structured text: [jsonl](./CWE_corpus/jsonl)

jsonl version of the stripped CWE specification.

A .txt is added to the files as NotebookLM does not support files with jsonl extension.


### Unstructured text: [pdf](./pdf)

The full [CWE specification pdf](https://cwe.mitre.org/data/published/cwe_latest.pdf) from https://cwe.mitre.org/data/downloads.html is split into smaller pdfs using [a script](./pdfsplit.sh)

> [!NOTE]
> - it contains a lot of information that an LLM does not need for CWE Mapping e.g. change history
> - it is less structured than markdown or json


