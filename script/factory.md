# key pooints
- when we have large number of objects of the same supertype
- object creation can be put on a factory class instead of main part
- the logic for creating objects can then be unite in one place instead of being distributed among whole program
- those created objects by factory can then be reused also i.e. factory can act as a sort of of caching as well.
- factory itself can also be reused for new types of objects added to the program.
- abstract factory pattern can create multiple objects at a time meaning we can group certain types of objects based 
on a relation logic and make sure the group of object make sense together.
- factory pattern is implemented in python by using "eval" function 
# usage samples
- those systems that work with data in the database, factory pattern can be used like an ORM (??)
- abs factory pattern: in shooting games (i.e. PUBG), certain types of guns can only have certain types of equipments
 