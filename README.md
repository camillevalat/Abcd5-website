
---

# Get Ready

**Writers! Directors! Producers!** Are you ready to embark on a journey to find out all the tips and tricks on how to make a great movie? Our pursuit resembles crafting a ‘cheat sheet’ —a thorough manual— that aims to unravel the necessary elements to create a _truly exceptional_ film that will leave its marks on viewers. Throughout this expedition, you will get a taste of a variety of factors which impact a movie's IMDB rating. Whether it’s the release date or the languages the movie was translated to, we didn’t leave a single stone unturned! Shall we get started?


<p align="center">
  <img src="./assets/img/background-photo.jpeg" alt="">
</p>

---


## The Name Effect

We’ve all had the experience of watching a movie and being captivated by a certain character. Investigating the influence of a character on a movie's rating reveals the complex interactions taking place: their depth, relatability, and the charisma they bring to the screen. Their presence can sway the audience's perception, affecting the film's reception and success. To investigate this theory, the two main questions we shifted our focus towards were:

Does the number of instances a character name appears have any effect on a movie’s rating?
And moreover, does the same character appearing in specifically a movie sequel have any effect on a movie’s rating?

But before starting, enjoy the interactive visualisation of the number of movies each character has appeared in! (save as html)

Character Names appearance number and Rating
*   Png plot
*   Write results
  
Which character names associate with which genre best?
*   Write results
  
Do films with sequels have a higher weighted_score?
*   Png plot
*   While films with 2 sequences vary among their

---

## Trope/Type

For this next part, we look into typical character types, and if their presence has any effect on movie ratings. By analysing ….

*   Which types are most and least popular
    * We started by grouping the data by character type and calculating the mean of their weighted scores. One can identify character types that are generally more positively received (higher scores) or those that might need improvement (lower scores). In this analysis, the two highest scores correspond to meaner, more aggressive characters. While the least two popular are women characters. Specifically, the type with the lowest mean weighted score is a woman character with a stronger character. Let’s see how trends differ when we separate the men and women types?

*   Does this trend change based on whether the type is a man or a woman?
    * We see that our data has multiple character types corresponding to men, but only 7 types corresponding to women.

*   Which type is more popular for a specific genre (?)
    * Write results

*   Are character names or character types more influential on weighted_score?
    * Now that we have gone through the different effects character names and character types have on ratings, it's time for a verdict! Which one is more influential? Instead of looking at each character name or type as a single feature, and analyse multiple p-values at once, we decided to base our conclusion on the R-squared value. This value was 0.95 for character names and 0.57 for character types, meaning that characters explain more of the variance of the weighted score compared to the types.  
This implies that the distinct individual characters have a stronger influence on a film's score compared to the character types. It suggests that specific character identities might have a more apparent impact on a movie's rating in our dataset than the character types they represent.

--- 

## Unlocking the Universal Language of Movies

<div style="display: flex; align-items: center;">
    <img src="./assets/img/universal_language.png" width="40%" style="margin-right: 10px;" />
    <p>
        In the vast world of cinema, language is more than just words, it is a bridge that connects diverse audiences, transcending borders and cultures. Why study the language feature of movies, you ask? Because language is the pulse of storytelling, an invisible yet pivotal force that shapes the experience on screen. We’re about to try to unveil the secrets of how language can elevate a film’s appeal and global reach.
    </p>
</div>


Let’s dive right into that and start by exploring the 10 most frequently used languages.


<div style="display: flex; justify-content: space-between;">
    <img src="./assets/img/language_count_top10.png" width="50%" />
    <img src="./assets/img/language_top10_pie.png" width="50%" />
</div>

As no surprise, English takes the center stage, standing as the undisputed leader.

Let’s also quickly examine the average scores associated with each of these top 10 languages.

<div style="display: flex; align-items: center;">
    <img src="./assets/img/language_top10_score.png" width="60%" style="margin-right: 10px;" />
    <p>
        For now, we don’t observe a significant difference in average scores, especially among the top 5 languages.
    </p>
</div>

However, it gets intriguing when we seek to establish a connection between language and a movie’s country of origin.

To achieve this, we build a heat map using data from the first 200 movies in our dataset. That allows us to gain insights into the distribution of languages across different countries, while maintaining a comprehensible heatmap, considering the complexity of analyzing our collection of about 55000 movies.

