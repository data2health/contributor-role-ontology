The following is intended to serve as a guide for anyone who would like to contribute to the CRO project by making new term requests.

# Does the term you are looking for already exist?
First, please look at the current HPO and check whether the term is already there. There are several online browsers that you can use, and it is also possible to use [Protege](http://protege.stanford.edu/).
* [HPO Browser](https://hpo.jax.org/app/)
* [Old HPO Browser](http://compbio.charite.de/hpoweb/showterm?id=HP:0000118)
* [EBI Ontology Lookup Browser for HPO](https://www.ebi.ac.uk/ols/ontologies/hp)
* [Ontobee Browser for HPO](http://www.ontobee.org/ontology/HP)
* [Monarch Initiative Phenotype Browser](https://monarchinitiative.org/phenotype) (Contains additional information on model organism phenotypes)
* [NCBO Browser for HPO](https://bioportal.bioontology.org/ontologies/HP/?p=classes&conceptid=root)

# Is the term you are looking for a synonym of an existing term?
If you do not immediately find the term you are looking for, please look for synonyms. One way of doing this with one of the HPO browser listed above is to go to a likely parent of the term and peruse all of the children to spot a likely synonym. For instance, if you are looking for a term entitled swollen finger and do not find it, go to the term _Abnormality of finger_ in one of the above browsers and look through all of the children.

If you find such a term, then make a term request SYNONYM Request: Please add "_My synonym_" to existing HPO term "_Term_"

# Bundled terms
If you find a description in a publication such as "Sparse eyebrows and eyelashes", note that the description is refering to two separate phenotypic features. The HPO would encode this using two different terms, _Sparse eyebrows_ and _Sparse eyelashes_. The idea is that one HPO term should refer to an "atomic" phenotypic abnormality rather than to a collection of abnormalities observed in an individual patient. Please "debundle" the description and proceed as described above.

# The distinction between diseases and phenotypes
The community uses the word "phenotype" with multiple meanings. The HPO defines a **disease** as an entity that has all four of the following features:
- an etiology (whether identified or as yet unknown)
- a time course
- a set of phenotypic features, and 
- if treatments exist, there is a characteristic response to them

A phenotype (better: phenotypic feature) is a component of a disease. HPO terms can be used to describe the set of phenotypic features that characterize a disease. For instance, if the disease is the common cold, then the phenotypes would be runny nose, fever, cough, fatigue, etc. Therefore, in the following description:
```
a sepsis-like condition with intestinal pseudoobstruction, transient hypoglycemia, 
cholestatic hepatitis, and transient renal failure (maximum plasma creatinine 
132 μmol/L and urea 11 mmol/L at day 5 of life, which normalized on day 10).
```
We would conceptualize the "sepsis-like condition" as a disease, and would use HPO terms to describe

1. intestinal pseudoobstruction
2. transient hypoglycemia
3. cholestatic hepatitis
4. transient renal failure (or perhaps increased creatinine and increase BUN)

# Anatomy of an HPO term
Once you have convinced yourself that the item you need is not already present in the HPO, please provide us with the following information

1. **Preferred Label:** What is the name of the term? This should be the name most commonly used by the community.
2. **Synonyms.** If you are aware of synonyms for you term, please include them in your term request.
3. **Definition.** Please try to formulate a definition of your term that will be comprehensible to non-specialists.
4. **References.** Please include a PubMed ID if possible, so that other users of the HPO can find more information about your term.
5. **Parent term.** If possible, please suggest where your new term should be placed within the existing ontology. It is sufficient to write the name(s) of the parent term(s) (i.e., you do not need to tell us the HPO ID, e.g., HP:1234567)
