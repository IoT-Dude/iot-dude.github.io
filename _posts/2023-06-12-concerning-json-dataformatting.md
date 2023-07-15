
# Concerning JSON - formatting, Serialization and Unserialization
Fun Experimental Generative Text Projects with JSON (No AI)
By [Patrik Ackell](https://iot-dude.github.io/)


### <i>"I love to daydream. I was floating down the Barking in a boat with my friend the dog."</i>
<br>

## Data formatting, Serialization and Unserialization of JSON objects
JSON (JavaScript Object Notation) is a way of formatting data so that it can be shared between different computer systems. 
The idea is that you might have a data structure in one application and you want to be able to send that data structure to another application. 
<br>
<br>
In order to send a data structure to another application, three things are needed: 
1. a common format that both applications understand (like JSON)
2. a way to take an in-memory data structure on the source machine and convert it to that format - this is called "serialization"
3. a way to change the "serialized" data back into an in-memory data structure on the target machine.

Python has a library called `json` that does the work in 2 and 3 for us. The json library has two important functions: 
1. `dumps` ("dump string"), which converts a Python data structure to JSON
2. `loads` ("load string") which converts a JSON string to a Python data structure. Here's an example:


```python
import json
```


```python
rat = {"name": "ruth", "length": 26.5, "favorite_food": "cheddar", "age": 2}
rat_json = json.dumps(rat)
type(rat_json)
```




    str




```python
rat_json
```




    '{"name": "ruth", "length": 26.5, "favorite_food": "cheddar", "age": 2}'



### A strong resemblance but not always
The notation for Python objects (the way we write them in our programs) has a strong resemblance to the way that same data looks when encoded as JSON. 
<br>But there are some differences: JSON uses null instead of None, JSON always has double-quoted keys and values and escape sequences in JSON strings are very different from those in Python. 
<br>
With those exceptions for the most part the formatted data look familiar. 
<br>
<br>
The json library can take pretty much any Python data structure and turn it into a JSON object: dictionaries, lists, ints, floats, also even nested data structures, like dictionaries with lists as values.

### JSON encoded data is just a string
The great thing about JSON is that JSON encoded data is just a string. It is possible to copy JSON data into an e-mail and send it to someone without having to worry about formatting, and one could paste it back into Python to get back the original data structure. 
<br>
The same thing can be said about web applications that encodes data structures as JSON and one could read them with another computer program.

<br>
<br>

v0.6
