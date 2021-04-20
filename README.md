# Api Tripadvisor

## getting started
This Api let's you scrap information of any restaurant of any city you choose in french.\
there are a few thing to know before you use it :\
This API can be pretty slow if you run it for a whole city, because of waiting time

### how TripAdvisor works
This information is requiered to know before using the API, because it uses a similar structure.\
a TripAdvisor URL is as follows :\
https://www.tripadvisor.fr/Restaurant_Review-g187137-d15335670-Reviews-La_table_Saint_Thomas-Reims_Marne_Grand_Est.html \
it is first comprised of the website domain, then category, and by 2 IDs\
here, in this example :\
"g187137" is the city ID\
"d15335670" is the restaurant ID.

### what it can do
this api can scrap basic information about a restaurant of your liking and produce a JSON.

#### single restaurant reviews
to do so you need to execute the following request :\
http://127.0.0.1:8000/restaurant/{cityid}/{restaurantid}
\
the info you are then getting is the top 30 reviews of that restaurant\
you can add the following query to extract all reviews for that restaurant :\
?review=True \ 
so you should be having a url that looks like :\
http://127.0.0.1:8000/restaurant/{cityid}/{restaurantid}?review=True
\

#### multiple restaurants info 
to do so you need to execute the following request :\ 
http://127.0.0.1:8000/restaurant/{cityid}
\
the info you are then getting is the top 30 restaurants of that city\
you can add the following query to extract all restaurants for that city :\
?full=True\
so you should be having a url that looks like :\
http://127.0.0.1:8000/restaurant/{cityid}?full=True
\
you can add the following query to extract all reviews for that city :\
?review=True\
so you should be having a url that looks like :\
http://127.0.0.1:8000/restaurant/{cityid}?review=True
\
you can also combine both to extract all reviews for all the restaurants of the city you chose by :\
http://127.0.0.1:8000/restaurant/{cityid}?full=True&review=True

#### dashboard
this api has a dashbord that can be displayed for a specific restaurant with the following informations:
1. restaurant infos
2. list of most used words in the review
3. a top 10 best comments (user, score, date of visit and review)
4. a top 10 worst comments (user, score, date of visit and review)

## TODO
add better lisibility to the whole API itself and restructure it \
add Sentiment Analysis prediction based on review
