---
layout: post
title:      "A simple tale of complexity"
date:       2020-08-24 03:33:10 +0000
permalink:  a_simple_tale_of_complexity
---


Its Rails project and wow, what a doozy. The MVC framework was pretty straight forward for me this time after moving through Sinatra but it still had its pit falls. I think the speed with which you can create a Rails project actually lends to its complexity. After only a few minutes, you're dealing with several models, controllers and views. It can get pretty hairy after that.

I struggled a bit on the omniauth set up. I decided to try my hand at the Google authorization and that was a mistake. I ended up decided against Google when they wanted me to submit my app for a 4 to 6 week review, yeah I'm a student and that is not gonna work. I moved on to the GitHub authorization and that was a lot smoother. I was able to use two websites to set up and they were pretty straight forward. 

I'm still getting the hang of refactoring with partials. I understand that a line like this : <%= render partial: "model_form", locals: {car: car}%>, means its going to render a _model_form partial and its going to utilize a local called car that is in a sense block element used for iteration. 

I found the devise helper method current_user to be amazing. It took me a bit to understand how to use it but once I did I was up and running. A line like this : @car = current_user.cars.find(params[:id]) would allow me to search a car id that is only associated with the current user that is logged in. I could then place that in a private method and use it anywhere in the controller. It makes authorization a lot easier Although after Sinatra, it it cool to know what is going on under the hood.

It took me a bit to understand how the application layout worked but I got the hang of it. The application layout is essentially the html framework for the entire website. The base stays the same even if you are rendering different data to the page. It possible to have different layouts for each page but I decided against that. I wanted the application to be uniform through out.

cheers,
Berkley


