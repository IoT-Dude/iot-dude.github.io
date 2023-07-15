# JSON files with more sophisticated data structures

Fun Experimental Generative Text Projects with JSON (No AI)
By [Patrik Ackell](https://iot-dude.github.io/)

<br>

### <i>"I love to daydream. I was floating down the Barking in a boat with my friend the dog."</i>

<br>
In this project I will use JSON files to randomly create announcements in London underground stations from the tube driver






### More sophisticated data structures

Not all JSON files have the same structure. Some of the files in the Corpora Project in particular aren't just dictionaries that have a list of strings. Let's say that we want to write a small random narratives about the London underground train stations. Start with [this list of london underground stations](https://github.com/dariusk/corpora/blob/master/data/geography/london_underground_stations.json).


<b>So here is what the data looks like:</b>


#https://github.com/dariusk/corpora/blob/master/data/geography/london_underground_stations.json

"description": "London Underground stations, with their lines and Travelcard zones",
  "source": "https://en.wikipedia.org/wiki/List_of_London_Underground_stations",
  "stations": [
    {
      "name": "Acton Town",
      "lines": ["District", "Piccadilly"],
      "zones": [3]
    },
    {
      "name": "Aldgate",
      "lines": ["Metropolitan", "Circle"],
      "zones": [1]
    },
    {
      "name": "Aldgate East",
      "lines": ["Hammersmith & City", "District"],
      "zones": [1]
    },
    {
      "name": "Alperton",
      "lines": ["Piccadilly"],
      "zones": [4]
    },
    {
      "name": "Amersham",
      "lines": ["Metropolitan"],
      "zones": [9]
    },
    {
      "name": "Angel",
      "lines": ["Northern"],
      "zones": [1]
    },
    {
      "name": "Archway",
      "lines": ["Northern"],
      "zones": [2, 3]
    },
    {
      "name": "Arnos Grove",
      "lines": ["Piccadilly"],
      "zones": [4]
    },
    {
      "name": "Arsenal",
      "lines": ["Piccadilly"],
      "zones": [2]
    },
    {
      "name": "Baker Street",
      "lines": ["Metropolitan", "Bakerloo", "Circle", "Jubilee", "Hammersmith & City"],
      "zones": [1]
    },    

    
    
    ... etc ...
    
    


### What value does it have?
Take a look below at this data and try to characterize how it's structured. The entire thing is a dictionary; there's a `description` key and a `source` key which aren't of tremendous interest to us. The value for the `stations` key is where most of the useful information resides.

Let's take a look at that value for `stations`: it's a list! 
<br>
And each element of the list is *itself* a dictionary. 
Let's load the data and put our theory to the test:


```python
#london_underground_stations.json
london_underground_stations_data = json.loads(open("london_underground_stations.json").read())
station_name = london_underground_stations_data["stations"]
type(station_name)
```




    list



Okay, so we have the list of london_underground_stations. Here's the first item in the list, and hopefully it is representative of the rest of the items in the list:


```python
station_name[0]
```




    {'name': 'Acton Town', 'lines': ['District', 'Piccadilly'], 'zones': [3]}



To get the `name` key for <b>this</b> london underground station dictionary key:


```python
station_name[0]['name']
```




    'Acton Town'



To get a list of *just* the station names, write a list comprehension that grabs just the `name` key of each dictionary in the list:


```python
only_the_station_names = [item['name'] for item in station_name]
```


```python
only_the_station_names
```




    ['Acton Town',
     'Aldgate',
     'Aldgate East',
     'Alperton',
     'Amersham',
     'Angel',
     'Archway',
     'Arnos Grove',
     'Arsenal',
     'Baker Street',
     'Balham',
     'Bank',
     'Barbican',
     'Barking',
     'Barkingside',
     'Barons Court',
     'Bayswater',
     'Becontree',
     'Belsize Park',
     'Bermondsey',
     'Bethnal Green',
     'Blackfriars',
     'Blackhorse Road',
     'Bond Street',
     'Borough',
     'Boston Manor',
     'Bounds Green',
     'Bow Road',
     'Brent Cross',
     'Brixton',
     'Bromley-by-Bow',
     'Buckhurst Hill',
     'Burnt Oak',
     'Caledonian Road',
     'Camden Town',s   what  call out
     'Canada Water',
     'Canary Wharf',
     'Canning Town',
     'Cannon Street',
     'Canons Park',
     'Chalfont & Latimer',
     'Chalk Farm',
     'Chancery Lane',
     'Charing Cross',
     'Chesham',
     'Chigwell',
     'Chiswick Park',
     'Chorleywood',
     'Clapham Common',
     'Clapham North',
     'Clapham South',
     'Cockfosters',
     'Colindale',
     'Colliers Wood',
     'Covent Garden',
     'Croxley',
     'Dagenham East',
     'Dagenham Heathway',
     'Debden',
     'Dollis Hill',
     'Ealing Broadway',
     'Ealing Common',
     "Earl's Court",
     'East Acton',
     'East Finchley',
     'East Ham',
     'East Putney',
     'Eastcote',
     'Edgware',
     'Edgware Road',
     'Edgware Road',
     'Elephant & Castle',
     'Elm Park',
     'Embankment',
     'Epping',
     'Euston',
     'Euston Square',
     'Fairlop',
     'Farringdon',
     'Finchley Central',
     'Finchley Road',
     'Finsbury Park',
     'Fulham Broadway',
     'Gants Hill',
     'Gloucester Road',
     'Golders Green',
     'Goldhawk Road',
     'Goodge Street',
     'Grange Hill',
     'Great Portland Street',
     'Greenford',
     'Green Park',
     'Gunnersbury',
     'Hainault',
     'Hammersmith',
     'Hammersmith',
     'Hampstead',
     'Hanger Lane',
     'Harlesden',
     'Harrow & Wealdstone',
     'Harrow-on-the-Hill',
     'Hatton Cross',
     'Heathrow Terminals 1, 2, 3',
     'Heathrow Terminal 4',
     'Heathrow Terminal 5',
     'Hendon Central',
     'High Barnet',
     'Highbury & Islington',
     'Highgate',
     'High Street Kensington',
     'Hillingdon',
     'Holborn',
     'Holland Park',
     'Holloway Road',
     'Hornchurch',
     'Hounslow Central',
     'Hounslow East',
     'Hounslow West',
     'Hyde Park Corner',
     'Ickenham',
     'Kennington',
     'Kensal Green',
     'Kensington (Olympia)',
     'Kentish Town',
     'Kenton',
     'Kew Gardens',
     'Kilburn',
     'Kilburn Park',
     'Kingsbury',
     "King's Cross St. Pancras",
     'Knightsbridge',
     'Ladbroke Grove',
     'Lambeth North',
     'Lancaster Gate',
     'Latimer Road',
     'Leicester Square',
     'Leyton',
     'Leytonstone',
     'Liverpool Street',
     'London Bridge',
     'Loughton',
     ' Maida Vale',
     'Manor House',
     'Mansion House',
     'Marble Arch',
     'Marylebone',
     'Mile End',
     'Mill Hill East',
     'Monument',
     'Moorgate',
     'Moor Park',
     'Morden',
     'Mornington Crescent',
     'Neasden',
     'Newbury Park',
     'North Acton',
     'North Ealing',
     'North Greenwich',
     'North Harrow',
     'North Wembley',
     'Northfields',
     'Northolt',
     'Northwick Park',
     'Northwood',
     'Northwood Hills',
     'Notting Hill Gate',
     'Oakwood',
     'Old Street',
     'Osterley',
     'Oval',
     'Oxford Circus',
     'Paddington',
     'Park Royal',
     'Parsons Green',
     'Perivale',
     'Piccadilly Circus',
     'Pimlico',
     'Pinner',
     'Plaistow',
     'Preston Road',
     'Putney Bridge',
     "Queen's Park",
     'Queensbury',
     'Queensway',
     'Ravenscourt Park',
     'Rayners Lane',
     'Redbridge',
     "Regent's Park",
     'Richmond',
     'Rickmansworth',
     'Roding Valley',
     'Royal Oak',
     'Ruislip',
     'Ruislip Gardens',
     'Ruislip Manor',
     'Russell Square',
     "St. James's Park",
     "St. John's Wood",
     "St. Paul's",
     'Seven Sisters',
     "Shepherd's Bush",
     "Shepherd's Bush Market",
     'Sloane Square',
     'Snaresbrook',
     'South Ealing',
     'South Harrow',
     'South Kensington',
     'South Kenton',
     'South Ruislip',
     'South Wimbledon',
     'South Woodford',
     'Southfields',
     'Southgate',
     'Southwark',
     'Stamford Brook',
     'Stanmore',
     'Stepney Green',
     'Stockwell',
     'Stonebridge Park',
     'Stratford',
     'Sudbury Hill',
     'Sudbury Town',
     'Swiss Cottage',
     'Temple',
     'Theydon Bois',
     'Tooting Bec',
     'Tooting Broadway',
     'Tottenham Court Road',
     'Tottenham Hale',
     'Totteridge & Whetstone',
     'Tower Hill',
     'Tufnell Park',
     'Turnham Green',
     'Turnpike Lane',
     'Upminster',
     'Upminster Bridge',
     'Upney',
     'Upton Park',
     'Uxbridge',
     'Vauxhall',
     'Victoria',
     'Walthamstow Central',
     'Wanstead',
     'Warren Street',
     'Warwick Avenue',
     'Waterloo',
     'Watford',
     'Wembley Central',
     'Wembley Park',
     'West Acton',
     'West Brompton',
     'West Finchley',
     'West Ham',
     'West Hampstead',
     'West Harrow',
     'West Kensington',
     'West Ruislip',
     'Westbourne Park',
     'Westminster',
     'White City',
     'Whitechapel',
     'Willesden Green',
     'Willesden Junction',
     'Wimbledon',
     'Wimbledon Park',
     'Wood Green',
     'Wood Lane',
     'Woodford',
     'Woodside Park']








v0.3
