Additional materials to the paper “An Approach to Information Extraction from Texts of a Limited Subject Domain Based on a Chain of Large Language Models” by Elena A. Sidorova, Aleksandr I. Ivanov, Daria V. Ilina, Kristina A. Ovchinnikova, Nikita M. Osmushkin, Aleksey S. Sery.

## Datasets

The materials contain marked-up corpora of texts in the subject area of Computational Linguistics.

### Dataset with markup of terms
The [terms](./terms/) folder contains a dataset with expert markup of subject area terms in BIO notation: a B (beginning) label is placed to indicate the beginning of the term, I (inside) is placed to indicate a token – the continuation of the term, and O (outside) is any word outside the term. The corpus is used to train ruRoBERTa to extract subject domain terms.

### Dataset with markup of terms, their classes and relations
The [ents](./ents/) folder contains a corpus of texts, manually annotated by experts, with the following information:
* text fragments;
* terms contained in each fragment;
* start and end position of each term (ordinal numbers of the first and last characters);
* the class of each term;
* relations between terms for each class.
The dataset is used to conduct experiments with LLM to extract terms and relations.

Seventeen classes were used in the markup:
* Person
* Dataset
* Environment
* Library
* Organization
* Value
* Lang
* Date
* Model
* Activity
* Task
* InfoResource
* Method
* Metric
* Object
* Application
* Science

The following relationships between the terms were labelled:
* hasAuthor (for classes Method and Organization, Method and Person, Application and Person, Application and Organization, Model and Organization, Model and Person, Activity and Organization, Library and Person, Library and Organization)
* isUsedIn (for classes Method and Science, Application and Science, Method and Application, Metric and Task, Model and Application, Environment and Library, Method and Library, Library and Science)
* isUsedInSolving (for classes Object and Task)
* isDateOf (for classes Date and Method, Date and Model, Date and Application)
* isModificationOf (for classes Model and Model)
* isExampleOf (for classes Model and Model)
* isPartOf (for classes Model and Model, Method and Method, Object and Object)
* isAppliedTo (for classes Metric and Method, Method and Object, Application and Object, Library and Object)
* hasValue (for classes Metric and Value)
* solves (for classes Method and Task)
* isSolvedIn (for classes Task and Science)
* isTrainedForSolving (for classes Dataset and Task)
* isTrainedOn (for classes Model and Dataset)
* isUsedFor (for classes Metric and Model)
* Language (for classes Model and Lang, InfoResource and Lang, Dataset and Lang)
* isUsedForSolving (for classes Application and Task, Model and Task, Library and Task)
* isUsedForTraining (for classes Method and Model)
* uses (for classes Method and Model)
* isIncludedIn (for classes Model and Library)
* isAlternativeNameFor (for classes Object and Object, Activity and Activity, Application and Application, Person and Person, Task and Task, Method and Method, Organization and Organization, Library and Library, Dataset and Dataset, Metric and Metric, Science and Science, InfoResource and InfoResource, Environment and Environment, Model and Model)

### Datasets with markup of coreference relations
The [coref](./coref/) folder contains files with fragments of articles, in which the words and phrases denoting concepts of the subject area and being in coreferential relations are marked. Coreferent terms are combined into arrays, and the terms themselves are labelled with ordinal numbers of initial and final symbols.
The markup was done manually by the expert; the files were generated using the CorefMarkup program.

## See also:
Sidorova E., Ivanov A., Ovchinnikova K. Information extraction from texts based on ontology and large language models [In Russian] // Ontology of designing. 2025. — Vol. 15, no. 1. — P. 114–129. — https://doi.org/10.18287/2223-9537-2025-15-1-114-129

## License

Shield: [![CC BY 4.0][cc-by-shield]][cc-by]

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]

[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[cc-by-shield]: https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg