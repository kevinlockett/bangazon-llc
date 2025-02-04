# Classes

## Setup

```sh
mkdir -p ~/workspace/python/exercises/petting_zoo && cd $_
touch animals.py
```

## Why are you Learning This?

You are learning about the syntax and usage of classes because when you extract data from a relational database later in the course, each row of data represents the state of certain things, such as a student, a building, a book, or any other real-world object that you want to store data about.

Classes let you define your own, custom type in Python. The current types that you know about are `list`, `dict`, and `set`. These data structure types are very limiting when you need to represent a complex object in code, though.

## Introduction to Classes

Much like Javascript, almost everything in Python is based on objects. The ability to create objects in a predictable, organized way is essential. This is where classes come into play.

A class is like an object constructor, or a blueprint for creating objects. It helps us define the representation of something from the real world, in code. That 'something' is defined by its values and behaviors (properties).

Once a class is defined, you can use it to crank out objects based on the class. We call those objects _instances_ of the class.

![visualization of two instances of the Student class](./images/python-class-instances.png)

To define a class, such as **`Student`**, above, you begin with the keyword `class` and then define at least an `__init__` method for the class. The `__init__` method holds the instructions for what to do when a developer makes an instance of your class.
Below that are examples of objects being created as instances of **`Student`**. So, `fletcher` and `red` each hold the value of an object, each of which contains properties defined in the class, but each with their own unique values.

## Helping Bobby

To help Bobby with his petting zoo, you know you're going to need to represent animals in his petting zoo with code. Each animal will have properties such as name, species, and year it was added to the zoo.

Here's how you could define a template for how each animal will be represented in the application. Open the `animal.py` module and add the following code.

```py
# import the python datetime module to help us create a timestamp
from datetime import date

class Llama:

    def __init__(self):
        # Establish the properties of each animal
        # with a default value
        self.name = ""
        self.species = ""
        self.date_added = date.today()
```
Remember, this class is not a llama itself. It's just a mechanism for creating llama objects. To create an instance of the class, you type the name of the class and put parenthesis after it. You should always store the object instance in a variable.

Right after the class definition in `animals.py`, create a new instance of a llama.

```py
miss_fuzz = Llama()
```

For any class, when you create an instance of it, it executes an internal `__init__` method. In this method, one common thing to do is to define properties that every instance of the class will contain. Time to examine what the value of each of our llama's properties are.

> **Tip:** What's up with that _self_ parameter that is the first argument of the `__init__` method? It's the instance of the class that you created.

Update the object by defining the values for the name and species properties.

```py
miss_fuzz.name = "Miss Fuzz"
miss_fuzz.species = "domestic llama"
```

Now looping over the `miss_fuzz` object would produce the following output.

```py
name:
Miss Fuzz

species:
domestic llama

date_added: "2020-06-16"
```
That's a good start, but animals -- in the real world and in our system -- also have some properties that help differentiate them from each other. For example, to us it's clear that a cottonmouth snake is quite different from a miniature goat. But without baking that distinction into our class definitions, our system can't recognize that difference. With that in mind, we can also give our critters additional properties that are not common across every class in the system.

For example, Bobby's critters can be divided into three fairly distinct groups by how they move around their home: walking, slithering, and swimming. So, the **`Llama`** class could benefit from adding `self.walking = True` to it. And a **`KingSnake`** class would have `self.slithering = True` in its `__init__` method. Something tells you those distinctions might come in very handy for Bobby as his business grows...

> "Hello? Hey there, hello?"
>
> You snap out of your reverie, and realize you zoned out thinking about class syntax in Python. "Sorry", you say. "I was just...uh...already picturing how to build your app."
>
> Bobby smiles his infectious grin. "Oh, I understand completely. I could dream about pot-bellied pigs and pan tumaca all day, myself!"
>
> After a thorough hand-washing and a bite of cheese sampler, on the house, you head back to the office to get started

## Practice: Classy Critters Collection

You're going to create 15 classes for representing critters from Bobby's petting zoo in Python. (_Seriously -- 15. Hey, we saw that. Don't roll your eyes at us!_).

You will create all of these classes at the beginning of your `animals.py` module.

As shown earlier, define every class with the following properties in the `__init__` method so that each instance can have its own specific values for those properties:

+ name
+ species
+ date_added

But you should also take into consideration the fact that there are different categories of animals at Critters and Croquettes. Specifically, there are critters in the following areas.

1. the petting area, such as donkeys, llamas, and goats
2. the glass tank, like copperheads and rat snakes
3. the pond, like mallards and goldfish

With that in mind, designate 5 critter each to go in these areas. As you define each one, give it one of the following properties where most appropriate:

+ `self.swimming = True` - These animals are in the tank
+ `self.slithering = True` - These animals are in the pond
+ `self.walking = True` - These animals are in the petting area

Once your classes are defined, make at least one instance of each of them. Now you'll have 15-plus objects created. Eventually, those objects might be stored in a database or sent to a browser to be viewed as HTML. For now, though, you're not worried about how this data will be represented. You just want to get the logic working correctly. So, use the `print()` method to see your results.

```py
print(miss_fuzz)
```

It will be...disappointing. You should see something like this:

`<__main__.Llama object at 0x109df9cd0>`

What the heck is that? Your instructors will explain this in more detail, and will eventually show you a trick for getting a more human-readable output. For now, just note that you can't log out a Python object the way you could a Javascript object, and try `print(miss_fuzz.name)` as a temporary solution.

