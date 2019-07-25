## OBSOLETING

1. If one class should be merged with another class, first obsolete the class that will be merged.
2. Search for the class to be obsoleted
3. Rename label to: obsolete [class name]
4. Add annotation owl:deprecated and indicated true (in literal)
5. Add annotation term replaced by and add ID of term which replaced it (in CURIE format, such as CRO:0000004).
6. Remove superclass axioms
7. If the class has children, remove the superclass assertion for the children
8. Search for the replacement term
9. Add annotation database_cross_reference and add the term ID Annotate the database_cross_reference annotation with source 
10. Move all the synonyms to the new term.
11. Save and commit

#### Back to [Editors Guide](https://data2health.github.io/contributor-role-ontology/pages/editors.html)
#### Back to [home](https://data2health.github.io/contributor-role-ontology/)
