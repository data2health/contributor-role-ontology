# Editors' Guide for CRO developers

## GETTING STARTED

### Creatng a new branch

Edits to the CRO should be done on a branch via a Pull Request. For guidance on creating a branch and creating a pull request, go [here](pages/editorsguide/pullrequest.md).

1. Open the file cro-edit.owl in Protege. On the bottom left, you should see your branch name (not Git: master)

2. Switch on the Elk reasoner: Reasoner->Start Reasoner. If you are making changes, be sure to synchronize the reasoner.

### Edit the ontology in Protege:

1. Find parent term in Protege by searching in the search box (at top of screen)
1. Double check that term is not already there
1. Add subclass
1. Add label (URI should be auto-generated)
1. Under annotations, add definition, click OK
1. Annotation on definition (see below)
1. database_cross_reference
1. dbxref: Your ORCID (if you do not have an ORCID, sign up here: [https://orcid.org/](https://orcid.org/))
1. Under annotations, add synonyms, if necessary (has_exact_synonym, etc).

### Save

**do not edit any other files!!!**

### Commit your changes

~~~
  git diff
  git status
  git commit -a -m "COMMIT MESSAGE"
  git push
~~~

## CREATING NEW TERMS (Checklist)

* In general, the term should be announced on the [GitHub tracker](https://github.com/data2health/contributor-role-ontology/issues) prior to creation of new term
* Make sure the Protege reasoner (Elk) is active to investigate any unforeseen and unintended logical inferences
* Most terms should have the following items added:
  * Label  
  * Definition (english-language). This should be extended by database_cross_reference (e.g., PMID:123 to provide additional information. _Note, there should be no spaces in the PMID._)  
  * _Optional_ Comment. A comment can be used to provide additional information about the term.  
  * database_cross_reference. Indicate an item in another database that is equivalent to this CRO term. For instance, [add example]. We can add a label (e.g., "Single umbilical artery") by the "Annotations" button.  
  * If possible, add relevant synonyms. Use "has_exact_synonym" for true synonyms (preferred). If needed, use has_related_synonym for words/phrases that are not 100% identical in meaning but are likely to be confused with the main term.  

## Closing Issues with Commit Messages
This is the preferred way to commit a new term.  
See the [GitHub help pages for this](https://help.github.com/articles/closing-issues-via-commit-messages/).
To close and commit terms that relate to issue #68, for instance, create the terms and save them to file.
git add -u .
git commit -m "This closes #68"
git push

## CHECKLIST
---------

Always synchronize the reasoner before committing. Did your changes
introduce unsatisfiable classes? If so, investigate them.

For any classes you have created, are they in your ID range? Did you
add text definitions, adding provenance information? Is the reasoner finding unintended inferred equivalent classes? Subclasses?

Check the Travis report after your commits. This should alert you to
any of the following:

 * consistency problems with anatomy ontologies
 * consistency problems with other ontologies
 * violation of obo-format (e.g. two labels for a class; two text
   definitions; etc)

#### Back to [Editors Guide](https://data2health.github.io/contributor-role-ontology/pages/editors.html)
#### Back to [home](https://data2health.github.io/contributor-role-ontology/)
