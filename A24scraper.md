```python
# libraries
import pandas as pd
from bs4 import BeautifulSoup as bs
import requests
from requests.adapters import HTTPAdapter
```

## Scraping data


```python
# Scraping of single movie
r = requests.get('https://en.wikipedia.org/wiki/The_Witch_(2015_film)')
```


```python
# Convert to bs object
soup = bs(r.content)

# Print out the HTML 
contents = soup.prettify()

info_box = soup.find(class_ = "infobox vevent")

info_rows = info_box.find_all("tr")

for row in info_rows:
    print(row.prettify())
```

    <tr>
     <th class="infobox-above summary" colspan="2" style="font-size: 125%; font-style: italic;">
      The Witch
     </th>
    </tr>
    
    <tr>
     <td class="infobox-image" colspan="2">
      <a class="image" href="/wiki/File:The_Witch_poster.png">
       <img alt="The Witch poster.png" data-file-height="384" data-file-width="259" decoding="async" height="326" src="//upload.wikimedia.org/wikipedia/en/thumb/b/bf/The_Witch_poster.png/220px-The_Witch_poster.png" srcset="//upload.wikimedia.org/wikipedia/en/b/bf/The_Witch_poster.png 1.5x" width="220"/>
      </a>
      <div class="infobox-caption">
       Theatrical release poster
      </div>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Directed by
     </th>
     <td class="infobox-data">
      <a href="/wiki/Robert_Eggers" title="Robert Eggers">
       Robert Eggers
      </a>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Written by
     </th>
     <td class="infobox-data">
      Robert Eggers
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Produced by
     </th>
     <td class="infobox-data">
      <style data-mw-deduplicate="TemplateStyles:r1126788409">
       .mw-parser-output .plainlist ol,.mw-parser-output .plainlist ul{line-height:inherit;list-style:none;margin:0;padding:0}.mw-parser-output .plainlist ol li,.mw-parser-output .plainlist ul li{margin-bottom:0}
      </style>
      <div class="plainlist">
       <ul>
        <li>
         Jay Van Hoy
        </li>
        <li>
         <a href="/wiki/Lars_Knudsen_(producer)" title="Lars Knudsen (producer)">
          Lars Knudsen
         </a>
        </li>
        <li>
         Jodi Redmond
        </li>
        <li>
         Daniel Bekerman
        </li>
        <li>
         Rodrigo Teixeira
        </li>
       </ul>
      </div>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Starring
     </th>
     <td class="infobox-data">
      <link href="mw-data:TemplateStyles:r1126788409" rel="mw-deduplicated-inline-style"/>
      <div class="plainlist">
       <ul>
        <li>
         <a href="/wiki/Anya_Taylor-Joy" title="Anya Taylor-Joy">
          Anya Taylor-Joy
         </a>
        </li>
        <li>
         <a href="/wiki/Ralph_Ineson" title="Ralph Ineson">
          Ralph Ineson
         </a>
        </li>
        <li>
         <a href="/wiki/Kate_Dickie" title="Kate Dickie">
          Kate Dickie
         </a>
        </li>
        <li>
         Harvey Scrimshaw
        </li>
        <li>
         Ellie Grainger
        </li>
        <li>
         Lucas Dawson
        </li>
       </ul>
      </div>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Cinematography
     </th>
     <td class="infobox-data">
      <a href="/wiki/Jarin_Blaschke" title="Jarin Blaschke">
       Jarin Blaschke
      </a>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Edited by
     </th>
     <td class="infobox-data">
      Louise Ford
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Music by
     </th>
     <td class="infobox-data">
      <a href="/wiki/Mark_Korven" title="Mark Korven">
       Mark Korven
      </a>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      <div style="display: inline-block; line-height: 1.2em; padding: .1em 0;">
       Production
       <br/>
       companies
      </div>
     </th>
     <td class="infobox-data">
      <div style="vertical-align: middle;">
       <link href="mw-data:TemplateStyles:r1126788409" rel="mw-deduplicated-inline-style"/>
       <div class="plainlist">
        <ul>
         <li>
          Parts and Labor
         </li>
         <li>
          RT Features
         </li>
         <li>
          Rooks Nest Entertainment
         </li>
         <li>
          Maiden Voyage Pictures
         </li>
         <li>
          Mott Street Pictures
         </li>
         <li>
          Code Red Productions
         </li>
         <li>
          <a href="/wiki/Scythia_Films" title="Scythia Films">
           Scythia Films
          </a>
         </li>
         <li>
          Pulse Films
         </li>
         <li>
          Special Projects
         </li>
        </ul>
       </div>
      </div>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Distributed by
     </th>
     <td class="infobox-data">
      <link href="mw-data:TemplateStyles:r1126788409" rel="mw-deduplicated-inline-style"/>
      <div class="plainlist">
       <ul>
        <li>
         <a href="/wiki/A24" title="A24">
          A24
         </a>
         (United States)
        </li>
        <li>
         <a href="/wiki/Elevation_Pictures" title="Elevation Pictures">
          Elevation Pictures
         </a>
         (Canada)
        </li>
       </ul>
      </div>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      <div style="display: inline-block; line-height: 1.2em; padding: .1em 0;white-space: normal;">
       Release dates
      </div>
     </th>
     <td class="infobox-data">
      <link href="mw-data:TemplateStyles:r1126788409" rel="mw-deduplicated-inline-style"/>
      <div class="plainlist">
       <ul>
        <li>
         January 27, 2015
         <span style="display:none">
          (
          <span class="bday dtstart published updated">
           2015-01-27
          </span>
          )
         </span>
         (
         <a href="/wiki/2015_Sundance_Film_Festival" title="2015 Sundance Film Festival">
          Sundance
         </a>
         )
        </li>
        <li>
         February 19, 2016
         <span style="display:none">
          (
          <span class="bday dtstart published updated">
           2016-02-19
          </span>
          )
         </span>
         (United States)
        </li>
       </ul>
      </div>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      <div style="display: inline-block; line-height: 1.2em; padding: .1em 0;white-space: normal;">
       Running time
      </div>
     </th>
     <td class="infobox-data">
      92 minutes
      <sup class="reference" id="cite_ref-1">
       <a href="#cite_note-1">
        [1]
       </a>
      </sup>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Countries
     </th>
     <td class="infobox-data">
      <link href="mw-data:TemplateStyles:r1126788409" rel="mw-deduplicated-inline-style"/>
      <div class="plainlist">
       <ul>
        <li>
         United States
         <sup class="reference" id="cite_ref-2">
          <a href="#cite_note-2">
           [2]
          </a>
         </sup>
        </li>
        <li>
         Canada
         <sup class="reference" id="cite_ref-3">
          <a href="#cite_note-3">
           [3]
          </a>
         </sup>
         <sup class="reference" id="cite_ref-4">
          <a href="#cite_note-4">
           [4]
          </a>
         </sup>
        </li>
       </ul>
      </div>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Language
     </th>
     <td class="infobox-data">
      <a href="/wiki/Early_Modern_English" title="Early Modern English">
       Early Modern English
      </a>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Budget
     </th>
     <td class="infobox-data">
      $4 million
      <sup class="reference" id="cite_ref-5">
       <a href="#cite_note-5">
        [5]
       </a>
      </sup>
     </td>
    </tr>
    
    <tr>
     <th class="infobox-label" scope="row" style="white-space: nowrap; padding-right: 0.65em;">
      Box office
     </th>
     <td class="infobox-data">
      $40.4 million
      <sup class="reference" id="cite_ref-BOM_6-0">
       <a href="#cite_note-BOM-6">
        [6]
       </a>
      </sup>
     </td>
    </tr>
    


