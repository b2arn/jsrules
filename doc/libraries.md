## Introduce library whenever you can

Any project must contain only the things strictly specific to this project.
Any other things must be moved into separated library project.

As a result, you will have:

* Compact and clear main project
* Libraries you can reuse in further projects
* Loose coupling between code parts

Also, this way you are reducing complexity, hiding it within libraries.

The rule must be applied to each library as well.
Library is a project itself and must contain only things strictly specific to itself.
