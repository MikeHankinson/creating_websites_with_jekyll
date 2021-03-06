---
#layout: dark
layout: page
title: About
example: This is an example value.
---


#Use Liquid language to style the sentence below  
This page describes the amazing {{ site.title }} by {{ site.author.name }}.
{{ page.example }}


#Use Liquid language to insert big-cat.html from the _Include Folder 
{% include big-cat.html %}



## About About Pages

The About page is a common convention found on websites.
It is your opportunity to let us know all the details "about" your project:

- focus and topic area
- people involved
- code and projects used

# Table Insert from https://tablesgenerator.com/markdown_tables


|         	| Test Accuracy 	| False negative<br>out of 1,300 	| False Positive<br>out of 1,300 	|
|---------	|---------------	|--------------------------------	|--------------------------------	|
| Base    	|      0.97     	|               41               	|               28               	|
| Model 1 	|      0.95     	|               65               	|               61               	|
| Model 2 	|      0.98     	|               22               	|               33               	|
| Model 3 	|      0.98     	|               23               	|               25               	|
| Model 4 	|      0.95     	|               65               	|               54               	|
| Model 5 	|      0.92     	|               47               	|               154              	|
| Model 6 	|      0.94     	|               83               	|               78               	|
| Model 7 	|      0.90     	|               37               	|               221              	|


# Table Using Advanced Liquid (For Loop)
## List of Animals

{% for animal in site.data.animal %}
- The {{ animal.name }} is a {{ animal.size }} animal.
{% endfor %}

## Large Animals are Better (If and For Loop)

{% for animal in site.data.animal %}
{% if animal.size == "large" %}- <strong style="color: {{ animal.color }};">{{ animal.name }}</strong>
{% else %}- <small>{{ animal.name }}</small>
{% endif %}
{% endfor %}

## List of Small Animals (Where)

{% assign small_animals = site.data.animal | where: "size", "small" %}
{% for animal in small_animals %}
- {{ animal.name | upcase }}
{% endfor %}
