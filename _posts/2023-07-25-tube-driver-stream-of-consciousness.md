
# The tube driver stream of consciousness



Fun Experimental Generative Text Projects with JSON (No AI)
<br>
By [Patrik Ackell](https://iot-dude.github.io/)
<br>
<br>
### <i>"I love to daydream. I was floating down the Barking in a boat with my friend the dog."</i>
<br>
<br>

In this project I will use JSON files to randomly create a tube driver stream of consciousnessa while driving around in the London Underground





### The tube driver
Far out!
<br>
This is a random stream of conscience flow by a London Underground tube driver - a combination of two JSON files to create a 
experimental generative text, proclaimed by someone operating a london underground tube carriage

Quote: <i>"I love to daydream. I was floating down the Barking in a boat with my friend the dog."</i>



```python
#personality_test.json
#
# Create personaly treaties that will be uttered.
#personality_test_data = json.loads(open("personality_test.json").read())
# Test.
#personality_test_data

#utterings_out.
#
personality_test_data = json.loads(open("personality_test.json").read())
utterings_out = personality_test_data["personality_test"]
random_utterings_out = random.choice(utterings_out)
# Test.
#random_utterings_out
```


```python
call_out_station_name = random.choice(only_the_station_names)
call_out_utterings_out = random.choice(utterings_out)
animal1 = random.choice(animals)

print(call_out_utterings_out + "\nI was floating down the " + call_out_station_name +  " in a boat with my friend the "  + animal1 +".")
```

    I believe that people are essentially evil.
    I was floating down the Shepherd's Bush Market in a boat with my friend the zebra.











v0.21
