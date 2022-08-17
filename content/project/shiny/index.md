---
title: "Shiny for Python"
subtitle: "R Shiny is Now Available in Python"
excerpt: "This theme has a form-to-email feature built in, thanks to the simple Formspree integration. All you need to activate the form is a valid recipient email address saved in the form front matter."
date: 2022-08-15
author: "Adam Bozman"
draft: false
tags:
  - hugo-site
categories:
  - Theme Features
  - R
  - package
layout: single
links:
- icon: door-open
  icon_pack: fas
  name: website
  url: https://bakeoff.netlify.com/
- icon: github
  icon_pack: fab
  name: code
  url: https://github.com/apreshill/bakeoff
---

![Twitter Sentimant Analyzer](twitter_logo.png)

---

## Building a Web Framework

As a finance PhD, I’m often irrationally irritated by my restriction in publishable coding languages.  In my experience, SAS and Python are the most commonly accepted for any sort of statistical or technical analysis in the field.  While I’ve done my best to adopt SAS, it still feels like nothing more than a remnant of generations past – something that while not quite as clunky as SPSS, still offers little adaptability and customization.  I do understand the need for reproducibility, which is why I believe that any journal calculations should be done in an open-source, object-oriented language – something available to the masses.  

While I’ve been restricted to Python (and some SAS) for most of my academic work, I regularly dabble in other scripting languages that have more breadth and personalization to them.  For example, this website is built using primarily R and Hugo.  For this reason, I was very excited to see earlier this month the introduction of _Shiny for Python_, an adaptation to Shiny in R.  


## Shiny for Python | Twitter Sentiment

Shiny was one of the first low-code web frameworks for either R or Python, and Python still (in my opinion) doesn’t have the great UI of something like Shiny or Dash in R.  This makes it challenging to share projects, collaborate with peers, or demonstrate coding applications to students.  

This "Twitter Sentiment Analyzer" project is an initial application of Shiny in Python – something only available for the last few weeks.  This app uses **snscrape** to combine tweets in real time and calculate the sentiment surrounding keywords using _NLP_ and _Sklearn_.  While this is a relatively simple example, it does have applications in my future research.  It also utilizes snscrape (a library currently exclusive to python) and Shiny (formerly exclusive to R).  Keep in mind, Shiny for Python is currently in Alpha, and changes to their APIs will likely occur.  If this application has any issues when you try to access it, I am likely just lazy in updating APIs – all the codes should still be reproducible though.    

## RStudio Rebranded

This endeavor by RStudio seems to be the next step in their coming October rebrand.  RStudio will be rebranded as [Posit](https://www.rstudio.com/blog/rstudio-is-becoming-posit/), an extension of their current IDE to what they call “A Single Home for R & Python”.  This rebrand is part of a broader expansion that appears to be happening.  Recently, RStudio announced [Quarto](https://www.rstudio.com/blog/announcing-quarto-a-new-scientific-and-technical-publishing-system/), a “scientific and technical publishing system” very similar to RMarkdown.  They’re also extending the platform to Julia and other languages as they transform from the default home for R to a completer and more purposeful IDE for statisticians and developers.  

> _I do have additional thoughts on the blend of RStudio and Python [here](/blog/2022-08-15-posit/).  For me, and I imagine for anyone frequently working with data, this is a very interesting time._
