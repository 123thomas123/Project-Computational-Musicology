---
title:  'Project Computational Musicology'
author: 'Thomas Visser'
date:   'February--March 2020'
output: 
    flexdashboard::flex_dashboard:
        storyboard: true
        theme: flatly
---

```{r setup}
# In order to use these packages, we need to install flexdashboard, plotly, and Cairo.
library(tidyverse)
library(plotly)
library(spotifyr)
source('Spotify.R')
library(viridis)
remotes::install_github('jaburgoyne/compmus')
library(compmus)

```

### Introduction: Fleetwood Mac, from a British blues band to a worldwide poprock band, what happenend?

**Fleetwood Mac as a Blues Band**

Fleetwood Mac is originally a British blues band that came up at the end of the 1960s and beginning of the 1970s. The original band members was formed by Peter Green, Mick Fleetwood, Jeremy Spencer John McVie and later Chistine Perfect and Danny Kirwan.The Blues period lasted from 1967 to 1969, when Peter Green and Jeremy Spencer both left the band due to mental illness. The band began transitioning into a more pop/rock style from 1970 to 1974 but this potential was not fully reached until the recruitment of Lindsey Buckingham and Stevie Nicks.     

**Fleetwood Mac as a Pop Rock Band**

Fleetwood Mac established itself as a poprock band in 1975 when they recruited Lindsey Buckingham and Stevie Nicks. The first album they created together was a breakthrough for the band. They became popular worldwide and got mainstream media fame. After this album all romantic relationships within the band came to an end. This caused major tensions in the band but thankfully all these came together in the creative drug infused and alcoholic miracle album Rumours. This album was basically in album with only hits giving the band even more succes across the globe. Rumours has become number eight on the list of best-selling albums of all time with 40 million copies sold. After this albums a few other succeful albums were created, but none came close to the succes of the Rumours. The tensions in the band made it so people were leaving and joining the band every couple of years and not as many music was created as in the early blues days.

**What is the Difference in Music?**

Fleetwood Mac is a band that has had such an exciting musical history and has made so many huge hits that it's interesting to compare all the Fleetwood Mac albums to each other using the Spotify API. What were the differences between these albums? What is the secret of the album Rumours compared to the other albums? And how did the Blues era compare to the transitiong era and to the pop/rock era of Fleetwood Mac?

**The Research Project**

