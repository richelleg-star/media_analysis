# Media of Video and Videogame: User Trends

This project looks at the variation of trends and media, specifically concerning user rating and temrinology within what users are reading. To present the data, this code
utilizes python libraries to create an interactive display. This code had challenges that made it more difficult to analysis and present data.

## Summary
In terms of amount of production, videogames and different TV/Movie/Video seem to have increased in amount over the years,
with certain genres trending more than others. From ratings on scales 1-10, it appears that qualities of media forms tend to
flucuate, with videogames having higher averages than video formats. Lastly, when looking at terminology, we see that amongst
(Different Media), the similarities are more dissimilar to each other than similar

## Research Questions
1. How has the Amount of Different Media's Genre changed overtime?
2. How has the ratings of different media changed overtime?
3. Over the years, how has terminology within synopsis of different media stay similar or become different?

## Answers:
1. How has the Amount of Different Media's Genres changed overtime?
Overall, we see that overall, no matter what media type it is, overtime, there is an increase in the amount of content, regardless of
genre. We see that there are certain genre types within media formats, such as drama for games and documentary for
tv/movies/videos.
2. How has the ratings of different media changed overtime?
Overall, we see that ratings across different media formats tend to flucture. Interestingly enough, we see that the average ratings
for videogames is slightly higher than the ratings for tv/shows/videos. This could also be attributed towards the fact that
videogames is missing/does not have data from previous years that tv/shows/videos do have.
3. Over the years, how has terminology within synopsis of different media stay similar or
become different?
Overall, we see that comparing each media format's synopsis against eachother to see similarity, seems to also fluctuate. The
average synosis similairty amongst different medias is less than 50% (meaning they are more dissimilar than they are similar).

##Challenge Goals
Challenge Goals 1: Utlize 3 or more files
I think that they were closer to my proposal, so I suppose I didn't really add or scale anything back. I was going to add more, but I
was limited by the memory within juptyr hub, and adding another dataframe would have caused the kernel to repeatedly crashed.
Although, in terms of execution, I feel like I did more than I was expecting, espciaially since requiring merging allowed me to do
more with the datasets than if I had left them to their individual variables. I think you can see this a lot in the spacy dataset, as it
requires a merge of teh dataset to combine the synopsis. I also wanted to challenge myself more, so I used a large dataset (150k~)
instead of teh original 30k~ values
Challenge Goals 2: Utlize a new Library
I definetly stuck to my project proposal, and used Plotly and Spacy for this project (like I originally planned). Although, I will say,
compared to what was expected to me, I defiently expanded it. I mainly used spacy becuase I felt like I could do some analysis of
synopsis, and I would not be able to do that otherwise. Moreover, I think plotly looked a lot better compared to using seaborn or
matplotlib (in its basic form). In combination of these two reasons, I feel like this is the reason why I ended up using two new
libraries instead of one.

# Datasets

This project utlized curated datasets from Kaggle. I tried utlizing datasets that had the most up-to-date content for a more accurate
representation of data within the dataset. Each dataset utlizes content from places that aggregate content with each other; for
example, the movie and TV show database utlizes information from TMDB to get its information. Likewise, each videogame dataset
got their information from Backloggd and Metacritic.
However, each dataset has content spanning different years, so some data that one dataset might have on a previous year might
not exist. The same applies going forward; a lot of datasets have games and media that have not been released as of downloading
each of these datasets. Because of this, I have made the decision to drop games that have not been released yet (considering data
that is 2025<= ).

Data sets utilized:
https://www.kaggle.com/datasets/asaniczka/full-tmdb-tv-shows-dataset-2023-150k-shows
https://www.kaggle.com/datasets/beridzeg45/video-games
https://www.kaggle.com/datasets/matheusfonsecachaves/popular-video-games

# Methods
Overall methods:
obtain datasets over kaggle, getting media datasets
import all required libraries
reviewed example project
create definitions that do repetivive work
clean dataset
merge datasets for q1 and q2
utlize spacy to compare and contrast synopsis of media in q3
create plot from plotly
Global Data transformations:
added a column that took the Year from a given date and add one
Drop NaN values from the dataframes
create graphs to represent the changes overtime
drop years that are > 2024
per question, drop any columns that were not going to be utlized
Research Q1 transformations:
look at the datasets individiually and adjust genre columns;
for the videogame dataset:
take the genre list as a literal list (using atr to do so)
explode the list via python explode and convert genre list to long-form dataset
for videos/tv/movie dataset:
take the genre string and split them up using split()
take that split result and explode it
Research Q2 transformations:
create a new sum (adding rating columns of both dataset) column
merged datasets that were altered
during groupby(), utlized the mean function
Research Q3 transformations
during groupby functions, aggregated a join function to combine all values together for a given year
utlized clean function to force a lowercase and remove all punctionation from this new result

