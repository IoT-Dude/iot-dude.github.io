# The Corpora Project - a miscellaneous resource for generating JSON data 
Fun Experimental Generative Text Projects with JSON (No AI)
By [Patrik Ackell](https://iot-dude.github.io/)



### <i>"I love to daydream. I was floating down the Barking in a boat with my friend the dog."</i>




In this project I will use JSON files to randomly create a group of interesting characters for an animated mock film




## The Corpora Project - a miscellaneous resource for generating JSON data 

JSON data is often made available as files with a `.json` extension. 

A source for fun data (in JSON format) that I am using in this project is Darius Kazemi's [Corpora project](https://github.com/dariusk/corpora/), which makes available an eclectic collection of <i>"static corpora (plural of 'corpus') that are potentially useful in the creation of weird internet stuff."</i>


The project is a collection of static corpora (plural of "corpus") - in this case is to a collection of adjectives.
In his project Darius Kazemi would like this to help with rapid prototyping of projects: <i>"for example: you might use nouns.json to start with, just to see if an idea you had was any good. Once you've built the project quickly around the nouns collection, you can then rip it out and replace it with a more complex or exhaustive data source."</i>


For example, there is [a list of common English nouns](https://github.com/dariusk/corpora/blob/master/data/words/nouns.json), [a list of color names with corresponding RGB values](https://github.com/dariusk/corpora/blob/master/data/colors/xkcd.json), and even [a list of guitar manufacturers](https://github.com/dariusk/corpora/blob/master/data/music/a_list_of_guitar_manufacturers.json).

These files are a good source for making experimental generative text projects. The simplest way to use one in your notebook is to download it from Github and put it in the same directory as the notebook file. To download one of the files, navigate to it in the repository (click on the `data` directory and navigate through the categories until you find something that looks interesting), then click on the button that reads "Raw." This will show the JSON data directly in your browser, without the surrounding formatting of the Github web page. Then use your browser to save the file (usually `File > Save Page As...`). Save the file in the same directory as your notebook. You should see it pop up in Jupyter Notebook's `Home` tab.


### Project: A Random Ensemble of Actors Made up by Animals



Using JSON files to randomly cast a group of interesting characters for an animated mock film


As a example, I am going to randomly create a group of interesting characters one can use for an animated film (Think Pixars next blockbuster - or something in that line of thought).
<br>
With [this list of common animals](https://github.com/dariusk/corpora/blob/master/data/animals/common.json), downloaded as `common.json` in to the same directory as this notebook.
<br>
To "deserialize" it into a Python data structure, I will use the `open()` function and the `loads()` function from the `json`.


```python
pixar_animal_data = json.loads(open("common.json").read())
```

Here's what the resulting data structure looks like:


```python
pixar_animal_data
```




    {'description': 'A list of common types of animals',
     'animals': ['aardvark',
      'alligator',
      'alpaca',
      'antelope',
      'ape',
      'armadillo',
      'baboon',
      'badger',
      'bat',
      'bear',
      'beaver',
      'bison',
      'boar',
      'buffalo',
      'bull',
      'camel',
      'canary',
      'capybara',
      'cat',
      'chameleon',
      'cheetah',
      'chimpanzee',
      'chinchilla',
      'chipmunk',
      'cougar',
      'cow',
      'coyote',
      'crocodile',
      'crow',
      'deer',
      'dingo',
      'dog',
      'donkey',
      'dromedary',
      'elephant',
      'elk',
      'ewe',
      'ferret',
      'finch',
      'fish',
      'fox',
      'frog',
      'gazelle',
      'gila monster',
      'giraffe',
      'gnu',
      'goat',
      'gopher',
      'gorilla',
      'grizzly bear',
      'ground hog',
      'guinea pig',
      'hamster',
      'hedgehog',
      'hippopotamus',
      'hog',
      'horse',
      'hyena',
      'ibex',
      'iguana',
      'impala',
      'jackal',
      'jaguar',
      'kangaroo',
      'koala',
      'lamb',
      'lemur',
      'leopard',
      'lion',
      'lizard',
      'llama',
      'lynx',
      'mandrill',
      'marmoset',
      'mink',
      'mole',
      'mongoose',
      'monkey',
      'moose',
      'mountain goat',
      'mouse',
      'mule',
      'muskrat',
      'mustang',
      'mynah bird',
      'newt',
      'ocelot',
      'opossum',
      'orangutan',
      'oryx',
      'otter',
      'ox',
      'panda',
      'panther',
      'parakeet',
      'parrot',
      'pig',
      'platypus',
      'polar bear',
      'porcupine',
      'porpoise',
      'prairie dog',
      'puma',
      'rabbit',
      'raccoon',
      'ram',
      'rat',
      'reindeer',
      'reptile',
      'rhinoceros',
      'salamander',
      'seal',
      'sheep',
      'shrew',
      'silver fox',
      'skunk',
      'sloth',
      'snake',
      'squirrel',
      'tapir',
      'tiger',
      'toad',
      'turtle',
      'walrus',
      'warthog',
      'weasel',
      'whale',
      'wildcat',
      'wolf',
      'wolverine',
      'wombat',
      'woodchuck',
      'yak',
      'zebra']}



Something to know about the Corpora Project (and a lot of JSON data in general, really) is that there's no standard way of arranging the data. In order to work with this data, you'll have to look at the data structure and figure out how to write expressions that access the data you want. In this case, the `animal_data` value is a dictionary:


```python
type(pixar_animal_data)
```




    dict



That dictionary has a single key, `animals`, whose value is a list of strings:


```python
pixar_animal_data['animals']
```




    ['aardvark',
     'alligator',
     'alpaca',
     'antelope',
     'ape',
     'armadillo',
     'baboon',
     'badger',
     'bat',
     'bear',
     'beaver',
     'bison',
     'boar',
     'buffalo',
     'bull',
     'camel',
     'canary',
     'capybara',
     'cat',
     'chameleon',
     'cheetah',
     'chimpanzee',
     'chinchilla',
     'chipmunk',
     'cougar',
     'cow',
     'coyote',
     'crocodile',
     'crow',
     'deer',
     'dingo',
     'dog',
     'donkey',
     'dromedary',
     'elephant',
     'elk',
     'ewe',
     'ferret',
     'finch',
     'fish',
     'fox',
     'frog',
     'gazelle',
     'gila monster',
     'giraffe',
     'gnu',
     'goat',
     'gopher',
     'gorilla',
     'grizzly bear',
     'ground hog',
     'guinea pig',
     'hamster',
     'hedgehog',
     'hippopotamus',
     'hog',
     'horse',
     'hyena',
     'ibex',
     'iguana',
     'impala',
     'jackal',
     'jaguar',
     'kangaroo',
     'koala',
     'lamb',
     'lemur',
     'leopard',
     'lion',
     'lizard',
     'llama',
     'lynx',
     'mandrill',
     'marmoset',
     'mink',
     'mole',
     'mongoose',
     'monkey',
     'moose',
     'mountain goat',
     'mouse',
     'mule',
     'muskrat',
     'mustang',
     'mynah bird',
     'newt',
     'ocelot',
     'opossum',
     'orangutan',
     'oryx',
     'otter',
     'ox',
     'panda',
     'panther',
     'parakeet',
     'parrot',
     'pig',
     'platypus',
     'polar bear',
     'porcupine',
     'porpoise',
     'prairie dog',
     'puma',
     'rabbit',
     'raccoon',
     'ram',
     'rat',
     'reindeer',
     'reptile',
     'rhinoceros',
     'salamander',
     'seal',
     'sheep',
     'shrew',
     'silver fox',
     'skunk',
     'sloth',
     'snake',
     'squirrel',
     'tapir',
     'tiger',
     'toad',
     'turtle',
     'walrus',
     'warthog',
     'weasel',
     'whale',
     'wildcat',
     'wolf',
     'wolverine',
     'wombat',
     'woodchuck',
     'yak',
     'zebra']



I'm just going to assign that list to a separate variable, so it's a little easier to work with:


```python
animals = pixar_animal_data['animals']
```

So, lets create a cast list of this next animated film from our favourite maker of animated films by selecting a random subset of these characters:


```python
import random
my_film = random.sample(animals, 10)
print("Cast (In this animated film we have the following characters):")
for item in my_film:
    print("* " + item)
```

    Cast (In this animated film we have the following characters):
    * lynx
    * salamander
    * sheep
    * lizard
    * seal
    * ocelot
    * baboon
    * porpoise
    * llama
    * crow


Let's add some personality to our band using [this list of moods](https://github.com/dariusk/corpora/blob/master/data/humans/moods.json). After having downloaded the raw JSON, you can grab the list of moods from the file like so:


```python
mood_data = json.loads(open("moods.json").read())
moods = mood_data["moods"]
```

Now let's generate a new text combining the two:


```python
print("Current characters in the film is")
print("------------------")
for i in range(10):
    print("The " + random.choice(animals) + " is " + random.choice(moods))
```

    Current characters in the film is
    ------------------
    The guinea pig is mocking
    The mustang is powerless
    The ape is uncanny
    The frog is self-assured
    The toad is persecuted
    The armadillo is recognized
    The bull is hospitable
    The muskrat is reflective
    The lizard is enthusiastic
    The rhinoceros is up






v0.6
