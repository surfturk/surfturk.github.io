---
layout: post
title:      "Learning to gig with Sinatra"
date:       2020-07-20 16:47:46 -0400
permalink:  learning_to_gig_with_sinatra
---


This week was all about Sinatra and building a web application with it. I used a different approach this week to complete my project and I think it will be how I work moving forward. For one thing, it took me a solid amount of time to understand ActiveRecord. I understand now that it is a database manipulator essentially but it took several youtube videos for me to understand that. I've never really worked with databases before and I can count on my hands the amount of times I used Excel. Needless to say, its a new way of thinking for me. I will be doing mandatory youtube deep dives from now on when I'm confronted with new material. I'm a visual learner so I need all the slides and explanation I can get. 

Setting up the project was pretty painless once you used Corneal and that is truly an amazing gem(pun intended). I still needed to wrap my head around the MVC idea so I did a deep dive on youtube and I found answers. The restaurant analogy was huge and it really got me thinking about everything. It was now time to decide on my project.

I'm a huge music lover so I went with a music centric project and chose a playlist app. I would have two models; a user and a playlist. I set up the associations, schema, db and username/password authentication. From there, it got a bit murky. I really did not understand the get, post and patch aspects of the controller classes so I again had to deep dive. I have to say that Aysan Isayo's videos on youtube are amazing. She just simply breaks down concepts the way I need them broken down. Huge props to her!! 

I finally had the REST methods set up but I ran into another roadblock and that was sessions. After some conversations with a fellow student I understood that a session key was a unique hash keyword that could be associated with a user. So, a current user could carry around a session id and this makes protecting another user's data a whole lot easier. So if I typed out,
def current_user 
 User.find(session[:user_id]) if session[:user_id] 
end

I could use this method anywhere I want in REST methods and the current user would only be able to view or manipulate their data. Wow, big breakthrough.

After testing the functionality of my app, it was time to style it a bit. This is where I ran into a google font problem. I decided to use bootstrap for my project and I had linked bootstrap in the head but my google font link was not working. After two hours of furious google searching I found the issue! The order of placement of style links in the head matters a lot. For example,

head
link href="https://fonts.googleapis.com/css2?family=Lobster&display=swap" rel="stylesheet"
  link href="https://fonts.googleapis.com/css2?family=Do+Hyeon&display=swap" rel="stylesheet"
  link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css" integrity="sha384-9aIt2nRpC12Uk9gS9baDl411NQApFmC26EwAOH8WgZl5MYYxFfc+NcPb1dKGj7Sk" crossorigin="anonymous"
  link rel="stylesheet" href="/css/main.css"
head

is important because I had to place the fonts before bootstrap and my main.css files. After that however, my font was still not working. Another deep dive and I found out that I would have to inline style my font. I guess its an issue with bootstrap and google fonts. Not my ideal choice but maybe I should have just gone with materialize in the first place, hahah oh well. 

After all the font problems I had one final issue and it was cool to learn about. I was having trouble validating params and making sure that empty data wasn't being saved for a playlist. For example, a user could create and save an empty playlist. I didn't want that to be an option so I searched for about an hour and I finally understood what was happening. This is how my code originally looked:

post '/playlists/new' do
         @playlist = current_user.playlists.create(
           playlist_name: params[:playlist_name], 
           genre: params[:genre], 
           artist: params[:artist], 
           song: params[:song])
           @playlist.save
        erb :"/playlists/show" end
      
			 
I looked on the ActiveRecord docs site and I found my answer, sheeebang! If my create method didn't have a shebang after it then it would never validate the data and would simply create whatever was entered or not entered in this case. As soon as I threw that shebang on, everything worked and pumped my fists in the air! That was a great feeling. This was actually a really fun project to work and I learned so much. Cheers!
