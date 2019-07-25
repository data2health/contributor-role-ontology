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
[https://travis-ci.org/data2health/contributor-role-ontology](https://travis-ci.org/data2health/contributor-role-ontology)

Check for errors in the report, send an email to curators if you cannot determine what the error is.

#### Back to [Editors Guide](https://data2health.github.io/contributor-role-ontology/pages/editors.html)
#### Back to [home](https://data2health.github.io/contributor-role-ontology/)
