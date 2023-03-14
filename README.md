# A24scraping

### A24 is currently one of the best movie studios in the world if not the best (at least when it comes to ambitious, often budget cinema). This is confirmed e.g. by the huge success of Everything Everywhere At Once. Studio made in last year also hits such as Lamb, Bodies Bodies Bodies, The Whale or Aftersun. So, as a fan of these movies I made data about A24 and analysis of their budget, gross etc.<br>

I scraped list of movies from Wikipedia (https://en.wikipedia.org/wiki/List_of_A24_films) and then modified and cleaned them. Operations such as: 'release dates' from different strings to datetime, 'budget', 'box office' from different strings with $ to float etc.<br>

Columns:
title - The title of the film <br>
Directed by - The director(s) of the film<br>
Written by - The writer(s) of the film<br>
Produced by - producer(s) of the film<br>
Starring - main actors/actress in the film<br>
Cinematography - cinematographer(s)<br>
Edited by - editor(s)<br>
Music by - music maker(s)<br>
Production companies<br>
Distributed by - distributor(s)<br>
Country - string<br>
Language - string<br>
Running time (int) - time of movie<br>
Budget (float) - the budget of the film ($)<br>
Box office (float) - Money earned by film ($)<br>
Release dates (datetime) - release date, there were a few dates and I left first, usually on festivals<br>
imdb - film rating from imdb (float)<br>
metascore - film rating from metascore (float)<br>
rotten_tomatoes - film rating from rotten tomatoes (float)<br>
Screenplay by - screenplayer(s)<br>
Based on - the book the film was based on<br>
