# A24scraping

### A24 is currently one of the best movie studios in the world if not the best (at least when it comes to ambitious, often budget cinema). Studio made many good movies, just in last year such as Lamb, Bodies Bodies Bodies, The Whale or Aftersun. So, as a fan of these movies I made data about A24 and analysis of their budget, gross etc.

I scraped list of movies from Wikipedia (https://en.wikipedia.org/wiki/List_of_A24_films) and then modified and cleaned them. Operations such as: 'release dates' from different strings to datetime, 'budget', 'box office' from different strings with $ to float etc.

Columns:
title - The title of the film
Directed by - The director(s) of the film
Written by - The writer(s) of the film
Produced by - producer(s) of the film
Starring - main actors/actress in the film
Cinematography - cinematographer(s)
Edited by - editor(s)
Music by - music maker(s)
Production companies
Distributed by - distributor(s)
Country - string
Language - string
Running time (int) - time of movie
Budget (float) - the budget of the film ($)
Box office (float) - Money earned by film ($)
Release dates (datetime) - release date, there were a few dates and I left first, usually on festivals
imdb - film rating from imdb (float
metascore - film rating from metascore (float)
rotten_tomatoes - film rating from rotten tomatoes (float)
Screenplay by - screenplayer(s)
Based on - the book the film was based on
