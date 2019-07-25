## MIREOTING
---------
Sometimes you may wish to reference a class from another ontology in the context of editing CRO, and the term may not yet be MIREOT'd.

1. Identify the class to be included, and copy the URI (for example, look in Ontobee or open file in separate Protege instance and do control U to copy the URI). Note the superclass(es) of the class.

2. Whilst editing CRO, change the "Active Ontology" file in the top header to the import file that will house the new class, for example, credit.owl

3. Add a new class under the appropriate superclass in the import file, change the URI by doing control U and pasting the URI as per above. Make sure to add the label as an annotation so that you can find the class later.

4. Save the file (note that you should save in RDF/XML with the "use XML entities" checked in the Preferences/Save tab.

5. Do a Diff to make sure you are saving in the proper file format.

6. Advanced editors with Owltools - run "make imports". This will pull in the closure and add the metadata.

#### Back to [Editors Guide](https://data2health.github.io/contributor-role-ontology/pages/editors.html)
#### Back to [home](https://data2health.github.io/contributor-role-ontology/)