For this project I created three era's of albums that I want to compare, a Blues era containing the albums Fleetwood Mac (Peter Green's Fleetwood Mac), Mr.Wonderful and Then Play On, a Transitioning era containing the albums Kiln House, Future Games, Bare Trees, Penguin, Mystery to Me and Heroes are Hard to Find and a pop/rock era containing the albums Fleetwood Mac (Stevie Nicks/Lindsey Buckingham's Fleetwood Mac), Rumours, Tusk, Mirage, Tango in the Night, Behind the Mask, Time and Say You Will. These are in total all the studio albums from Fleetwood Mac (according to Wikipedia). Rumours was saved as a stand-alone album aswell so it could be compared to all the other albums. I also made a playlist containing all the albums so general means of all variables could be calculated. I looked at five features from the Spotify API: danceability, valence, tempo, energy and instrumentalness. 

### First Glance at Spotify API features Danceability, Valence, Tempo, Energy and Instrumentallness. What are Striking first findings in means and standard deviations?

**Danceability**

Danceability is (according to the Spotify API) a measure of how suitable a track is for dancing, based on the combination of some musical elements including tempo, rhythm stability, beat strength and overall regularity. Danceability is measured on a scale from 0 to 1, where a zero stands for least danceable and a one stands for most danceable.

When looking at danceability you can see a small steady increase with a lower danceability of the Blues era (M = 0.52, SD = 0.12), a higher danceability of the transitioning era (M = 0.53, SD = 0.10) and the highest danceability of the pop/rock era (M = 0.60, SD = 0.11). The danceability of Rumours was the highest overall (M = 0.65, SD = 0.08). The average danceability across all albums was 0.56 (SD = 0.12).

**Valence**

Valence is (according to the Spotify API) a measure that describes the musical positiveness conveyed by a track. Tracks with a high valence are generally more happy, cheerful and euphoric and tracks with a low valence are generally more sad, depressed and angry.
Valence is measured on a scale from 0 to 1, where a zero stands for most negative (lowest valence) and a one stands for most positive (highest valence).

When looking at valence you see an increase in the beginning with a lower valence of the Blues era (M = 0.55, SD = 0.26) and a high valence of the transitioning era (M = 0.65, SD = 0.24). Then the valence stays more or less the same in the pop/rock era (M = 0.64, SD = 0.23). The valence of Rumours was the highest overall (M = 0.71, SD = 0.19). The average valence across all albums was 0.62 (SD = 0.25).

**Tempo**

Tempo is (according to the Spotify API) the estimated pace of a track in beats per minute (BPM). This is a measure that can be interpreted as how fast or slow a song is. Tempo has a scale that ranges from about 50 (BPM) to about 220 (BPM), where 50 (BPM) stands for a slow tempo/song and 220 (BPM) stands for a very high tempo/song.

When looking at tempo you can see a steady increase with a lower tempo in the Blues era (M = 114.05, SD = 29.79), a higher tempo in the transitioning era (M = 122.90, SD = 29) and the highest tempo in the pop/rock era (M = 124.47, SD = 24.64). The tempo of Rumours was the highest overall (M = 130.80, SD = 21.54). The average danceability across all albums was 121.62 (SD = 27.30).

**Energy**

Energy is (according to the Spotify API) a measure of intensity and activity. High energetic tracks are generally loud and noisy and low energetic tracks are generally quiet. Energy is measured on a scale from 0 to 1, where a zero stands for least energetic and a one stands for most energetic.

When looking at energy you see a small increase in the beginning with a lower energy of the Blues era (M = 0.40, SD = 0.21) and a bit higher energy of the transitioning era (M = 0.48, SD = 0.19). In the pop/rock era the energy has increased by a lot and the highest average value for energy is found (M = 0.61, SD = 0.21). The Energy of Rumours was about the same as the overall energy in the pop/rock era (M = 0.59, SD = 0.26). The average energy across all albums was 0.53 (SD = 0.22).

**Instrumentalness**

Instrumentalness is (according to the Spotify API) a measure of **non ** vocalness and the spoken word in a song. In this context are *ooh* and *aah * sounds considered as vocal. So a track with a high instrumentalness has not many vocals in the song and a track with a low instrumentalness has many vocals in the song. Instrumentalness is measured on a scale from 0 to 1, where a zero stands for most vocal and a one stands for least vocal (most instrumental).

When looking at the Instrumentalness you can see a bell shaped curve with a lower Instrumentalness in the Blues era (M = 0.17, SD = 0.32) a higher Instrumentalness in the transitioning era (M = 0.24, SD = 0.33) and the lowest Instrumentalness in the pop/rock era (M = 0.06, SD = 0.16). The Instrumentalness of Rumours was about the same as the overall instrumentalness in the pop/rock era (M = 0.05, SD = 0.14). The average Instrumentalness across all albums was 0.13 (SD = 0.27).


**Striking Features**

The features Danceability, Tempo and Energy all seem to increase from the blues era to the pop/rock era. This makes semantical sense because Blues is generally less danceable, has a slower pace and a lower energy compared to pop/rock. Valence increased from the Blues era to the Transitional era and then stayed the same in the pop/roprock era. Blues music sounds generally more negative than the tracks in the other two era's of Fleetwood Mac so this finding makes sense. Also, when listening to the transitional and the pop/rock era I do not hear much difference in the overall positiveness of the songs so tha valence having the same value for these era's makes sense. 

Instrumentalness has a very interesting result, with the highest instrumentalness (lowest vocalness) in the transitional period and the lowest instrumentalness in the pop/rock era. This seems likely to be explained by the fact that both singers Peter Green and Jeremy Spencer left the band at this time so there was not a leadsinger established. The bandmember Danny Kirwan was forced more or less to be the frontman of the band but he was more of a guitar player at heart. This explains the fact that there were less vocals in the transitional period. In the pop/rock era Stevie Nicks and Lindsey Buckingham joined the band and they were both singers and lyrically talented, which is why the instrumentalness is almost zero in this era, indicating a high amount of vocalness within the songs.

Rumours does seem different compared to all other albums when looking at the features Danceability, Valence and Tempo. It scored the highest on all of these features indicating that this album was musically different than the other albums, even compared to the pop/rock era in which the music was very similar. The features Energy and Instrumentalness of Rumours do not seem to differ from the overall Energy and Intstrumentalness pop/rock era. 

### Visualisation: Fleetwood Mac moves from slow low energy blues tracks to high energy danceable tracks

```{r}

# Creating all the wanted variables for comparisons

fleetwood_mac_all_albums <- get_playlist_audio_features('thomas visser', '06uRyAVYL3GHFF02q2QtjC')

fleetwood_mac_album1 <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Fleetwood Mac'),]
Mr.wonderful <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Mr. Wonderful'),]
then_play_on <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Then Play On (2013 Remaster; Expanded Edition)'),]
Kiln_House <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Kiln House'),]
Future_games <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Future Games'),]
Bare_trees <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Bare Trees'),]
Penguin <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Penguin'),]
Mystery_to_me <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Mystery to Me'),]
Heroes_are_hard_to_find <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Heroes Are Hard to Find'),]
fleetwood_mac_album2 <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Fleetwood Mac (2017 Remaster)'),]
rumours <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Rumours'),]
Tusk <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Tusk (2015 Remaster)'),]
Mirage <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Mirage (2016 Remaster)'),]
Tango_in_the_night <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Tango in the Night (2017 Remaster)'),]
Behind_the_mask <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Behind the Mask'),]
Time <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Time'),]
Say_you_will <- fleetwood_mac_all_albums[which(fleetwood_mac_all_albums$track.album.name == 'Say You Will'),]


Blues_era <- fleetwood_mac_album1 %>% bind_rows(Mr.wonderful, then_play_on)
Transitioning_era <- Kiln_House %>% bind_rows(Future_games, Bare_trees, Penguin, Mystery_to_me, Heroes_are_hard_to_find)  
Pop_rock_era <- fleetwood_mac_album2 %>% bind_rows(rumours, Tusk, Mirage, Tango_in_the_night, Behind_the_mask, Time, Say_you_will)
# Rumours    

Fleetwood_all <- Blues_era %>% mutate(era = "Blues era") %>% bind_rows(Transitioning_era %>% mutate(era = "Transitioning era")) %>% bind_rows(Pop_rock_era %>% mutate(era = "Pop/Rock era"))

#fleetwood_mac_all_albums$era <- rbind('Blues era' = fleetwood_mac_all_albums[1:53,], 'Transitioning era' = #fleetwood_mac_all_albums[54:113,], 'Pop rock_era' = fleetwood_mac_all_albums[114:227,])

mean_dans <- fleetwood_mac_all_albums %>% summarise(M = mean(danceability), SD = sd(danceability))
mean_val <- fleetwood_mac_all_albums %>% summarise(M = mean(valence), SD = sd(valence))
mean_tempo <- fleetwood_mac_all_albums %>% summarise(M = mean(tempo), SD = sd(tempo))
mean_energy <- fleetwood_mac_all_albums %>% summarise(M = mean(energy), SD = sd(energy))
mean_instru <- fleetwood_mac_all_albums %>% summarise(M = mean(instrumentalness), SD = sd(instrumentalness))


```


```{r}

# ADD GRAPH OF INSTRUMENTALNESS LATER

Fleet <-
  Fleetwood_all %>% # Start with all albums
  ggplot(                      # Set up the plot.
    aes(
      x = danceability,
      y = energy,
      size = valence,
      colour = era,
      label = track.name   # Labels will be interactively visible.
    )
  ) +
  geom_point() +               # Scatter plot.
  geom_rug(size = 0.1) +       # Add 'fringes' to show data distribution.
  #facet_wrap(~ era) +          # Separate charts per playlist.
  scale_x_continuous(          # Fine-tune the x axis.
    limits = c(0, 1),
    breaks = c(0, 0.50, 1),  # Use grid-lines for quadrants only.
    minor_breaks = NULL      # Remove 'minor' grid-lines.
  ) +
  scale_y_continuous(          # Fine-tune the y axis in the same way.
    limits = c(0, 1),
    breaks = c(0, 0.50, 1),
    minor_breaks = NULL
  ) +
  scale_colour_brewer(         # Use the Color Brewer to choose a palette.
    type = "qual",           # Qualitative set.
    palette = "Paired"       # Name of the palette is 'Paired'.
  ) +
  scale_size_continuous(       # Fine-tune the sizes of each point.
    trans = "exp",           # Use an exp transformation to emphasise loud.
    guide = "none"           # Remove the legend for size.
  ) +
  theme_light() +              # Use a simpler them.
  labs(                        # Make the titles nice.
    x = "Danceability",
    y = "Energy",
    colour = "",
    size = "Valence"
  ) + scale_color_viridis(discrete = T, option = "D")


ggplotly(na.omit(Fleet))



#ggplot(fleetwood_mac_all_albums, aes(x = track.album.release_date, y = valence, color = track.popularity)) + geom_point()
#ggplot(fleetwood_mac_all_albums, aes(x = track.popularity, y = danceability, color = track.album.name)) + geom_boxplot()

# color = track.album.name facet_wrap(~track.album.name)

# fleetwood_mac_all_albums$track.album.release_date <- as.Date(fleetwood_mac_all_albums$track.album.release_date)


```

***

This Graph contains all songs of Fleetwood Mac studio albums. The songs are divided in the three different era's of Fleetwood Mac, the Blues era, the Transitioning era and the Pop/Rock era. These era's and their colours are shown on the right side of the graph. The size of the dot represents the overall valence (positivity) of that particalur song. You can hover over songs to get some extra information about them.    

Fleetwood Mac started out as a band with mostly songs that were not that danceable and low energy, which really illustrates there Blues era. In the transitional period you see the yellow dots moving more towards higher energy and higher danceability, while still making slow low energy songs here and there. They are trying to find a new sounds but they are not there yet. The Green dots really showcase how Fleetwood Mac has changed in the Pop/rock era. Most songs are very high energy and the danceability is also considerably higher. An outlier to this pattern seems to be the song The Second Time (green dot leftside below).

The Mode is the valence of the song (positivity). As you can see the Blues era has mostly small dots, which are more negative sounds in their songs. The Transitional and Pop/Rock era have mostly big dots, meaning the sounds are a lot more positive which is porbably also why they are more danceable and have higher energy.

### Visualisation: Was Rumours really that special?

```{r}

Rumours_rum <-
  Pop_rock_era %>%            # Start with all albums from pop/rock era
  ggplot(                      # Set up the plot.
    aes(
      x = danceability,
      y = valence,
      #size = tempo,
      colour = track.album.name,
      label = track.name   # Labels will be interactively visible.
    )
  ) +
  geom_point() +               # Scatter plot.
  geom_rug(size = 0.1) +       # Add 'fringes' to show data distribution.
  #facet_wrap(~ era) +          # Separate charts per playlist.
  scale_x_continuous(          # Fine-tune the x axis.
    limits = c(0, 1),
    breaks = c(0, 0.50, 1),  # Use grid-lines for quadrants only.
    minor_breaks = NULL      # Remove 'minor' grid-lines.
  ) +
  scale_y_continuous(          # Fine-tune the y axis in the same way.
    limits = c(0, 1),
    breaks = c(0, 0.50, 1),
    minor_breaks = NULL
  ) +
  scale_colour_brewer(         # Use the Color Brewer to choose a palette.
    type = "qual",           # Qualitative set.
    palette = "Paired"       # Name of the palette is 'Paired'.
  ) +
  scale_size_continuous(       # Fine-tune the sizes of each point.
    trans = "exp",           # Use an exp transformation to emphasise loud.
    guide = "none"           # Remove the legend for size.
  ) +
  theme_light() +              # Use a simpler them.
  labs(                        # Make the titles nice.
    x = "Danceability",
    y = "Valence",
    colour = "Album Name",
    size = "Tempo"
  ) + scale_color_viridis(discrete = T, option = "D")


ggplotly(na.omit(Rumours_rum))



```

***

This Graph contains all songs of Fleetwood Mac albums in the Pop/Rock era. Rumours was such a huge album with many hits so it is interesting to see how this album contests with all the other albums of the Pop/Rock era. 

When looking at this graph, we notice that Rumours does not look that different than all the other albums of the Pop/Rock era in these specific Spotify features. So maybe is Rumours not that musically different from these albums but is it more semantically different. With semantically different I mean that the songs of rumours all contain real lyrics and emotions in a time were the tensions of the band were really high. It might be that people understand the difference between a lyrically meaningful song and a lyrically not so meaningful song, but an Algorithm cannot view this distance. 

So I would argue that Rumours does not look different from other albums in the Pop/Rock era because an algorithm cannot distinct between meaningful and meaningless songs. Therefore the conclusion would be that although Rumours does not look that different in this graph, it might still be different in its semantical meaning compared to the other albums. 

### Chromagram: is The Second Time really musically different from the other Fleetwood Mac songs?


```{r }

second_time <- 
  get_tidy_audio_analysis('14nc3a84fMDelO7Y3Rwqg2') %>% 
  select(segments) %>% unnest(segments) %>% 
  select(start, duration, pitches)

# outlier The Second Time from the album behind the mask.


```

```{r}

second_time %>% 
  mutate(pitches = map(pitches, compmus_normalise, 'chebyshev')) %>% 
  compmus_gather_chroma %>% 
  ggplot(
    aes(
      x = start + duration / 2, 
      width = duration, 
      y = pitch_class, 
      fill = value)) + 
  geom_tile() +
  labs(x = 'Time (s)', y = NULL, fill = 'Magnitude') +
  theme_minimal() + scale_color_viridis(option = "D")



```

*** 

This is a chromagram of the outlier to the Energy/Danceability pattern of the song The Second Time. 

I still find it difficult to interpret this chromagram. I think it shows that mostly the song was played in the C but I am not sure.