```python
#import into dictionary
movie_info = {}

# get content function
def get_content_value(row_data):
    if row_data.find("li"):
        return[li.get_text(" ", strip = True).replace("\xa0", " ") for li in row_data.find_all('li')]
    else:
        return row_data.get_text(" ", strip = True).replace("\xa0", " ")

for index, row in enumerate (info_rows):
    if index == 0:
        movie_info['title'] = row.find("th").get_text(" ", strip = True)
    elif index == 1:
        continue
    else:
        content_key = row.find('th').get_text(" ", strip = True)
        content_value = get_content_value(row.find("td"))
        movie_info[content_key] = content_value

movie_info
```




    {'title': 'The Witch',
     'Directed by': 'Robert Eggers',
     'Written by': 'Robert Eggers',
     'Produced by': ['Jay Van Hoy',
      'Lars Knudsen',
      'Jodi Redmond',
      'Daniel Bekerman',
      'Rodrigo Teixeira'],
     'Starring': ['Anya Taylor-Joy',
      'Ralph Ineson',
      'Kate Dickie',
      'Harvey Scrimshaw',
      'Ellie Grainger',
      'Lucas Dawson'],
     'Cinematography': 'Jarin Blaschke',
     'Edited by': 'Louise Ford',
     'Music by': 'Mark Korven',
     'Production companies': ['Parts and Labor',
      'RT Features',
      'Rooks Nest Entertainment',
      'Maiden Voyage Pictures',
      'Mott Street Pictures',
      'Code Red Productions',
      'Scythia Films',
      'Pulse Films',
      'Special Projects'],
     'Distributed by': ['A24 (United States)', 'Elevation Pictures (Canada)'],
     'Release dates': ['January 27, 2015 ( 2015-01-27 ) ( Sundance )',
      'February 19, 2016 ( 2016-02-19 ) (United States)'],
     'Running time': '92 minutes [1]',
     'Countries': ['United States [2]', 'Canada [3] [4]'],
     'Language': 'Early Modern English',
     'Budget': '$4 million [5]',
     'Box office': '$40.4 million [6]'}




```python
# The same for every movie from A24 Studio films list ('https://en.wikipedia.org/wiki/List_of_A24_films')

r = requests.get('https://en.wikipedia.org/wiki/List_of_A24_films')
soup = bs(r.content)

contents = soup.prettify()
```


```python
#get funtions
def get_content_value(row_data):
    if row_data.find("li"):
        return[li.get_text(" ", strip = True).replace("\xa0", " ") for li in row_data.find_all('li')]
    elif row_data.find("br"):
        return [text for text in row_data.stripped_strings]
    else:
        return row_data.get_text(" ", strip = True).replace("\xa0", " ")

def clean_tags(soup):
    for tag in soup.find_all(["sup", "span"]):
        tag.decompose()
        
def get_info_box(url):
    
    r = requests.get(url)
    soup = bs(r.content)
    info_box = soup.find(class_ = "infobox vevent")
    info_rows = info_box.find_all("tr")

    clean_tags(soup)  
        
    movie_info = {}
    for index, row in enumerate (info_rows):
        if index == 0:
            movie_info['title'] = row.find("th").get_text(" ", strip = True)
        else:
            header = row.find('th')
            if header:
                content_key = row.find('th').get_text(" ", strip = True)
                content_value = get_content_value(row.find("td"))
                movie_info[content_key] = content_value
                
    return movie_info

```


```python
#getting list of movies with printing movies with no attributes
try:
    page = requests.get('https://en.wikipedia.org/wiki/List_of_A24_films')
except requests.exceptions.ConnectionError:
    r.status_code = "Connection refused"
soup = bs(r.content)
movies = soup.select('.wikitable.sortable i a')

base_path = 'https://en.wikipedia.org/'

movie_info_list = []
for index, movie in enumerate(movies):

    try:
        relative_path = movie['href']
        full_path = base_path + relative_path
        title = movie['title']
        
        movie_info_list.append(get_info_box(full_path))
        
    except Exception as e:
        print(movie.get_text())
        print(e)
```

    Rolling Stone
    'NoneType' object has no attribute 'find_all'
    Wehrmacht
    'NoneType' object has no attribute 'find_all'
    haenyeo
    'NoneType' object has no attribute 'find_all'
    


```python
len(movie_info_list)
```




    154




```python
#save to json
import json

def save_data(title, data):
    with open(title, 'w', encoding = 'utf-8') as f:
        json.dump(data, f, ensure_ascii = False, indent = 2)
```


