<span style="color:red"><B>Work in Progress</B></span>
<br>
# Concerning JSON

By [Patrik Ackell](https://iot-dude.github.io/)

## Serialization and Unserialization
JSON (JavaScript Object Notation) is a way of formatting data so that it can be shared between different computer systems. 
The idea is that you might have a data structure in one application, and you want to be able to send that data structure to another application. 
<br>
In order to send a data structure to another application, three things are needed: 
1. a common format that both applications understand (like JSON)
2. a way to take an in-memory data structure on the source machine and convert it to that format---this is called "serialization"
3. a way to change the "serialized" data back into an in-memory data structure on the target machine.

Python has a library called `json` that does the work in 2 and 3 for us. The json library has two important functions: 
1. `dumps` ("dump string"), which converts a Python data structure to JSON
2. `loads` ("load string") which converts a JSON string to a Python data structure. Here's an example:


<br>
<br>

import json

rat = {"name": "ruth", "length": 26.5, "favorite_food": "cheddar", "age": 2}
<br>
rat_json = json.dumps(rat)
<br>
type(rat_json)



v0.4
