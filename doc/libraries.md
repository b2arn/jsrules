## Introduce library whenever you can

* Any project must contain only the things strictly specific to this project
* Any other things must be moved into separated library project

This gives you the following:

* Compact and clear main project
* Libraries you can reuse in further projects
* Loose coupling between code parts

This helps you to reduce the complexity, hiding it within libraries.

Note that this rule must be applied to each library also, because any library is a project itself and must contain only things strictly specific to it with moving all other things to other libraries.