```python
import json

def load_data(title):
    with open(title, encoding = 'utf-8') as f:
        return json.load(f)
```


```python
save_data('a24_data.json', movie_info_list)
```

## Cleaning data


```python
movie_info_list = load_data("a24_data.json")
```


```python
# looking on columns formats and what cleaning is necessary
movie_info_list[50]
```




    {'title': 'It Comes at Night',
     'Directed by': 'Trey Edward Shults',
     'Written by': 'Trey Edward Shults',
     'Produced by': ['David Kaplan', 'Andrea Roa'],
     'Starring': ['Joel Edgerton',
      'Christopher Abbott',
      'Carmen Ejogo',
      'Riley Keough',
      'Kelvin Harrison Jr.'],
     'Cinematography': 'Drew Daniels',
     'Edited by': ['Trey Edward Shults', 'Matthew Hannam'],
     'Music by': 'Brian McOmber',
     'Production companies': ['A24', 'Animal Kingdom'],
     'Distributed by': 'A24',
     'Release dates': ['April 29, 2017 ( Overlook Film Festival )',
      'June 9, 2017 (United States)'],
     'Running time': '91 minutes',
     'Country': 'United States',
     'Language': 'English',
     'Budget': '$2.4–5 million',
     'Box office': '$20 million'}



To clean:
- convert running time to int and drop NAs
- convert budget to one format and drop NAs
- convert box office to one format and drop NAs
- clean up references
- convert release dates to datetime



