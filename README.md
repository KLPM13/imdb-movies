**-- average rating for each genre**

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

**-- highest rating for movie director**

SELECT 
  Director, 
  avg(IMDB_Rating) director_rating
FROM `reflecting-poet-391612.project.imdb-movies` 
group by Director
order by director_rating desc;

**--Total sales by year**

update imdb-movies set Released_year = "1995" where Released_year = "PG" ;

SELECT distinct Released_Year, sum(Gross) as total_year_sales
FROM `reflecting-poet-391612.project.imdb-movies` 
where gross is not null
group by Released_Year
order by Released_Year desc;

**-- WHICH GENRE GENERATE THE MOST HIGHEST REVENUE**

select sum(total_gross) action


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Action%"
group by Genre);

select sum(total_gross) adventure


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Adventure%"
group by Genre);

select sum(total_gross) animation


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Animation%"
group by Genre);

select sum(total_gross) biography


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Biography%"
group by Genre);

select sum(total_gross) comedy


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Comedy%"
group by Genre);

select sum(total_gross) crime


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Crime%"
group by Genre);

select sum(total_gross) drama


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Drama%"
group by Genre);

select sum(total_gross) family


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Family%"
group by Genre);

select sum(total_gross) fantasy


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Fantasy%"
group by Genre);

select sum(total_gross) filmnoir


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Film-Noir%"
group by Genre);

select sum(total_gross) history


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%History%"
group by Genre);

select sum(total_gross) horror


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Horror%"
group by Genre);

select sum(total_gross) music


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Music%"
group by Genre);

select sum(total_gross) musical


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Musical%"
group by Genre);

select sum(total_gross) mystery


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Mystery%"
group by Genre);

select sum(total_gross) romance


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Romance%"
group by Genre);

select sum(total_gross) scifi


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Sci-Fi%"
group by Genre);

select sum(total_gross) sport


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Sport%"
group by Genre);

select sum(total_gross) thriller


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Thriller%"
group by Genre);

select sum(total_gross) war


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%War%"
group by Genre);

select sum(total_gross) western


from (SELECT 
  Genre, SUM(Gross) total_gross

FROM `reflecting-poet-391612.project.imdb-movies`
where gross is not null and Genre like "%Western%"
group by Genre);

**-- which among all star generated the most revenue**

select
  star,
  sum(Gross) as star_total_gross
from  
  (select
    Star1 as star, Gross FROM `reflecting-poet-391612.project.imdb-movies`
    union all
   select
    Star2 as star, Gross FROM `reflecting-poet-391612.project.imdb-movies`
    union all
   select 
    Star3 as star, Gross FROM `reflecting-poet-391612.project.imdb-movies`
    union all
   select
    Star4 as star, Gross FROM `reflecting-poet-391612.project.imdb-movies`
    ) stars_gross

group by star
order by star_total_gross desc;

**-- which among all star have the highest rating**

select
  star,
  avg(IMDB_Rating) as star_rating
from  
  (select
    Star1 as star, IMDB_Rating  FROM `reflecting-poet-391612.project.imdb-movies`
    union all
   select
    Star2 as star, IMDB_Rating  FROM `reflecting-poet-391612.project.imdb-movies`
    union all
   select 
    Star3 as star, IMDB_Rating FROM `reflecting-poet-391612.project.imdb-movies`
    union all
   select
    Star4 as star, IMDB_Rating FROM `reflecting-poet-391612.project.imdb-movies`
    ) stars_gross

group by star
order by star_rating desc;


