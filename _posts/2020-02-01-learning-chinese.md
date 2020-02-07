---
layout: single
title:  "Learning chinese, my experience"
date:   2019-01-26 12:00:00 -0600
author_profile: true
excerpt_separator: "<!--more-->"
header:
  overlay_image: /images/paris.jpg
  overlay_filter: 0.5 # same as adding an opacity of 0.5 to a black background
---


My learning chinese journey has been lasting for years now and I would like to share my adventure (with a tech point of view) as well as give some tips that you might find useful if you are getting started.

<!--more-->

# Flashcards

Learning a new language in general, takes time and energy, and constant practice. Chinese has different origin than my mother tongue (french) and it thus makes it harder to memorize the vocabulary that you will learn. Chinese's logic and etymology are completely different than latin based languages.
I found myself struggling remembering some words that had no single similarities with the translations to the languages I know, which can be discouraging.

I read a lot of articles about how to be more efficient at learning a language as it can be really time consuming. You can either spend more time on it or be more efficient at it (or both)!

One thing i found many times recommended on the internet were flashcards. Flashcards are a simple method, a front and back card. Front is whatever you are trying to memorize, it could be a word, sentence but could also be a sound, an image etc. On the back is the solution, it's what should come to your mind when you see the front.

Once you flip the card you get to see the solution and grade your result. You are giving the grade yourself, it is no point to cheat, you'd better be honest if you wanna improve! The app i am using has 4 grades _fail, hard, good_ and _easy_.

Here is an example, from the app _AnkiApp_.

| Front         | Back           |
|:-------------:|:-------------:|
| ![front]({{ '/images/flashcard_front.png' | relative_url }}) | ![back]({{ '/images/flashcard_back.png' | relative_url }})  |

Once you chose a grade it goes to the next card and so on until you reviewed N cards, N being a setting that you can change, usually from 10 to 20.
The good thing about it is that you'll tend to be given the cards that you did not memorize, i.e. the cards you gave _fail_ or _hard_. This way you won't spend too much time on the cards you know but mainly on the ones you don't, even if sometimes it will give you cards you graded _easy_ just to make sure you didn't forget it!

There are plenty of flashcards app you can use online, most famous being [**Anki**](https://apps.ankiweb.net) and [**AnkiApp**](https://www.ankiapp.com).
They both have a mobile and desktop version with account management that lets you revise your own decks on both platforms.
I personally prefer AnkiApp as it got a free version on MacOS, which is not the case for Anki, it's about 25 bucks.

Great thing about both those apps is that they usually have a nice "marketplace", with a lot of people creating and sharing decks that you can download and instantly use on your device! For example, for HSK (official chinese language exam), you can find plenty of cards for the vocabulary (official vocabulary list).

However as soon as you want to create your own cards, it is getting quite tricky as writing them down through your phone or even through the web/desktop version can be time consuming. The great thing about making your own flashcards is that first, you choose the content you want to revise, if there is a word you want to memorize just make the flashcard and you'll naturally learn it in the next days with the new cards.


That's why I created a small set of simple scripts that allow me to create flashcards automatically from a list of words that I want to memorize. In my case, learning chinese, what I needed was a way to take a list of chinese characters as input (also called hanzi), and generate all the flashcards so that I can directly review them on my phone.

In the next chapter I'll quickly describe the script I developed. You can later find available flashcards that I created below.

## Flashcards generation

I found that great python library called pinyin [**pinyin**](http://pinyin.lxyu.net) that gives you, from a given hanzi (你好): the translation (hello) and the pinyin (nĭ hăo) (phonetic translation in latin alphabet and keyboard input method).

Once I get that I can simply write them to a tsv format (tabs separated values) that can thus be read by most Anki clients, including the two I mentioned earlier. I also added tags management, which lets you create some tags for each word so that you can later filter them by tags, which can be useful for example if you wanna differentiate verbs from noun, or differentiate the ones you got in textbook from the ones you found online etc.

If you are interested to use it to create your own or to reuse it for something else feel free. Functions are generic and can be use for anything, not only hanzi.

Check out the github repository [_hanzi to anki_](https://github.com/RafaelCartenet/hanzi_to_anki)

## Available flashcards

I have made available my flashcards so that everyone can use them.
You can download the raw files and import them on the web or desktop applications.

You can find them all on github, [_hsk flashcards_](https://github.com/RafaelCartenet/hsk_flashcards)

I created flashcards especially for the books **HSK Standard Course** which is the book used in many chinese schools including mine.

Each HSK level has its own book (or more) and is divided in lessons. What I particularly like is to be able to revise only the vocabulary from the last lesson you had or all the lessons you attended till now, to be always up to date. If you just start preparing HSK4 and you get all the 600 flashcards at the same time to revise, you're gonna have a hard time. Instead, having only the words you learned during the previous course/lesson will make you feel confident.


I created two tags,

1. _textbook_ for all the words that are introduced from the textbook. All the cards without that tag are words I did not know during that lesson and that I added. They might be from HSK3 or less or totally different words.
2. _LESSON.SUBLESSON_ in order to classify cards according to the lessons we had. Each lesson is covered in three parts (sub lessons)

You will find below the link to the different flashcards sets.

### HSK 3

| Lesson      | Raw file                                                                                                                                      | AnkiWeb link
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------|---|
| All lessons | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/all_lessons.tsv" download>Raw file</a> | / |
| Lesson 1    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_1.tsv" download>Raw file</a>   | / |
| Lesson 2    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_2.tsv" download>Raw file</a>   | / |
| Lesson 3    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_3.tsv" download>Raw file</a>   | / |
| Lesson 4    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_4.tsv" download>Raw file</a>   | / |
| Lesson 5    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_5.tsv" download>Raw file</a>   | / |
| Lesson 6    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_6.tsv" download>Raw file</a>   | / |
| Lesson 7    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_7.tsv" download>Raw file</a>   | / |
| Lesson 8    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_8.tsv" download>Raw file</a>   | / |
| Lesson 9    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_9.tsv" download>Raw file</a>   | / |
| Lesson 10   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_10.tsv" download>Raw file</a>  | / |
| Lesson 11   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_11.tsv" download>Raw file</a>  | / |
| Lesson 12   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_12.tsv" download>Raw file</a>  | / |
| Lesson 13   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_13.tsv" download>Raw file</a>  | / |
| Lesson 14   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_14.tsv" download>Raw file</a>  | / |
| Lesson 15   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_15.tsv" download>Raw file</a>  | / |
| Lesson 16   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_16.tsv" download>Raw file</a>  | / |
| Lesson 17   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_17.tsv" download>Raw file</a>  | / |
| Lesson 18   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_18.tsv" download>Raw file</a>  | / |
| Lesson 19   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_19.tsv" download>Raw file</a>  | / |
| Lesson 20   | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk3/lesson_20.tsv" download>Raw file</a>  | / |

### HSK 4

On going

| Lesson      | Raw file                                                                                                                                      | AnkiWeb link
|-------------|-----------------------------------------------------------------------------------------------------------------------------------------------|---|
| Lesson 1    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk4/lesson_1.tsv" download>Raw file</a>   | / |
| Lesson 2    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk4/lesson_2.tsv" download>Raw file</a>   | / |
| Lesson 3    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk4/lesson_3.tsv" download>Raw file</a>   | / |
| Lesson 4    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk4/lesson_4.tsv" download>Raw file</a>   | / |
| Lesson 5    | <a href="https://raw.githubusercontent.com/RafaelCartenet/hsk_flashcards/master/output_flashcards/hsk4/lesson_5.tsv" download>Raw file</a>   | / |
