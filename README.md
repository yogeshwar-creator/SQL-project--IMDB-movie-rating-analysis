# SQL-project--IMDB-movie-rating-analysis
#task1
select*from movies;

#task2
select*from directors;

#task3
select count(original_title) as movies from movies;

#task4
select * from directors where name in ('james cameron','luc besson','john woo');

#task5
select name from directors where name like 'S%';

#task6
select  count( gender) from directors where gender='1';

#task7
select name from directors where gender=1 order by name asc limit 1 offset 9;

#task8
select original_title as movie from movies order by popularity desc limit 3;

#task9
select original_title as movie from movies order by revenue desc limit 3;

#task10
select vote_average,release_date from movies where year(release_date)>=2000 order by vote_average desc limit 1;

#task11
select m.original_title as movie from directors d join movies m on d.id=m.director_id where d.name= 'Brenda Chapman';


#task12
select d.name,count(m.id) as total_movie from directors as d join movies as m on d.id=m.director_id group by d.id order by total_movie desc ;

#task13
select d.name,sum(revenue) as total_revenue from directors as d join movies as m on d.id=m.director_id group by d.id order by total_revenue desc;

select d.name as director_name, count(m.id) as movie_count from directors as d join movies as m on d.id=m.director_id group by d.name order by movie_count desc limit 10;
