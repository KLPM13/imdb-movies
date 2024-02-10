-- average rating for each genre

SELECT 
 avg(avg_rating) avg_fantasy_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Fantasy%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_action_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Action%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_adventure_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Adventure%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_Animation_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Animation%" 
      group by Genre);

  SELECT 
 avg(avg_rating) avg_comedy_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Comedy%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_Crime_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Crime%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_Drama_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Drama%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_family_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Family%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_history_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%History%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_horror_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Horror%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_music_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Music%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_musical_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Musical%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_Mystery_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Mystery%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_romance_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Romance%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_scifi_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Sci-Fi%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_thriller_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Thriller%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_war_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%War%" 
      group by Genre);
SELECT 
 avg(avg_rating) avg_western_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Western%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_biography_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Biography%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_sport_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Sport%" 
      group by Genre);

SELECT 
 avg(avg_rating) avg_filmnoir_rating
FROM (select
       genre, avg(IMDB_Rating) avg_rating
      from `reflecting-poet-391612.project.imdb-movies`
      where Genre like "%Film-Noir%" 
      group by Genre);

-- highest rating for movie director

SELECT 
  Director, 
  avg(IMDB_Rating) director_rating
FROM `reflecting-poet-391612.project.imdb-movies` 
group by Director
order by director_rating desc;

update imdb-movies set Released_year = "1995" where Released_year = "PG" ;

SELECT distinct Released_Year, sum(Gross) as total_year_sales
FROM `reflecting-poet-391612.project.imdb-movies` 
where gross is not null
group by Released_Year
order by Released_Year desc;
