---
layout: post
title:  "Book of Mormon Text Analysis"
description: A dive into speech comparison in the Book of Mormon
image: /assets/img/post2header.png
---

## Introduction

The Book of Mormon has been examined in many ways using several tools and by seasoned experts. Much of these analyses are written in dense research literature examining the intricacies of the text and pulling out fine details. As a statistician I have been fascinated by this work but wanted to create an interactive way to showcase findings and allow a reader to examine it for themselves. This Streamlit app does just that!

## Motivating questions:
-	Are there clear differences between Book of Mormon authors language use?
-	How is the word ‘desire’ used throughout the Book of Mormon?

By examining these trends, we can gain new insights into how the authors of the Book of Mormon used language and compare the differences. In taking a deeper dive into how the word ‘desire’ is used we can start to understand the differences between the intended meaning of the word by the Book of Mormon authors and how we use it today.

## Key Insights
1.	Nephi never used the Word Christ
When comparing word usage throughout the Book of Mormon, it is shocking to see that Christ doesn’t appear once in 1st Nephi. When I was originally coding this up, I thought I made a mistake in the code but upon closer examination this is true. In fact, Nephi doesn’t even know the Savior of the World’s name until it is revealed to his brother Jacob. This insight can be seen in this first graph:

![post3plot1.png]({{site.url}}/{{site.baseurl}}/assets/img/post3plot1.png)

As you can see, the word ‘Christ’ is not found in 1st Nephi as the bar representing occurrences of Christ and normalized by length is at 0. If we look at a table holding the occurrences of Christ in 2nd Nephi (the book that immediately follows 1st Nephi) we can look at the situation:


| Book    | Chapter:Verse | Text                                                     |
|:-------:|:-------------:|----------------------------------------------------------|
| 2 Nephi | 10:3          | must need be expedient that christ for in the last night |
| 2 Nephi | 10:7          | in me that i am christ then have i covenanted with       |
| 2 Nephi | 11:4          | truth of the coming of christ for for this end hath      |
| 2 Nephi | 11:6          | unto my people that save christ should come all men must |


The first time “Christ” is used in the Book of Mormon is in 2nd Nephi 10:3 where Jacob continues his sermon to the people of Nephi and says:

“3 Wherefore, as I said unto you, it must needs be expedient that Christ—for in the last night the angel spake unto me that this should be his name—should come among…”

It makes sense that the word “Christ” never appeared before this instance as it is revealed to Jacob during between days of his sermon. However, Nephi later uses the word Christ later in his teachings in 2 Nephi 33:10-12 which would show that he learned this from his brother Jacob. This interesting insight was found as we examined the data and understood the word occurrences in the Book of Mormon.

2.	Desire in the Book of Mormon
From a quick glance of how ‘desire’ is found throughout the Book of Mormon, it seems that Mormon uses this word the most. This can be seen in the following graph where each column represents a different writer:

![post3plot2.png]({{site.url}}/{{site.baseurl}}/assets/img/post3plot2.png)

This appears that Mormon uses the word ‘desire’ the most, but Mormon is also the author of Words of Mormon, Mosiah, Alma, Helaman, 3 Nephi, 4 Nephi, and most of Mormon. When we normalize the occurrences by amount of text a new pattern emerges:

![post3plot3.png]({{site.url}}/{{site.baseurl}}/assets/img/post3plot3.png)

This new trend that appears shows that Enos used the word ‘desire’ the most frequently in his words. The book of Enos is only 1 chapter long but has 4 references of some form of ‘desire.’ We can use this to better understand what the word ‘desire’ implied back then. Enos only uses this word for the welfare of others in helping them eventually come to Jesus Christ. When his soul wants to come to Christ and feel joy, he uses other words. Desire to Enos meant a want to help others. 

This is interesting because today we use the words desire, want, wish, etc. pretty much interchangeably. We might use the word to show what we need or to express a future need. However, according to Enos ‘desire’ was something completely different. This insight was gained as we looked deeply in the counts of words and understood the data. You too can gain valuable insights from Book of Mormon data!

## Streamlit App:
This Streamlit app (which can be found by clicking on THIS LINK) allows any user to investigate intricacies of the Book of Mormon and visualize them in a meaningful way. It is helpful to better understand how different authors explained concepts and can be used to enhance one’s understanding of the Book of Mormon.

Here is a couple of suggestions to get started with the application:
1.	Go to the Streamlit app
2.	Choose a word from the Book of Mormon and type it into the input on the left sidebar on the screen (tense and case doesn’t matter due to text lowercasing and lemmatization)
3.	Click on the ‘Word’ tab under the title
4.	Scroll and compare the first graph (occurrences in each book) to the second graph (occurrences in each book normalized by length of book)
5.	Once you’re done there, scroll a bit more and click a specific book and look at the corresponding table to see the specific instances with chapter and verse to find it yourself later
6.	You can also jump over to the author tab (under the title) to look how the word is used by different authors

Hopefully this gets you started with a few of the features available! Feel free to explore more and better understand how text is used in the Book of Mormon. If you have a suggestion, we would love your feedback! Feel free to use the suggestion tab (under the title) to fill out a form where we can improve this app in the future!


## Conclusion:

The Book of Mormon is more than just a good religious book and there is much to learn from it. I hope the Streamlit app can help you as you study the Book of Mormon and inspires you to create a Streamlit app of your own! Here is a link to my GitHub repo where you can copy and create new features yourself. 
