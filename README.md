**1.TypeScript interface vs type**

TypeScript makes our code stronger, cleaner and helps with type-dependency. In typeScript, two different ways to define a type are interface and type. Most of time newcomers get confused between interface and type. Lets see the difference between interface and type.

First lets talk about what is interface and type. Interface mainly used to describe te structure of an object. On the other hand, type is used to define type of alias or type is type alias like we can define type with a new name.

_interface_
interface X {
  name: string
  age: number
}

_type_
type Y = {
  name: string;
  age: number;
};

* Extending
we can easily extend interface but we can not extend type.
ex:
interface X {
  name: string;
}
interface Y extends X {
  age: number;
}
other hand we can not extend type. but we can intersect type with other type.lets see: 
type X = {
  name: string
}
type Y = X & {
  age: number;
};

* syntax
we can declare both of object with interface and type.
interface X {
  name: string;
}
type Y = {
  name: string;
};

* Declaration 
if we declare with interface more then once typeScript automatically marge 
interface User {
  name: string;
}
interface User {
  dob: number;
}
but we can't do in type 
type User = {
  name: string;
}
type User = {
  dob: number;
}

Now lets we when we should use interface and type.
interface: object related, declaration marge
type: type alias like: (type, tuple, union) , intersection



**3.TypeScript: The difference between any,unknown,never**

In typeScript using type system makes our code safer trusty. In typeScript wex can see three types any, unknown, never. Lets find out the difference between them.

Lets talk about _any_. Everything is allowed in any thats why we can't see type check thats why we can't see the error of type. Any makes easy to write but its not safe because compiler doesn't check the type or provide no warnings.


_unknown_ atc like i don't know the type yet but i wnt to be safe. Its better then any and ist alternative use of any. We can assign any type to unknown. But we need to check type before it use . we can use it when we work with API and when we don't know the type of data but we want to safer spot.

_never_ atc like never will happen. Never return nothing when function throw error.

conclusion: any is just risky. unknown is safer but need to extra check. Never just like never but its for advanced typing, especially within functions or conditions.
Never use for error throw, infinity loop I think never for advance typing.
