# beatmania-iidx
This is the dataset of ALL the songs and their charts from Japanese Rhythm game from Konami called beatmania IIDX. It is a game where the player has 7 keys with a piano layout and a scratching disc to hit the notes as they approach the mark. The game has been around since February 26, 1999 and has close to 30 versions over the span of 20+ years. I am collecting data using remywiki.com as my source. My foucs is just the arcade version of beatmania IIDX.

**THIS DATASET IS STILL WIP AND HAS ONLY COVERED THE FOLLOWING:**
-beatmania IIDX (1st style)
-beatmania IIDX substream
-beatmania IIDX 2nd style
-beatmania IIDX 3rd style (4/10/2022)
-beatmania IIDX 4th style (4/11/2022)
-beatmania IIDX 5th style (4/11/2022)
-beatmania IIDX 6th style (11/22/2024)
-beatmania IIDX 7th style (11/23/2024)

When making this dataset, I often ask myself about what kind of rules does the set have to implement in order for it to be used for Data Analysis for SQL or Data Visualization Tools. 
1. Normally, I could go for just Artist name, but the music producers that contribute to the game often use different names for some of their songs, which is why there are two columns used for the artists: The name used for the song and the credit, which is mostly the musician's real name. 
**E.G. **
"AA" and "LEADING CYBER" were produced by Takayuki Ishikawa, who used "D.J. Amuro" and "dj TAKA" respectively for these songs. 

For songs that involved two or more artists, I usually put the artists' names in just the Artist Credit column, but I will need to remind myself to use a delimiter (", ") when it is loaded up in Python or SQL. Otherwise, "Naoki Maeda, Robbie Danzie, Aaron G" will be counted as one artist instead of 3 different string values/artists, especially when a song has "vs." in the "Artist Name."

2. Some songs will have BPM changes during the song and were sometimes to throw off players and listeners. There are two columns dedicated to the lowest BPM and the highest. 
**E.G. **
"era(nostalmix)" 's lowest BPM is 90 while it constantly runs at 180BPM. However for "ICARUS," despite the song played at 176BPM, it has a slow buildup section that starts at 126BPM and goes up to 251BPM.

3. On top of songs having different BPM during the song, some charts have different values depending on the difficult chosen. The song may have more than one entry to help satisfy this condition.
**E.G. **
"quell (the seventh slave)" runs at 140BPM on Normal and Hyper, but clocks at 162BPM when playing it on Another difficulty.

Right now, "empathy" from IIDX 4th style is taking up multiple rows due to the HYPER/ANOTHER charts having different BPM ranges compared to its NORMAL chart. 

4. As of 4/10/2022, any song that was written in Japanese would instead use the Romanji name since I am still figuring out how to make SQL or any data analysis recognize Japanese text. Artist names is also affected by this.
**E.G. **
"桜" on the dataset would be written as "Sakura"

For now, I have used the song's Japanese title as it was written but when using it for Data Visualization and SQL, I may need to figure out how to let the tools recognize Japanese text.

5. Even though songs may have similar genres, they may be written differently when it was released.
**E.G. **
Songs with "Drum'n'Bass," " Drum and Bass," DnB" and "Drum & Bass" etc.

6. beatmania IIDX difficulty from 1 to 7+ from 6th through 9th style, 1 to 8 in 10th, 1 to 8+ in IIDX RED, and 1 to 12 from 12 HAPPY SKY onwards. However, this dataset will focus on the chart difficulty using the latest difficulty scale. It will also focus on charts that have been featured in its arcade release, so even though some songs did have a Beginner and Another difficulty option on its console (CS) appearance, it will not be included in the dataset.
7. As of the release of 8th style dataset (dated 11/24/2024), I had to add a column that would include a Japanese written title (or a title with special letters or characters) as an alternative because I am still figuring out how R or SQL could recognize text written in a language that is not English. (This is completely experimental!)

Important questions to ask as part of the showcase of skills:
** DATA CLEANSING **
Is there a possibility of transforming "n/a" values into integers in order help with its consistency?


** DATA VISUALIZATION **
How difficult are the license songs and their charts compared to the non-license songs and their charts?
Which non-license artist frequently contributes music for the series?
