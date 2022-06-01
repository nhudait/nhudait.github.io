---
weight: 4
title: "Software Developer | Girl Effect"
description: "Building conversational AI products to help girls in developing countries"
nav_heading: ""
thumbnail: "girleffect.png"
work_short_title: "Software Developer"
case_title: "Software Developer"
case_subtitle: "Girl Effect"
case_description: "Building conversational AI products using Natural Language Understanding to help girls in developing countries"
case_feature_img: ""
case_summary: "Building conversational AI products using Natural Language Understanding to help girls in developing countries"
tool: ["Python", "Pandas", "NLTK", "Tensorflow", "Keras", "PyTorch"]
area: ["Natural Language Processing", "Natural Language Understanding", "Software Development"]
methods: ["Contextual Inquiry", "Google Analytics", "Web Development", "User Interface Design"]
testimonial:
testimonial_photo: "nate.jpg"
testimonial_author: "Nathaniel Benedicto"
testimonial_subtitle: "Associate Vice President for Events, Ateneo Junior Marketing Association"
date: 2017-10-15T03:29:08-07:00
draft: false
---

# Overview

![](//nehahudait.com/girleffect/img/nikegirleffect.jpg)

[Girl Effect](https://girleffect.org) is a nonprofit organization dedicated to empowering and educating girls across the world, especially in developing countries, through Artificial Intelligence. I worked as a Software Developer for Girl Effect on their conversational AI products aimed to answer questions from girls. More specifically, I worked on Big Sis and Chhaa Jaa, Girl Effect's flagship products in the United States and India.

My work was primarily centered around improving the chatbot's functionality in understanding what the intent of the girl's message is and delivering tailored results. Through this, I primarily employed Natural Language Understanding techniques to improve the overall quality of responses for the girls.

## Springster
Springster is one of Girl Effect's mobile platforms which digitally connects marginalized and vulnerable girlsot online content designed to equip them with the knowledge, confidence, and connections they need to navigate the complex choices of adolescence. Springster publishes content co-created with and designed for girls, to build knowledge, inspire, and support girls to create positive change in their lives.

## Big Sis and Chhaa Jaa

Big Sis and Chhaa Jaa are chatbot that uses machine learning to provide girls with personalized answers to their questions on love, relationships, and sexual health, enabling girls to seek advice and find answers 24/7. Over 12.7 million unique users use these products yearly. As a result, it is important to interate upon the chatbot design to ensure that the content is factual and questions are being accurately interpreted and answered.

# The Problem
Currently, within the two chatbots, girls are able to ask questions about all things love, sex, and relationships. However, due to slang, mispellings, inaccurate translations, or other factors that can contribute to an incorrect dictionary, the chatbot has difficulty delivering catered responses.

Big Sis currently analyzes all of the text that is sent on the chatbot, identifies if there are any key words, and outputs a set of choices for the girl to select from. Chhaa Jaa adds this translation feature prior to looking at its dictionary. However this isn't necessarily sustainable and cannot deliver accurate results. For example, if a girl typed in "bf", the chatbot would not be able to recognize the keyword as "boyfriend."

# Workflow
To approach this, I created a machine learning model to create a mapping between some of the messages that different girls submitted to the chatbot to generate relevant results. Currently,
if a girl has a specific question about a certain topic, they are able to submit that subject or ask a question to the chatbot.

The chatbot will then query it’s dictionary to find relevant questions to display based on the topic of interest. However, if the topic is misspelled or slang is used, the chatbot will not be able to understand the word and as a result, will not be able to show relevant results.

I created a model to create a mapping between some of the messages to a generated keyword. In this case, this would be a topic relating to questions that girls may have. For example, if a girl typed in “I love my boyfriend” or “I love my bf,” this would map to the topic “boyfriend.” We used a Long Short Term Memory (LSTM) model to do this.

To create a proof of concept, I used the labels that Girl Effect currently uses for their
chatbot. Then, I generated inputs into the LSTM model. I created a list of sequences using
the entries and created a mapping from the index to character and character to the index for the
current data that I were looking at. I also created a mapping from the index to the topic
(“boyfriend”, “love”, etc.) and a mapping from the phrase to index. I finally utilized this mapping to make the LSTM input, which is the number of sequences x the number of elements
in the sequence x the number of characters in the alphabet. We then trained the LSTM model on
these inputs and made a streamlined way to predict what topic some input was related to after
training. Now, if a girl is able to enter the phrase “I love my bf” the chatbot will map this phrase to “love” or “boyfriend” and display the suggested topics.


# Takeaways
## Translation is Tricky
Translation and NLP remains a huge issue when using NLP for text in different languages. Because of the vast complexity of different languages, when doing direct translation, often times there is an associated loss. For example, idioms, irony, satire, slang etc. could be lost when doing direct translations from one language to another. As a result, using NLP techniques becomes much tricker because we want to minimize loss.

## Verification is Difficult
Because we are doing NLP on different languages, verifying our results becomes much more complex if we don't speak the language. I was fortunate enough to learn Hindi growing up, so I could quickly sanity check the results that I was getting from Chaa Jaa. However, my teammates really struggled with verifying results iteratively because they weren't as well versed in Hindi or the other languages that we were working with. When working with different languages, it's helpful to have native experts who can share insight on nuances and other complexities of languages.
