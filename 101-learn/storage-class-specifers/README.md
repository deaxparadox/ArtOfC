The storage class specifiers are:

- auto
- regiter
- statis
- extern
- typedef


The *auto* and *register* specifiers give the declared objects automatic storage class, and many be used only within functions. Such declarations also serve as definitions and cause storage to be reserved.

A *register* declaration is equivalent to an auto declaration, but hints that the declared objects will be accessed frequently. Only a few objects are actually plac