# TOPIC
JAVASCRIPT PROTOTYPE POLLUTION

# UNDERSTANDING

- In javascript, an object could be created using direct assignment.
- These objects could conatins primitive data types, or even functions.
- When these are assigned to the objects like :
```	person1.fullName = "Ragul";
	person1.age = 12;
	person1.details = function(){
	
	return this.fullName + " the age : " + this.age + "!!!" ;
	
}
```

- Now, when a new object is created and we need to add the same function, on those too ! Then, we have to manually add all
these again.
- Therefore, we can use PROTOTYPE functions.

## SYNTAX :
```
	person.prototype.details = function(){
	return this.Fullname + " the age : " + this.age;
}
```

- Now when person1 is called, and when ``` person1.details```
is executed, the details function from the initial function is executed.
- But, when a new person "person2" is created, and when ```person2.details```
is executed, the details function from a new object called ```__proto__```
is exectued.

## __PROTO__ function :
- When a new object is created, the function "details" is added to the prototype parameter, as it is defined in the 
"person.prototype.details = fun..."

There fore a newly created object would have the following properties, after adding the fullname and age.
personx = {fullName : "x", age: "0", __proto__: ""}

When the "details" function is called, it searches in the first level [ firstName, age, __proto__ ]. If not found there,
then it searches inside the __proto__, and returns the value.

This is called protochaining.

## OVERVIEW

-  In the first example, person1 has manual declaration of the details function. SO their object would look like
[FirstName, age, details, __proto__]
- The second newly created object, after adding FullName and age would look like, [FIrstName, age, __proto__], since
the details could not be found in this layer, the compiler opens the "__proto__", and finds the details there defined 
by the __proto__, and executes.

# JS PROTOTYPE POLLUTION
- The problem arises, when the __proto__ option is opened, and again the __proto__ attribute is opened, and done recursively, 
utill the top of the proto chain is reached.

 - Now adding a new attribute there on top of the proto chain, would declare the new attribute universally to all the objects.
Now any object created, would have that property in it.

THis is called PROTOTYPE POLLUTION.

# EXPLOIT

pass a "__proto__" as an object, adn you could inject key value pairs in the JSON object used for updating.
This would create a new object, and this proto would allow, the key value pair to sit in the top of the proto chian, thus
any new object would have the key value pair, in it.

like :
```
PUT /update HTTP/1.1
.
.
.
{
	"NAME" : "MAGMA",
	"AGE" : 25,
	"__proto__" : {
		"isAdmin": true
	}
}
```

This is called protoype pollution.
This addition of proto does not overwrite the existing one, but if the application uses a merge function to merge
the newly created objects, with the old one then this proto object also would get copied thus polluting it.

# REFERENCES
https://www.youtube.com/playlist?list=PL1YqgxjG5ke8wegThVFC8CaXuXbkiZxtX