# Implications and Limitations
Overall, this project benefits both the users and the developers/producers of media. Developers benefit from these research
questions to be able to track what is popular amongst fanbases, such as looking at specific genres. Moreover, when considering
what media type to put certain games, perhaps it could be beneficial to know each average rating within a given year of each
media type and produce something based off of that. Lastly, by looking at how similar synopsis tend to be across media,
In terms of users, I think they can benefit knowing what genres are popular to give a conuntinous feedback on developers; if users
think that something withn their media format is oversaturated, then they are able to use statistics to able to give critical feedback.
Moreover, I think that users can encourage developers to improve their quality of their games by utlizing quality trends overtime.
Lastly, I think users can benefit from knowing the similarity between media formats to gauge if the content they experience within a
given year is more similar to each other than not.
Those who might be harmed or excluded might actually be the developers/producers. Perhaps developers and producers might
lose funding from shareholders if shareholders are aware of popularity of certain genres; or maybe producers/developers might
stop developing certain genres for fear that their media format does not follow the most created genre.
There are three limitations to this:
1. in terms of similarity, spacy utlizes vectors to compare each text to one another and utlizes the average; meaning that the
results of similarity might be misconstrued if there was run on words or if messages use similar wording, but have different
messages.
2. in terms of ratings, this is an average rating for different media types, and does not consider other methods of collecting
information about rating, such as median or mode. Therefore, the data can be construed by extreme outliers.
3. in terms of genre counting, it should be noted that some media formats have entries with more than one genre, which means
that the count is considered for all genres it applies to (e.g. if a game has teh genre's action and drama, it would add +1 count
to action and drama).
Overall, people should be cautious of using my results as a basis of their conclusions on what is happening in different media
format; as times change and more data is being collected, averages will always fluctuate.


# Pictures of Graphs + Analysis

## Q1
![Question 1](https://github.com/user-attachments/assets/19480b17-a1e0-479c-99dc-fbf6e573411e)

Looking at the graphs that has been created, it looks like there is more television/videos being created compared to videogames.
Interestingly enough, both video game and TV/videos had similar trending genres throughout the years.
For example, videogames top 3 trending genres appears to be drama, action and Indie over consecutive years. Morover, for
televisions, the most popular genres appears to be Documentary, Simulator, animation.
This is innteresting to note, as it implies a few hypothetical answers as to why this is occuring. First hypothesis is that those genres
are just they type to trend amongst users over others. This also might imply hypothetical production costs into making these
genres; perhaps it is overall cheaper to make a documentary film or a drama filled game compared to other lower count genres
such as pinball or racing. This lastly might imply that lower scoring genres are not as interesting to the users compared to the more
produced genres

## Q2
![Quesiton 2](https://github.com/user-attachments/assets/1e612465-1905-4990-b19a-37cc62376957)

Overall, it looks like the ratings in videogames are a lot more in fluction compared to video/tv/movies. Moreover, the average rating
for video/tv/movies are lower than the overall average, while the average rating for video games is slightly higher than the overall
average.
I think overall, I feel like these results could be a for a few reasons. First, I feel like the quantity of videogames is lower than that of
videos/tv/movies, and therefore, the data might be a little scewed positively towards videogames. However, even without that
consideration, I think it's also because videogames offer that interaction that you can't get from watching a piece of media, which I
feel like is the result of a more positive average rating over video media. Moreover, I think that video media is a lot easier to critque
than a videogame, as you are rating things on subjective story plot, perhaps characters, while videogames consdier that in addition
to playability mechanics

## Q3
![Question 3](https://github.com/user-attachments/assets/f1be0e49-7a14-4ea1-a526-34e35978324c)

We see that overall similarity between different media synopsis seems to fluctuate, and with very high peaks and lows. Moreover,
the average similarity overall seems to be lower than 50%, implying that overall, media synopsis (and indication that what media
contains) is more dissimilar than similar.
There are a few plausible causes of this fluctuating similairty pattens. I think the first thing that might be causing these highs and
lows are external event related; for example, there was a significant drop in 2000, where there was a econimic recession; and then
we see anotehr drop in similarity during the covid-19 pandemic. Moreover, this average similarity of media being more dissimialr to
each other might also becuase certain media formats might not have similar themes because of their format; for example, we aren't
expecting the terminology of dungeon crawlers to appear in media about film. However, we would expect that for synopsis in
videogames, since it is a major genre. 