<p align="center">
  <img src="./assets/img/language_heatmap.png" alt="">
</p>

Once again, it comes that English reigns supreme as the most widely used language. Additionally, it’s evident that the majority of English-language films originate from the United State of America, followed by the United Kingdom.

### And what now?

Our initial foray into language analysis has provided us with a glimpse of the linguistic landscape in the world of cinema. As we’re aware, English is the most widely spoken language globally, so it begs the following question: what’s the impact of English usage on a movie’s success? 
For this investigation, we categorized movies into 2 distinct groups:
- Category 1 : movies not in English (excluding those from  the USA or  the UK)
- Category 2 : the movies that are in at least English and 1 (any) other language (excluding those from  the USA or  the UK)

Before we proceed, brief notes:
*   We've excluded movies from the USA and the UK since English is their primary language, and our earlier analysis revealed that most English-language movies originate from these 2 countries.

*   In Category 2, we've set the condition of including English and at least one other language to exclude movies from countries where English is the primary language (e.g., Canada)

*   Our dataset comprises 20,625 movies in Category 1 and 1,833 in Category 2. To ensure a fair comparison, we've randomly selected 1,833 movies from Category 1 for our future analysis


Now, let’s observe the basic descriptive statistics of these 2 categories.

|           | Category 1   | Category 2 |
|:----------|:-------------|:-----------|
| count     |     1833     |     1833   |
| std       |     15.5     |      18    |
| mean      |      36      |      47    |
| min       |     5.8      |     7.1    |
| 50%       |      34      |      45    |
| max       |      98      |     119    |


Wouldn’t it be more insightful with some visual aids?
Let’s take a look at the boxplots from both categories. Additionally,  histograms offer a more detailed view of the weighted score distributions.

<div style="display: flex; justify-content: space-between;">
    <img src="./assets/img/language_boxplots.png" width="40%" />
    <img src="./assets/img/language_categories_distrib.png" width="60%" />
</div>

The visualizations and statistics clearly highlight a difference in the average weighted scores between the 2 categories. It appears that movies in category 2 (those in English) tend to have higher weighted scores. Now, let’s address the critical question: is this difference statistically significant?



---

## Cracking the Code: When Should You Release Your Movie?

We're on a mission to figure out the best time to launch a movie. Why? Because we're not just aiming for success; we're aiming for the very best kind. And to crack this secret code, we're diving deep into the world of movie release timing.

Our Game Plan:

*  Looking at Each Type: We're not treating all movies the same. Nope! We're looking at each type or "genre" because each one has its own perfect time to shine.

*  Average Check: Armed with numbers, we're going to figure out the average performance for each genre in every month. This way, we can spot patterns and find out when each genre likes to do its best.

*  Top 20 Only: We're not looking at every type of movie out there. Nope, that would take forever! We're focusing on the top 20 most liked genres. These are the big players in the movie world.

Are you ready to unlock the secret to perfect movie timing? Get ready to discover when each genre shines the brightest! 

(plot average genre per month)

Action/Adventure takes the stage, captivating audiences with adrenaline-pumping tales in the sizzling months of June, July, and the festive December. Thriller aficionados, take note – the fourth month is your golden opportunity to shine, dominating the scene like never before. December is the month where Romantic Drama truly stands out among its peers. 
And for those moments when you find yourself in the midst of creative indecision, fear not! We've got your back with the ultimate cheat sheet. Across all months, the top three genres that consistently steal the spotlight are Action/Adventure, Thriller, and Mystery. These genres seem to have the Midas touch, bringing success no matter the season.


Now, let's talk about timing. If you're aiming for those chart-topping moments, mark your calendar for June, September, and December. These months stand tall as the shining stars of cinematic success, promising the perfect backdrop for your movie to dazzle and captivate audiences.
So, whether you're navigating the labyrinth of genres or pondering the calendar months, remember these top picks. It's not just about making a movie; it's about making the right moves at the right time. Lights, camera, action – let the magic unfold!

(fun fact)

We've curated a special treat just for you – a graph that unveils the fascinating journey of genres over time. Dive into the enchanting realm of filmmaking and witness the ebb and flow of genres, a delightful nugget of insight for all you moviemakers out there. Because understanding the past is the key to crafting a mesmerizing future in the world of cinema! 

(Graph of the genres over the years)


