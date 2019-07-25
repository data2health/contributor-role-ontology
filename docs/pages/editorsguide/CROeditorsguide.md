# Editors' Guide for CRO developers

## GETTING STARTED

### Creatng a new branch

_this content is under development_

Then, open the file cro-edit.owl in Protege

Switch on the Elk reasoner (see how to get plugins above). If you are making changes, be sure to synchronize the reasoner.

### Edit the ontology in Protege:

1. Find parent term in Protege by searching in the search box (at top of screen)
1. Double check that term is not already there
1. Add subclass
1. Add label (URI should be auto-generated)
1. Under annotations, add definition, click OK
1. Annotation on definition (see below)
1. database_cross_reference
1. dbxref: Your ORCID (if you do not have an ORCID, sign up here: [https://orcid.org/](https://orcid.org/))
1. Under annotations, add synonyms, if necessary (has_exact_synonym, etc). If applicable, mark the synonyms as an [abbreviation](https://github.com/obophenotype/human-phenotype-ontology/wiki/Abbreviation-synonym-annotation) or [layperson term](https://github.com/obophenotype/human-phenotype-ontology/wiki/Layperson-synonym-annotation).

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

* In general, the term should be announced on the GitHub tracker prior to creation of new term
* Make sure the Protege reasoner (Elk) is active to investigate any unforeseen and unintended logical inferences
* Most terms should have the following items added
** Label
** Definition (english-language). This should be extended by database_cross_reference (e.g., PMID:123 to provide additional information. _Note, there should be no spaces in the PMID._)
** Comment. This is optional but can be used to provide additional information about the term such as diseases that are characterized by the feature or diagnostic methods that can be used to demonstrated the feature
** database_cross_reference. Indicate an item in another database that is equivalent to this HPPO term. For instance, MeSH:D058529. We can add a label (e.g., "Single umbilical artery") by the "Annotations" button.
** If possible, add relevant synonyms. Use "has_exact_synonym" for true synonyms (preferred). If needed, use has_related_synonym for words/phrases that are not 100% identical in meaning but are likely to be confused with the main term.
* Note that "id" (e.g., HP:0001234) and "has_obo_namespace" (human_phenotype) were added automatically by the OBO to OWL conversion and are not required for new terms.


## Closing Issues with Commit Messages
This is the preferred way to commit a new term.  
See the [GitHub help pages for this](https://help.github.com/articles/closing-issues-via-commit-messages/).
To close and commit terms that relate to issue #608, for instance, create the terms and save them to file.
git add -u .
git commit -m "This closes #608"
git push


## OBSOLETING
---------------

!!! YOU NEED THE OBSOLESCENCE PLUGIN!!!! [https://github.com/balhoff/obo-actions/downloads](https://github.com/balhoff/obo-actions/downloads)

1. Find the  class you wish to obsolete, and compare it with the class you wish to replace (or consider) it with. You need to check that both the text definition and the logical axioms have the same intent, and that nothing desired is lost in the obsolescence.

2. Copy any subClass axioms that you intend to keep for historical purposes (e.g. those that are not replicated on the target class) into a comment annotation property. If you do this, please ensure to add to any exisiting comments rather than adding a new COMMENT. There can be only one COMMENT in obo format and Jenkins will throw an error. If there are equivalence axioms, you may wish to consult with an expert to make sure the axioms are retained properly in the file.

3. Go to the obsolescence plugin by going to the edit menu and scroll to the bottom, to "Make Entity Obsolete". This will perform the following for you:
	Relabel the class as "obsolete your old term label here".
	Add an annotation property, "deprecated", value "true", of type "boolean".
	Delete subClassOf axioms
You should see the class crossed out after you do this.

4. Add an annotation property "term replaced by". Navigate to the term by clicking on the "entity IRI" and either browse or control F to find the term that is replacing the one being obsoleted.

5. YOU HAVE TO ADD THE ALTERNATIVE-ID TAG to the class that replaces the obsolote class. All IDs of the old term have to be moved to this field!!

6. You may wish to add a comment regarding the reason for obsolescence or so as to include reference to why the term was replaced with whatever is indicated. Again, do not add more than one comment annotation on a class.

### SEARCHING BY URI
----------------
_**Note - this no longer applies in newer versions of Protege (ie Protege 5.0 and up)**_  
To view IDs instead of labels:  
View -> Render by name (rdf: id)  
search for ID  
View -> Render by label  
click on parent in description  
click back button to get back to your term  
(stupid, eh?)  


## MERGING
---------------
If you use the Refactor > Rename entity... menu item, and make the IRI of one term the same as the
IRI of another term, all the axioms are merged to one term.
Don't forget replaced_by and alt_id tags.


### SAVING and COMMITTING
---------------

Save and commit regularly. Always describe the changes you have made at a high level in the commit messages. It is a good idea to do a diff before committing (although the output can be hard to decipher, it can sometimes show you egregious errors, sometimes Protege's fault).

**Important: make sure you save in functional syntax, using the same prefixes as in the source file. This SHOULD be automatic (but Protege sometimes gets it wrong - one reason to do the diff).

**Important: there is currently a bug in Protege that is being investigated (well, there are many). If Protege asks you to name your merged file when you save and gives you no other option, DON'T DO IT. Quit Protege and start over. You will lose your work - another reason to save and commit in small increments.

If there are changes to the file after an SVN update, Protege will ask you to reload. You may wish not to trust the reload and simply reopen Protege.

After a commit, Travis will check your changes to make sure they conform to guidelines and do not introduce any inconsistencies - an email will be sent to the curators list.

You can check on the build here:
[https://travis-ci.org/obophenotype/human-phenotype-ontology](https://travis-ci.org/obophenotype/human-phenotype-ontology)

Check for errors in the report, send an email to curators if you cannot determine what the error is.

## MIREOTING
---------
Sometimes you may wish to reference a class from another ontology in the context of editing HP, and the term may not yet be MIREOT'd. You can currently pull in a new term from GO, Uberon, Chebi, CL, PATO or PR.

1. Identify the class to be included, and copy the URI (for example, look in Ontobee or open file in separate Protege instance and do control U to copy the URI). Note the superclass(es) of the class.

2. Whilst editing HP, change the "Active Ontology" file in the top header to the import file that will house the new class, for example, uberon_import.owl

3. Add a new class under the appropriate superclass in the import file, change the URI by doing control U and pasting the URI as per above. Make sure to add the label as an annotation so that you can find the class later.

4. Save the file (note that you should save in RDF/XML with the "use XML entities" checked in the Preferences/Save tab.

5. Do a Diff to make sure you are saving in the proper file format.

6. Advanced editors with Owltools - run "make imports", for example, make imports/uberon_import.owl  in the CL ontology directory. This will pull in the closure and add the metadata.

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
