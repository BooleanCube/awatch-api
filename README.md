# awatch-api
> Java Wrapper for anime related APIs

Awatch is powered by:
- [Jikan API](https://jikan.moe/)
- [Kawaii API](https://kawaii.red/)
- [Animechan API](https://animechan.vercel.app/)

An example of a project that uses this wrapper library: <br>
https://github.com/BooleanCube/lollipop-bot

## Necessary Libraries

Install JDA Wrapper Library for JSON wrapper (DataObject and DataArray) <br>
Installation Steps are in this README.md: https://github.com/DV8FromTheWorld/JDA/blob/master/README.md

## Usage
1. Declare a client object, attach AListener

```java
class Client implements AListener {

    // this refers to the instance of the AListener
    AClient client = new AClient(this);
    
}
```

2. Call methods to fetch data

```java
// search for an anime
client.searchAnime(String query, boolean nsfw);

// search for a character
client.searchChracter(String query);

// retrieves a randomly chosen anime quote
client.randomQuote();

// get a list of episodes of a certain anime given the malID (can be found from the searches made)
client.getEpisodes(long malID);

// get recent news of a certain anime given the malID (can be found from the searches made)
client.getNews(long malID);

// get statistics of a certain anime given the malID (can be found from the searches made)
client.getStatistics(long malID);

// get theme songs of a certain anime given the malID (can be found from the searches made)
client.getThemes(long malID);

// get recommendations from a certain anime that you like given the malID (can be found from the searches made)
client.getRecommendation(long malID);

// get the top review of a certain anime given the malID (can be found from the searches made)
client.getReview(long malID);

// get the highest ranking animes in term of score
client.getTop();

// get the latest trending animes of the season
client.getLatest();

// get a randomly chosen anime from the MAL datbase
client.randomAnime(boolean nsfw);

// get a randomly chosen anime related GIF
client.reandomGIF();

// get a random anime to use in your trivia
client.randomTrivia();
```

3. Implement the methods of AListener

```java
@Override
public void sendSearchAnime(ArrayList<Anime> animes) {
    for(int i=0; i<animes.size(); i++) {
        Anime anime = animes.get(i);
        System.out.println(anime.toString());
    }
}

@Override
public void sendSearchCharacter(Character character) {
    System.out.println(character.toString());
}

@Override
public void sendRandomQuote(Quote quote) {
    System.out.println(quote.toString());
}

@Override
public void sendEpisodes(ArrayList<Episode> episodes) {
    for(int i=0; i<episodes.size(); i++) {
        Episode episode = episodes.get(i);
        System.out.println(episode.toString());
    }
}

@Override
public void sendNews(ArrayList<Article> articles) {
    for(int i=0; i<articles.size(); i++) {
        Article article = articles.get(i);
        System.out.println(article.toString());
    }
}

@Override
public void sendStatistics(Statistic statistics) {
    System.out.println(statistics.toString());
}

@Override
public void sendThemes(Themes themes) {
    System.out.println(themes.toString());
}

@Override
public void sendRecommendation(Recommendation recommendation) {
    System.out.println(recommendation.toString());
}

@Override
public void sendReview(Review review) {
    System.out.println(review.toString());
}

@Override
public void sendTop(ArrayList<Anime> top) {
    for(int i=0; i<top.size(); i++) {
        Anime anime = top.get(i);
        System.out.println(anime.toString());
    }
}

@Override
public void sendLatest(ArrayList<Anime> latest) {
    for(int i=0; i<latest.size(); i++) {
        Anime anime = latest.get(i);
        System.out.println(anime.toString());
    }
}

@Override
public void sendRandomAnime(Anime random) {
    System.out.println(random.toString());
}

@Override
public void sendRandomGIF(GIF gif) {
    System.out.println(gif.toString());
}

@Override
public void sendTrivia(Question question) {
    System.out.println("Correct Anime: " + question.correct.title);
    System.out.println("Options: " + question.options.toString());
}
```

----

**Developed by BooleanCube**
