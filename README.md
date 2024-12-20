# CWE-Expert

💁 A CWE-Expert can be built for free in a browser in less than 1 minute using the instruction and CWE Corpus files provided here.

You can ask your CWE-Expert 
- any questions about CWEs
- to assign CWEs to vulnerability descriptions

**Demos**

- [Youtube video](https://www.youtube.com/watch?v=DAWJjYCpudE) showing general CWE questions, and CWE assignment for several CVEs
  
  [![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/DAWJjYCpudE/0.jpg)](https://www.youtube.com/watch?v=DAWJjYCpudE)
- [Some nuanced CWE assignments](./prompts/CVE_assignments.md)


This repo contains

1. The MITRE CWE specification stripped down to the minimum required for CWE mapping as the corpus for the CWE Expert.
2. Instructions on how to build a CWE Expert
3. Example prompts/questions to be used with the CWE Expert.

> [!NOTE]
> The code that creates the CWE Specification Corpus is [cwe_json.ipynb](./cwe_json.ipynb).



## Table of Contents
- [CWE-Expert](#cwe-expert)
  - [Table of Contents](#table-of-contents)
  - [CWE Specification Corpus](#cwe-specification-corpus)
    - [Mapping](#mapping)
    - [Unstructured text: markdown](#unstructured-text-markdown)
    - [Structured text: jsonl](#structured-text-jsonl)
    - [Unstructured text: pdf](#unstructured-text-pdf)
  - [LLM Tool NotebookLM](#llm-tool-notebooklm)
  - [Example Prompts](#example-prompts)




## CWE Specification Corpus

A [CWE mapping file](CWE_corpus/markdown/cwe_mappings.md.txt) is provided to make it easy for an LLM to find CWE Mapping info. 


The stripped MITRE CWE specification corpus is available as
1. Structured text: [jsonl](./CWE_corpus/jsonl)
2. Unstructured text: [markdown](./CWE_corpus/markdown)
3. Unstructured text: [pdf](.CWE_corpus/pdf)

> [!NOTE]
> CWE Version latest as at December 2024 is used as the input CWE specification:
> - JSON CWE Version 4.1**6** [https://github.com/CWE-CAPEC/REST-API-wg/blob/main/json_repo/cwe.json](https://raw.githubusercontent.com/CWE-CAPEC/REST-API-wg/refs/heads/main/json_repo/cwe.json)
> - PDF CWE Version 4.1**6** https://cwe.mitre.org/data/published/cwe_latest.pdf 


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



## LLM Tool NotebookLM

NoteBookLM is used in this example.

1. Open https://notebooklm.google.com/ in a broswer
2. Click Sources
3. Upload all files in the [markdown](./CWE_corpus/markdown) directory


> [!TIP]
> The notebook can be shared with other users via email (using the share button top right) to allow them to use the notebook. See https://support.google.com/notebooklm/answer/14276471?hl=en.
> 
> Sharing is via a user's email.

> [!IMPORTANT]
> After importing each file to NotebookLM, you should click on each source and look at the end of each source, and compare it to the end of the file imported.
>
> This ensures all of the file content is imported!
> NotebookLM will truncate files silently if it encounters certain content e.g. \"\<script\>\" or \"\<style\>\".


## Example Prompts

[questions.md](prompts/questions.md) contains example prompts or questions.

This gives an idea of the types of questions that can be asked of the CWE Expert. **Ask whatever you want!**
