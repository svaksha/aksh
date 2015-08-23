# Nirbhaya

+ [1. NIRBHAYA PROPOSAL](#1-nirbhaya-proposal)
   + [Abstract](#abstract)
+ [2. USECASE](#2-usecase)
   + [Description](#description)
   + [Implementation](#implementation)
        + [Storage](#storage)
   + [Challenges](#challenges)

----

# 1. NIRBHAYA PROPOSAL

Some years ago I had written a blog post about a [HotKey button](http://svaksha.com/post/2009/Cell-help) application that would ping your designated contact list when you are in danger of being assaulted and help track down your location via your cell-phone. However, I soon realised that this idea was ahead of its time because without the support infrastructure - prompt police response and co-operation, lack of social awareness, sensitivity and gender awareness to crime among Indians, lack of prompt medical aid, etc.. this would not work. The lack of ground level support that provides women backing when she needs help was crucial, else the HotKey application would only result in false alarms that caused the woman's family and friends more cause for worry about her safety, which can also have the negative effect of putting restrictions on her movement. Besides, smartphones were not a popular trend as they are today (in 2015) thanks to cheaper cellphones by different manufacturers. 

In 2011, the Thomson Reuters Foundation ranked [India as the fourth most dangerous country in the world for Women](http://indiatoday.intoday.in/story/india-is-fourth-most-dangerous-place-in-the-world-for-women-poll/1/141639.html) in terms of [six risk factors](http://www.theguardian.com/world/2011/jun/15/worst-place-women-afghanistan-india) including: health, discrimination and lack of access to economic resources, harmful cultural and religious practices, (non-)sexual violence, human trafficking and conflict-related violence. In 2012, after the violent Nirbhaya attack in NewDelhi, the Indian government introduced the [Gazette notification ammendment dated 03-Feb-2013](http://lawmin.nic.in/ld/ord_criminal_law.pdf), now popularly known as the Nirbhaya Act - The [Press Information Bureau](http://pib.nic.in/newsite/erelease.aspx?relid=91979) also has a release of the entire gazette notification. 

Today, there is more awareness about womens safety, the police claims to be responsive, more women are speaking up and rejecting the stigma associated with coming forward to [register cases under the Nirbhaya Act](http://www.thehindu.com/todays-paper/tp-national/tp-andhrapradesh/407-cases-registered-under-nirbhaya-act-in-krishna/article6730238.ece). However, the ground reality has not changed much and many Indian women are still unsafe and we hear many assault incidents being hilighted by the media on a regular basis. Some of the highly violent cases that get media attention are able to get the FIR (First Information Report) registered promptly due to public pressure, but what happens to the other low-profile cases? 

## Abstract

Since the Nirbhaya attack, various websites and forums have comments from defensive Indian men that ranges from claiming that India has the lowest sexual assault statistics as compared to USA and other developing nations, to the logical fallacy that the media focus on gender-related crimes is an international conspiracy to tarnish our great Indian culture, and the worst fallacy was some commenters accusing Nirbhaya of self-inflicting her injuries inorder to get famous. 

Statistics can lie when you dont consider the big picture and fail to account for some data patterns because the law is not the same in each country - Unlike other developed nations, in India the police treats "stalking", "eve-teasing" and other acts of aggression against women as a non-cognisable offence and sometimes eve-teasing is described as a “public nuisance” and the gravity of the crime is reduced to a petty non-cognisable offence under the IPC (Indian Penal Code) Act by [pitying the perpetrators of the sexual harrasment crime](http://bangalore.citizenmatters.in/articles/pitying-the-perpetrators-of-sexual-harassment-right-or-wrong).

This crucial statistical data difference has another angle - the FIR or First Information Report. When the critique of __sexual assaults in developed nations Vs. India__ rests on the use of government statistical data let us be wary of two pitfalls: First, statistics when used without context or accounting for the difference in laws can be misleading and second, the greater danger is that numbers have become a way to rationalise and underplay contemporary social failures in India. Social activists will tell you that when there is pressure on the police to keep crime numbers low, the police departments who are already under-staffed and heavily over-worked, will resort to the easiest method - __not registering an FIR__!

An FIR is one of the crucial links in the legal prosecution of an assault case and if the implementation fails at this level, there is less hope of justice for a woman trying to get the legal system to implement the laws that aim to provide gender justice, hence resulting in low statistics. This project aims to use Twitter to track people using the hashtag `#NirbhayaAct`, `#Nirbhaya` and statistically track if their case was registered or not by the police by asking the victims to come forward and provide the data. Initially, in the pilot stage, we will limit the tracking to Bengaluru city where the police is very tech savvy, uses [twitter](http://twitter.com/cpblr) and [FB](https://www.facebook.com/blrcitypolice) and has a team of officers that handle the IT aspect of their online presence.

---- 

# 2. USECASE

## Description

The goal is to bring in accountability and use statistics to hilight the number of cases that slip under the radar. When a woman (person) approaches the police to register an FIR, does the police treat each case with seriousness and sensitivity? Do they actually __register the FIR report under the Nirbhaya Act__ or try to dissuade her and water down the case? Every assault or harrasment case does not have to be a horrifically violent act that results in a woman's (persons) death for the police to take action. There will not be a change in the mindset that there are no consequences for stalking or assaulting women in India unless other forms of harassment and assault get the same level of accountability and justice especially because all cases may not come under the media spotlight. 

This project aims to use social media, like the Twitter API, to track the following information :

+ People can tweet if not taken seriously or pressured into not filing an FIR complaint by using the hashtag `#NirbhayaAct`, `#Nirbhaya`.
+ Statistically track if her FIR was registered or not by the police under the Nirbhaya Act and provide the data to the police on a regular basis. 
+ Contact the Bengaluru police to gather statistics from their IT arm and create visualizations for those statistics too.
+ Create visualizations for all the statistics gathered.
+ Encourage citizens to come forward and tweet if the police refuses or delays in filing an FIR.
+ Tweet if the police refuse to provide an ATR (Action Taken Report) within a reasonable time-frame.

## Implementation

It is proposed to use Python for programming the initial aspect of gathering data from Twitter, thereafter use Julia for the analysis of data stored in HDF5 files.

### Technical Stack

+ Python-3.x
+ Julia (git master)
+ DB (array based storage)
   + HDF5
   + https://github.com/h5io/h5io
+ NLP
   + http://NLTK.org
+ Github 
+ Twitter API
   + Credentials for Twitter API - create a new application at: https://dev.twitter.com/apps
   + https://dev.twitter.com/overview/documentation
   + https://dev.twitter.com/rest/reference/get/search/tweets
   + CLI integration : https://github.com/sixohsix/twitter
        + https://github.com/sferik/t
   + App by Meg Ford {{ReadOnly}} : https://github.com/MegFord/twitter_app/
   + https://julia67.github.io/tinkering-with-twitters-api/
+ Django / Flask / JS - {{ToDecide}}
   + https://github.com/ashleygwilliams/ashleygwilliams.github.io
+ Heroku

#### DB Storage
+ Array based storage using HDF5 and JLD
   * To use HDF5 (with JLD, which has been split recently), use Pkg.add("JLD") and in future, to use it say "using JLD" rather than "using HDF5, JLD."


## Challenges
How to ...
+ Ensure a tweeters privacy and the victims privacy? 
+ Get police support and buy-in for the above?
+ Ensure there are no repercursions (doxxing, stalking) for speaking up?