```python
# running time NAs
[movie.get('Running time', 'N/A') for movie in movie_info_list]
```




    ['86 minutes',
     '90 minutes',
     '94 minutes',
     '90 minutes',
     '95 minutes',
     '90 minutes',
     '108 minutes',
     '85 minutes',
     '83 minutes',
     '102 minutes',
     '89 minutes',
     '101 minutes',
     '100 minutes',
     '95 minutes',
     '112 minutes',
     '125 minutes',
     '109 minutes',
     '97 minutes',
     '92 minutes',
     '108 minutes',
     '84 minutes',
     '98 minutes',
     '128 minutes',
     '106 minutes',
     '112 minutes',
     '108 minutes',
     '118 minutes',
     '93 minutes',
     '92 minutes',
     '94 minutes',
     '81 minutes',
     '95 minutes',
     '105 minutes',
     '118 minutes',
     '107 minutes',
     '97 minutes',
     '101 minutes',
     '101 minutes',
     '91 minutes',
     '110 minutes',
     '163 minutes',
     '111 minutes',
     '122 minutes',
     '91 minutes',
     '118 minutes',
     '99 minutes',
     '93 minutes',
     '90 minutes',
     '94 minutes',
     '107 minutes',
     '91 minutes',
     '92 minutes',
     '81 minutes',
     '101 minutes',
     '100 minutes',
     '111 minutes',
     '121 minutes',
     '94 minutes',
     '103 minutes',
     '99 minutes',
     '111 minutes',
     '117 minutes',
     '103 minutes',
     '121 minutes',
     '104 minutes',
     '113 minutes',
     '102 minutes',
     '127 minutes',
     '102 minutes',
     '94 minutes',
     '107 minutes',
     '85 minutes',
     '117 minutes',
     '83 minutes',
     '105 minutes',
     '85 minutes',
     '92 minutes',
     '90 minutes',
     '96 minutes',
     '102 minutes',
     '110 minutes',
     '104 minutes',
     '139 minutes',
     '119 minutes',
     '120 minutes',
     '148 minutes',
     '100 minutes',
     '110 minutes',
     '89 minutes',
     '100 minutes',
     '86 minutes',
     '109 minutes',
     '96 minutes',
     '87 minutes',
     '135 minutes',
     '118 minutes',
     '135 minutes',
     '121 minutes',
     '109 minutes',
     '96 minutes',
     '84 minutes',
     '115 minutes',
     '92 minutes',
     '90 minutes',
     '108 minutes',
     '130 minutes',
     '106 minutes',
     '107 minutes',
     '108 minutes',
     '108 minutes',
     '128 minutes',
     '105 minutes',
     '103 minutes',
     '96 minutes',
     '106 minutes',
     '139 minutes',
     '100 minutes',
     '90 minutes',
     '90 minutes',
     '94 minutes',
     '86 minutes',
     '102 minutes',
     '106 minutes',
     '108 minutes',
     '101 minutes',
     '137 minutes',
     '101 minutes',
     '92 minutes',
     '95 minutes',
     '136 minutes',
     '96 minutes',
     '117 minutes',
     '82 minutes',
     '88 minutes',
     '104 minutes',
     '116 minutes',
     '84 minutes',
     '108 minutes',
     '179 minutes',
     '93 minutes',
     '106 minutes',
     '94 minutes',
     '97 minutes',
     '108 minutes',
     '97 minutes',
     '74 minutes',
     '100 minutes',
     '98 minutes',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A']




```python
# running time into an int
def minutes_to_int(running_time):
    if running_time == "N/A":
        return None
    
    if isinstance(running_time, list):
        entry = running_time[0]
        return int(running_time[0].split(" ")[0])
    
    else:
        return int(running_time.split(" ")[0])

for movie in movie_info_list:
    movie['Running time (int)'] = minutes_to_int(movie.get('Running time', 'N/A'))
```


```python
# Look on budget 
[movie.get('Budget', 'N/A') for movie in movie_info_list]
```




    ['N/A',
     'N/A',
     '$5 million',
     '$8.2 million',
     '$2.5 million',
     'N/A',
     ['£', '8\xa0million', '($13.3\xa0million)'],
     '$2 million',
     '$1 million',
     '12 million',
     '$2.4 million',
     '$3 million',
     'N/A',
     '$5 million',
     'N/A',
     '$20 million',
     'N/A',
     '$10 million',
     '$5 million',
     '$15 million',
     'N/A',
     '$15 million',
     '$3.4 million',
     'N/A',
     '$11.9 million',
     '$7.1 million',
     '$13 million',
     'N/A',
     '$4 million',
     '$9.6 million',
     '$30,000',
     '$5 million',
     'N/A',
     '$ 4 million',
     'N/A',
     '$3 million',
     'N/A',
     '$10,000.',
     'N/A',
     '$25 million',
     '$3.5 million',
     '$1.5 million',
     'N/A',
     '$3 million',
     '$7 million',
     'N/A',
     'N/A',
     '$7 million',
     'N/A',
     'N/A',
     '$2.4–5 million',
     '$100,000',
     'N/A',
     '$2 million',
     '$5 million',
     '$2 million',
     'N/A',
     '$10 million',
     '$10 million',
     '$6 million',
     '$5-8 million',
     'N/A',
     'N/A',
     '$8 million',
     '$8 million',
     '$3.5 million',
     'N/A',
     '$10 million',
     '$5 million',
     '$2 million',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     '$1.7 million',
     'N/A',
     'N/A',
     '$2.9 million',
     'N/A',
     '€8 million',
     'N/A',
     '$8 million',
     'N/A',
     '$3 million',
     '$9 million',
     '$3 million',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     '$11 million',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     '$19 million',
     '$2 million+',
     'N/A',
     'N/A',
     'N/A',
     '$2 million',
     'N/A',
     '$5 million',
     'N/A',
     '$15 million',
     'N/A',
     'N/A',
     '$8.3 million',
     'N/A',
     '$1.1 million',
     'N/A',
     'N/A',
     '$9–20 million',
     '$1 million',
     '$14.3–25 million',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     '$1 million',
     '$1 million',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     '$3 million',
     '$100 million',
     'N/A',
     '$3 million',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     '$134,815',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     'N/A',
     '$20.4 million',
     'N/A',
     'N/A']



Budget issues:
- some N/A's (drop them)
- milion as string (delete milion and number to int)
- ranges (I will take min or avg value)
- "2 milion +" - plus to delete
- one row with '£', '8\xa0million', '($13.3\xa0million)' - just to drop


```python
import re

# regex for format money strings
amounts = r"thousand|million"
number = r"\d+(,\d{3})*\.*\d*"

word_re = rf"\${number}(-|\sto\s|–)?({number})?\s({amounts})"
value_re = rf"\${number}"

#functions to money conversion from strings into flaot
def word_to_value(word):
    value_dict = {"thousand": 1000, "million": 1000000}
    return value_dict[word]

def parse_word_syntax(string):
    value_string = re.search(number, string).group()
    value = float(value_string.replace(",", ""))
    word = re.search(amounts, string, flags=re.I).group().lower()
    word_value = word_to_value(word)
    return value*word_value

def parse_value_syntax(string):
    value_string = re.search(number, string).group()
    value = float(value_string.replace(",", ""))
    return value

def money_conversion(money):
    if money == "N/A":
        return None

    if isinstance(money, list):
        money = money[0]
        
    word_syntax = re.search(word_re, money, flags=re.I)
    value_syntax = re.search(value_re, money)

    if word_syntax:
        return parse_word_syntax(word_syntax.group())

    elif value_syntax:
        return parse_value_syntax(value_syntax.group())

    else:
        return None
```


```python
# New columns: Budget (float) and Box Office (float)
for movie in movie_info_list:
    movie['Budget (float)'] = money_conversion(movie.get('Budget', "N/A"))
    movie['Box office (float)'] = money_conversion(movie.get('Box office', "N/A"))
```


```python
[movie.get('Budget (float)', 'N/A') for movie in movie_info_list]
```




    [None,
     None,
     5000000.0,
     8199999.999999999,
     2500000.0,
     None,
     None,
     2000000.0,
     1000000.0,
     None,
     2400000.0,
     3000000.0,
     None,
     5000000.0,
     None,
     20000000.0,
     None,
     10000000.0,
     5000000.0,
     15000000.0,
     None,
     15000000.0,
     3400000.0,
     None,
     11900000.0,
     7100000.0,
     13000000.0,
     None,
     4000000.0,
     9600000.0,
     30000.0,
     5000000.0,
     None,
     None,
     None,
     3000000.0,
     None,
     10000.0,
     None,
     25000000.0,
     3500000.0,
     1500000.0,
     None,
     3000000.0,
     7000000.0,
     None,
     None,
     7000000.0,
     None,
     None,
     2400000.0,
     100000.0,
     None,
     2000000.0,
     5000000.0,
     2000000.0,
     None,
     10000000.0,
     10000000.0,
     6000000.0,
     5000000.0,
     None,
     None,
     8000000.0,
     8000000.0,
     3500000.0,
     None,
     10000000.0,
     5000000.0,
     2000000.0,
     None,
     None,
     None,
     None,
     None,
     1700000.0,
     None,
     None,
     2900000.0,
     None,
     None,
     None,
     8000000.0,
     None,
     3000000.0,
     9000000.0,
     3000000.0,
     None,
     None,
     None,
     None,
     11000000.0,
     None,
     None,
     None,
     None,
     19000000.0,
     2000000.0,
     None,
     None,
     None,
     2000000.0,
     None,
     5000000.0,
     None,
     15000000.0,
     None,
     None,
     8300000.000000001,
     None,
     1100000.0,
     None,
     None,
     9000000.0,
     1000000.0,
     14300000.0,
     None,
     None,
     None,
     None,
     None,
     1000000.0,
     1000000.0,
     None,
     None,
     None,
     None,
     None,
     3000000.0,
     100000000.0,
     None,
     3000000.0,
     None,
     None,
     None,
     None,
     134815.0,
     None,
     None,
     None,
     None,
     None,
     None,
     None,
     None,
     None,
     None,
     None,
     None,
     None,
     None,
     20400000.0,
     None,
     None]




```python
# Convert dates to datetime

from datetime import datetime

dates = [movie.get('Release dates', 'N/A') for movie in movie_info_list]

def clean_date(date):
    return date.split("(")[0].strip()

def date_conversion(date):
    if isinstance(date, list):
        date = date[0]
        
    if date == "N/A":
        return None
        
    date_str = clean_date(date)
    print(date_str)
    
    fmts = ["%B %d, %Y", "%d %B %Y"]
    for fmt in fmts:
        try:
            return datetime.strptime(date_str, fmt)
        except:
            pass
    return None

for date in dates:
    print(date_conversion(date))
    print()
```

    November 15, 2012
    2012-11-15 00:00:00
    
    7 September 2012
    2012-09-07 00:00:00
    
    September 4, 2012
    2012-09-04 00:00:00
    
    May 16, 2013
    2013-05-16 00:00:00
    
    January 18, 2013
    2013-01-18 00:00:00
    
    8 September 2013
    2013-09-08 00:00:00
    
    29 August 2013
    2013-08-29 00:00:00
    
    2 September 2013
    2013-09-02 00:00:00
    
    January 17, 2014
    2014-01-17 00:00:00
    
    18 May 2014
    2014-05-18 00:00:00
    
    January 19, 2014
    2014-01-19 00:00:00
    
    September 6, 2014
    2014-09-06 00:00:00
    
    January 17, 2014
    2014-01-17 00:00:00
    
    September 10, 2014
    2014-09-10 00:00:00
    
    None
    
    November 6, 2014
    2014-11-06 00:00:00
    
    16 October 2014
    2014-10-16 00:00:00
    
    September 6, 2014
    2014-09-06 00:00:00
    
    June 16, 2014
    2014-06-16 00:00:00
    
    16 December 2014
    2014-12-16 00:00:00
    
    24 January 2015
    2015-01-24 00:00:00
    
    None
    
    
    None
    
    January 23, 2015
    2015-01-23 00:00:00
    
    April 8, 2015
    2015-04-08 00:00:00
    
    January 24, 2015
    2015-01-24 00:00:00
    
    September 4, 2015
    2015-09-04 00:00:00
    
    April 18, 2015
    2015-04-18 00:00:00
    
    January 27, 2015
    2015-01-27 00:00:00
    
    September 10, 2015
    2015-09-10 00:00:00
    
    March 16, 2015
    2015-03-16 00:00:00
    
    May 17, 2015
    2015-05-17 00:00:00
    
    April 16, 2015
    2015-04-16 00:00:00
    
    15 May 2015
    2015-05-15 00:00:00
    
    September 9, 2015
    2015-09-09 00:00:00
    
    January 22, 2016
    2016-01-22 00:00:00
    
    September 5, 2015
    2015-09-05 00:00:00
    
    September 12, 2015
    2015-09-12 00:00:00
    
    January 22, 2016
    2016-01-22 00:00:00
    
    May 16, 2015
    2015-05-16 00:00:00
    
    15 May 2016
    2016-05-15 00:00:00
    
    September 2, 2016
    2016-09-02 00:00:00
    
    None
    
    None
    
    October 8, 2016
    2016-10-08 00:00:00
    
    9 September 2016
    2016-09-09 00:00:00
    
    September 12, 2015
    2015-09-12 00:00:00
    
    8 September 2016
    2016-09-08 00:00:00
    
    April 22, 2017
    2017-04-22 00:00:00
    
    12 September 2016
    2016-09-12 00:00:00
    
    April 29, 2017
    2017-04-29 00:00:00
    
    January 22, 2017
    2017-01-22 00:00:00
    
    January 23, 2017
    2017-01-23 00:00:00
    
    May 25, 2017
    2017-05-25 00:00:00
    
    September 4, 2017
    2017-09-04 00:00:00
    
    May 22, 2017
    2017-05-22 00:00:00
    
    22 May 2017
    2017-05-22 00:00:00
    
    September 1, 2017
    2017-09-01 00:00:00
    
    March 12, 2017
    2017-03-12 00:00:00
    
    None
    
    March 11, 2017
    2017-03-11 00:00:00
    
    January 25, 2017
    2017-01-25 00:00:00
    
    April 22, 2017
    2017-04-22 00:00:00
    
    1 September 2017
    2017-09-01 00:00:00
    
    January 18, 2018
    2018-01-18 00:00:00
    
    August 31, 2017
    2017-08-31 00:00:00
    
    21 May 2017
    2017-05-21 00:00:00
    
    January 21, 2018
    2018-01-21 00:00:00
    
    September 10, 2017
    2017-09-10 00:00:00
    
    January 19, 2018
    2018-01-19 00:00:00
    
    March 13, 2017
    2017-03-13 00:00:00
    
    January 22, 2018
    2018-01-22 00:00:00
    
    19 May 2017
    2017-05-19 00:00:00
    
    None
    
    9 September 2017
    2017-09-09 00:00:00
    
    September 9, 2018
    2018-09-09 00:00:00
    
    9 September 2017
    2017-09-09 00:00:00
    
    25 January 2019
    2019-01-25 00:00:00
    
    13 May 2018
    2018-05-13 00:00:00
    
    September 7, 2018
    2018-09-07 00:00:00
    
    9 September 2018
    2018-09-09 00:00:00
    
    January 24, 2019
    2019-01-24 00:00:00
    
    May 15, 2018
    2018-05-15 00:00:00
    
    27 January 2019
    2019-01-27 00:00:00
    
    January 26, 2019
    2019-01-26 00:00:00
    
    June 18, 2019
    2019-06-18 00:00:00
    
    January 25, 2019
    2019-01-25 00:00:00
    
    September 8, 2018
    2018-09-08 00:00:00
    
    January 25, 2019
    2019-01-25 00:00:00
    
    January 26, 2019
    2019-01-26 00:00:00
    
    April 28, 2019
    2019-04-28 00:00:00
    
    May 19, 2019
    2019-05-19 00:00:00
    
    8 September 2018
    2018-09-08 00:00:00
    
    April 27, 2019
    2019-04-27 00:00:00
    
    August 30, 2019
    2019-08-30 00:00:00
    
    18 September 2018
    2018-09-18 00:00:00
    
    August 30, 2019
    2019-08-30 00:00:00
    
    August 30, 2019
    2019-08-30 00:00:00
    
    January 24, 2020
    2020-01-24 00:00:00
    
    September 22, 2020
    2020-09-22 00:00:00
    
    8 September 2019
    2019-09-08 00:00:00
    
    January 26, 2020
    2020-01-26 00:00:00
    
    June 18, 2021
    2021-06-18 00:00:00
    
    January 24, 2020
    2020-01-24 00:00:00
    
    July 7, 2021
    2021-07-07 00:00:00
    
    None
    
    13 July 2021
    2021-07-13 00:00:00
    
    July 8, 2021
    2021-07-08 00:00:00
    
    September 2, 2021
    2021-09-02 00:00:00
    
    September 12, 2021
    2021-09-12 00:00:00
    
    July 14, 2021
    2021-07-14 00:00:00
    
    September 24, 2021
    2021-09-24 00:00:00
    
    None
    
    July 8, 2021
    2021-07-08 00:00:00
    
    March 13, 2022
    2022-03-13 00:00:00
    
    March 11, 2022
    2022-03-11 00:00:00
    
    20 May 2022
    2022-05-20 00:00:00
    
    None
    
    September 3, 2021
    2021-09-03 00:00:00
    
    March 14, 2022
    2022-03-14 00:00:00
    
    May 24, 2022
    2022-05-24 00:00:00
    
    September 3, 2022
    2022-09-03 00:00:00
    
    March 13, 2022
    2022-03-13 00:00:00
    
    12 August 2019
    2019-08-12 00:00:00
    
    19 May 2022
    2022-05-19 00:00:00
    
    25 May 2022
    2022-05-25 00:00:00
    
    21 May 2022
    2022-05-21 00:00:00
    
    September 10, 2022
    2022-09-10 00:00:00
    
    September 8, 2022
    2022-09-08 00:00:00
    
    August 31, 2022
    2022-08-31 00:00:00
    
    6 September 2022
    2022-09-06 00:00:00
    
    September 4, 2022
    2022-09-04 00:00:00
    
    None
    
    January 20, 2022
    2022-01-20 00:00:00
    
    26 May 2022
    2022-05-26 00:00:00
    
    February 10, 2023
    2023-02-10 00:00:00
    
    None
    
    May 27, 2022
    2022-05-27 00:00:00
    
    None
    
    January 22, 2023
    2023-01-22 00:00:00
    
    January 21, 2023
    2023-01-21 00:00:00
    
    30 October 2022
    2022-10-30 00:00:00
    
    January 22, 2023
    2023-01-22 00:00:00
    
    None
    
    None
    
    None
    
    None
    
    None
    
    None
    
    None
    
    None
    
    None
    
    None
    
    None
    
    


```python
for movie in movie_info_list:
    movie['Release dates (datetime)'] = date_conversion(movie.get('Release dates', 'N/A'))
```

    November 15, 2012
    7 September 2012
    September 4, 2012
    May 16, 2013
    January 18, 2013
    8 September 2013
    29 August 2013
    2 September 2013
    January 17, 2014
    18 May 2014
    January 19, 2014
    September 6, 2014
    January 17, 2014
    September 10, 2014
    November 6, 2014
    16 October 2014
    September 6, 2014
    June 16, 2014
    16 December 2014
    24 January 2015
    
    January 23, 2015
    April 8, 2015
    January 24, 2015
    September 4, 2015
    April 18, 2015
    January 27, 2015
    September 10, 2015
    March 16, 2015
    May 17, 2015
    April 16, 2015
    15 May 2015
    September 9, 2015
    January 22, 2016
    September 5, 2015
    September 12, 2015
    January 22, 2016
    May 16, 2015
    15 May 2016
    September 2, 2016
    October 8, 2016
    9 September 2016
    September 12, 2015
    8 September 2016
    April 22, 2017
    12 September 2016
    April 29, 2017
    January 22, 2017
    January 23, 2017
    May 25, 2017
    September 4, 2017
    May 22, 2017
    22 May 2017
    September 1, 2017
    March 12, 2017
    March 11, 2017
    January 25, 2017
    April 22, 2017
    1 September 2017
    January 18, 2018
    August 31, 2017
    21 May 2017
    January 21, 2018
    September 10, 2017
    January 19, 2018
    March 13, 2017
    January 22, 2018
    19 May 2017
    9 September 2017
    September 9, 2018
    9 September 2017
    25 January 2019
    13 May 2018
    September 7, 2018
    9 September 2018
    January 24, 2019
    May 15, 2018
    27 January 2019
    January 26, 2019
    June 18, 2019
    January 25, 2019
    September 8, 2018
    January 25, 2019
    January 26, 2019
    April 28, 2019
    May 19, 2019
    8 September 2018
    April 27, 2019
    August 30, 2019
    18 September 2018
    August 30, 2019
    August 30, 2019
    January 24, 2020
    September 22, 2020
    8 September 2019
    January 26, 2020
    June 18, 2021
    January 24, 2020
    July 7, 2021
    13 July 2021
    July 8, 2021
    September 2, 2021
    September 12, 2021
    July 14, 2021
    September 24, 2021
    July 8, 2021
    March 13, 2022
    March 11, 2022
    20 May 2022
    September 3, 2021
    March 14, 2022
    May 24, 2022
    September 3, 2022
    March 13, 2022
    12 August 2019
    19 May 2022
    25 May 2022
    21 May 2022
    September 10, 2022
    September 8, 2022
    August 31, 2022
    6 September 2022
    September 4, 2022
    January 20, 2022
    26 May 2022
    February 10, 2023
    May 27, 2022
    January 22, 2023
    January 21, 2023
    30 October 2022
    January 22, 2023
    


```python
# Ratings from imdb, rottentomatoes and metascore
import os
import requests
import urllib

def get_omdb_info(title):
    base_url = 'http://www.omdbapi.com/?'
    parameters = {"apikey": "3fafe88c", 't': title}
    params_encoded = urllib.parse.urlencode(parameters)
    full_url = base_url + params_encoded
    return requests.get(full_url).json()

def get_rotten_tomato_score(omdb_info):
    ratings = omdb_info.get('Ratings', [])
    for rating in ratings:
        if rating['Source'] == 'Rotten Tomatoes':
            return rating['Value']
    return None

```


```python
for movie in movie_info_list:
    title = movie['title']
    omdb_info = get_omdb_info(title)
    movie['imdb'] = omdb_info.get('imdbRating', None)
    movie['metascore'] = omdb_info.get('Metascore', None)
    movie['rotten_tomatoes'] = get_rotten_tomato_score(omdb_info)
```


```python
# One more conversion of datetime
for movie in movie_info_list:
    current_date = movie['Release dates (datetime)']
    if current_date:
        movie['Release dates (datetime)'] = current_date.strftime('%d-%m-%Y')
    else:
        movie['Release dates (datetime)'] = None
```


```python
df = pd.DataFrame(movie_info_list)
```


```python
pd.set_option('display.max_columns', None)
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>Directed by</th>
      <th>Written by</th>
      <th>Produced by</th>
      <th>Starring</th>
      <th>Cinematography</th>
      <th>Edited by</th>
      <th>Music by</th>
      <th>Production companies</th>
      <th>Distributed by</th>
      <th>Release dates</th>
      <th>Running time</th>
      <th>Country</th>
      <th>Language</th>
      <th>Box office</th>
      <th>Running time (int)</th>
      <th>Budget (float)</th>
      <th>Box office (float)</th>
      <th>Release dates (datetime)</th>
      <th>imdb</th>
      <th>metascore</th>
      <th>rotten_tomatoes</th>
      <th>Countries</th>
      <th>Budget</th>
      <th>Screenplay by</th>
      <th>Based on</th>
      <th>Story by</th>
      <th>Production company</th>
      <th>Languages</th>
      <th>Release date</th>
      <th>Narrated by</th>
      <th>Yiddish</th>
      <th>Icelandic</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A Glimpse Inside the Mind of Charles Swan III</td>
      <td>Roman Coppola</td>
      <td>Roman Coppola</td>
      <td>[Roman Coppola, Youree Henley]</td>
      <td>[Charlie Sheen, Katheryn Winnick, Bill Murray,...</td>
      <td>Nick Beal</td>
      <td>Robert Schafer</td>
      <td>[Liam Hayes, Roger Neill]</td>
      <td>[American Zoetrope, The Directors Bureau]</td>
      <td>[A24, FilmBuff]</td>
      <td>[November 15, 2012 (Rome Film Festival), Febru...</td>
      <td>86 minutes</td>
      <td>United States</td>
      <td>English</td>
      <td>$210,565</td>
      <td>86.0</td>
      <td>NaN</td>
      <td>210565.0</td>
      <td>15-11-2012</td>
      <td>4.6</td>
      <td>28</td>
      <td>16%</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ginger &amp; Rosa</td>
      <td>Sally Potter</td>
      <td>Sally Potter</td>
      <td>[Christopher Sheppard, Andrew Litvin]</td>
      <td>[Elle Fanning, Alice Englert, Alessandro Nivol...</td>
      <td>Robbie Ryan</td>
      <td>Anders Refn</td>
      <td>NaN</td>
      <td>[British Film Institute, BBC Films, Adventure ...</td>
      <td>[Artificial Eye (United Kingdom), (United King...</td>
      <td>[7 September 2012 (Toronto), 19 October 2012 (...</td>
      <td>90 minutes</td>
      <td>NaN</td>
      <td>English</td>
      <td>$1.7 million</td>
      <td>90.0</td>
      <td>NaN</td>
      <td>1700000.0</td>
      <td>07-09-2012</td>
      <td>6.2</td>
      <td>69</td>
      <td>78%</td>
      <td>[United Kingdom, Denmark, Canada]</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Spring Breakers</td>
      <td>Harmony Korine</td>
      <td>Harmony Korine</td>
      <td>[Chris Hanley, Jordan Gertner, David Zander, C...</td>
      <td>[James Franco, Selena Gomez, Vanessa Hudgens, ...</td>
      <td>Benoît Debie</td>
      <td>Douglas Crise</td>
      <td>[Skrillex, Cliff Martinez]</td>
      <td>[Muse Productions, Annapurna Pictures, Divisio...</td>
      <td>A24</td>
      <td>[September 4, 2012 ( Venice ), March 22, 2013 ...</td>
      <td>94 minutes</td>
      <td>United States</td>
      <td>English</td>
      <td>$31.7 million</td>
      <td>94.0</td>
      <td>5000000.0</td>
      <td>31700000.0</td>
      <td>04-09-2012</td>
      <td>5.3</td>
      <td>63</td>
      <td>67%</td>
      <td>NaN</td>
      <td>$5 million</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>The Bling Ring</td>
      <td>Sofia Coppola</td>
      <td>NaN</td>
      <td>[Roman Coppola, Sofia Coppola, Youree Henley]</td>
      <td>[Emma Watson, Israel Broussard, Katie Chang, T...</td>
      <td>[Harris Savides, Christopher Blauvelt]</td>
      <td>Sarah Flack</td>
      <td>[Brian Reitzell, Daniel Lopatin]</td>
      <td>[American Zoetrope, NALA Films, Pathé Distribu...</td>
      <td>[A24 (United States), StudioCanal (United King...</td>
      <td>[May 16, 2013 ( Cannes ), June 12, 2013 (Franc...</td>
      <td>90 minutes</td>
      <td>NaN</td>
      <td>English</td>
      <td>$20 million</td>
      <td>90.0</td>
      <td>8200000.0</td>
      <td>20000000.0</td>
      <td>16-05-2013</td>
      <td>5.6</td>
      <td>66</td>
      <td>60%</td>
      <td>[United States, United Kingdom, France, German...</td>
      <td>$8.2 million</td>
      <td>Sofia Coppola</td>
      <td>["The Suspects Wore Louboutins", by, Nancy Jo ...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>The Spectacular Now</td>
      <td>James Ponsoldt</td>
      <td>NaN</td>
      <td>[Tom McNulty, Shawn Levy, Michelle Krumm, Andr...</td>
      <td>[Miles Teller, Shailene Woodley, Brie Larson, ...</td>
      <td>Jess Hall</td>
      <td>Darrin Navarro</td>
      <td>Rob Simonsen</td>
      <td>[Andrew Lauren Productions, 21 Laps Entertainm...</td>
      <td>A24</td>
      <td>[January 18, 2013 ( Sundance ), August 2, 2013...</td>
      <td>95 minutes</td>
      <td>United States</td>
      <td>English</td>
      <td>$6.9 million</td>
      <td>95.0</td>
      <td>2500000.0</td>
      <td>6900000.0</td>
      <td>18-01-2013</td>
      <td>7.1</td>
      <td>82</td>
      <td>91%</td>
      <td>NaN</td>
      <td>$2.5 million</td>
      <td>[Scott Neustadter, Michael H. Weber]</td>
      <td>[The Spectacular Now, by Tim Tharp]</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
# drop columns
df = df.drop(columns=['Running time', 'Release dates', 'Box office', 'Countries', 'Budget',
                     'Languages', 'Release date', 'Narrated by', 'Yiddish', 'Icelandic', 'Story by', 'Production company'])
```


```python
# save to csv
df.to_csv('a24_data_final.csv', index = False)
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>Directed by</th>
      <th>Written by</th>
      <th>Produced by</th>
      <th>Starring</th>
      <th>Cinematography</th>
      <th>Edited by</th>
      <th>Music by</th>
      <th>Production companies</th>
      <th>Distributed by</th>
      <th>Country</th>
      <th>Language</th>
      <th>Running time (int)</th>
      <th>Budget (float)</th>
      <th>Box office (float)</th>
      <th>Release dates (datetime)</th>
      <th>imdb</th>
      <th>metascore</th>
      <th>rotten_tomatoes</th>
      <th>Screenplay by</th>
      <th>Based on</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A Glimpse Inside the Mind of Charles Swan III</td>
      <td>Roman Coppola</td>
      <td>Roman Coppola</td>
      <td>[Roman Coppola, Youree Henley]</td>
      <td>[Charlie Sheen, Katheryn Winnick, Bill Murray,...</td>
      <td>Nick Beal</td>
      <td>Robert Schafer</td>
      <td>[Liam Hayes, Roger Neill]</td>
      <td>[American Zoetrope, The Directors Bureau]</td>
      <td>[A24, FilmBuff]</td>
      <td>United States</td>
      <td>English</td>
      <td>86.0</td>
      <td>NaN</td>
      <td>210565.0</td>
      <td>15-11-2012</td>
      <td>4.6</td>
      <td>28</td>
      <td>16%</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ginger &amp; Rosa</td>
      <td>Sally Potter</td>
      <td>Sally Potter</td>
      <td>[Christopher Sheppard, Andrew Litvin]</td>
      <td>[Elle Fanning, Alice Englert, Alessandro Nivol...</td>
      <td>Robbie Ryan</td>
      <td>Anders Refn</td>
      <td>NaN</td>
      <td>[British Film Institute, BBC Films, Adventure ...</td>
      <td>[Artificial Eye (United Kingdom), (United King...</td>
      <td>NaN</td>
      <td>English</td>
      <td>90.0</td>
      <td>NaN</td>
      <td>1700000.0</td>
      <td>07-09-2012</td>
      <td>6.2</td>
      <td>69</td>
      <td>78%</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Spring Breakers</td>
      <td>Harmony Korine</td>
      <td>Harmony Korine</td>
      <td>[Chris Hanley, Jordan Gertner, David Zander, C...</td>
      <td>[James Franco, Selena Gomez, Vanessa Hudgens, ...</td>
      <td>Benoît Debie</td>
      <td>Douglas Crise</td>
      <td>[Skrillex, Cliff Martinez]</td>
      <td>[Muse Productions, Annapurna Pictures, Divisio...</td>
      <td>A24</td>
      <td>United States</td>
      <td>English</td>
      <td>94.0</td>
      <td>5000000.0</td>
      <td>31700000.0</td>
      <td>04-09-2012</td>
      <td>5.3</td>
      <td>63</td>
      <td>67%</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>The Bling Ring</td>
      <td>Sofia Coppola</td>
      <td>NaN</td>
      <td>[Roman Coppola, Sofia Coppola, Youree Henley]</td>
      <td>[Emma Watson, Israel Broussard, Katie Chang, T...</td>
      <td>[Harris Savides, Christopher Blauvelt]</td>
      <td>Sarah Flack</td>
      <td>[Brian Reitzell, Daniel Lopatin]</td>
      <td>[American Zoetrope, NALA Films, Pathé Distribu...</td>
      <td>[A24 (United States), StudioCanal (United King...</td>
      <td>NaN</td>
      <td>English</td>
      <td>90.0</td>
      <td>8200000.0</td>
      <td>20000000.0</td>
      <td>16-05-2013</td>
      <td>5.6</td>
      <td>66</td>
      <td>60%</td>
      <td>Sofia Coppola</td>
      <td>["The Suspects Wore Louboutins", by, Nancy Jo ...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>The Spectacular Now</td>
      <td>James Ponsoldt</td>
      <td>NaN</td>
      <td>[Tom McNulty, Shawn Levy, Michelle Krumm, Andr...</td>
      <td>[Miles Teller, Shailene Woodley, Brie Larson, ...</td>
      <td>Jess Hall</td>
      <td>Darrin Navarro</td>
      <td>Rob Simonsen</td>
      <td>[Andrew Lauren Productions, 21 Laps Entertainm...</td>
      <td>A24</td>
      <td>United States</td>
      <td>English</td>
      <td>95.0</td>
      <td>2500000.0</td>
      <td>6900000.0</td>
      <td>18-01-2013</td>
      <td>7.1</td>
      <td>82</td>
      <td>91%</td>
      <td>[Scott Neustadter, Michael H. Weber]</td>
      <td>[The Spectacular Now, by Tim Tharp]</td>
    </tr>
  </tbody>
</table>
</div>


