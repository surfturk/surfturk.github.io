---
layout: post
title:      "Waves of code"
date:       2020-06-19 11:12:54 -0400
permalink:  waves_of_code
---


This week was all about my first project at Flatiron and honestly, it was a great time! The project idea came pretty quickly to me and I just ran with it from there. I lived overseas for over 5 year in Israel and during that time, I learned to surf. It was a tremendous activity to be involved with and it consumed my entire life. At one point, I though I might go the amateur competition route but life had other plans. 

Years later, here I am making a CLI project that centers around finding beach spots. I first went with a global api that had all types of wave and weather forecasts for beaches across the entire world. I found out rather quickly that that api was a little beyond my expertise, the amount of data from off shore winds was staggering. Plus, they would only allow me to use two beach spots! I finally found the California Coastal Commision api website. Wow, this was everything I had been looking for. It was open source, free and featured data for more than 1500 beaches across California. It was time to code!

I first started with the framework of the CLI, how would it flow? It would prompt the user, get input and then retrieve the beach data. My main concern at first was to simply connect to the api and retrieve some type of data. Several videos and tutorials later, I had success! However, how could I possibly organize 1500 beaches? Use their counties!!! I decided to write a loop that would print out all counties available in California, then I would be able to drill down to all beaches associated with a given county. This was the hard part of this project. It required me to reach out to several people to understand how OO programming and loops would work with api data. I then had to create multiple method and call upon those methods in other methods, whoa! 

Now that my objects and methods were communicating, it was time to trick out the user experience. I first added some personality to the on-screen text. This was a surfer app after all. I then went about trying to add some graphics to the intro and I went down a monsterous rabbit hole. Should I do color? Should I attempt animation? Should I try and add an entire photo realistic surfer to the intro? Ok, take it easy. its your first project. I finally decided on a nice, big logo for the intro and settled on that. 

Now it was time to boot this project up and run through it. Oh wow, it works. I built my first ever application from scratch. I was actually super pumped the first time I typed in commands and was playing around in the app. This is only the beginning and I have so much more to learn and be excited about! 

## Technical code breakdown:
I had a few technical hurdles that were fun to get through. I had a class method in my beach class that used an each 
iteration to loop through an array and based on a conditional, make a new array. After I received some guidance, 
I found out about Ruby's built-in select method. This method allowed me to select the elements I needed and create a
new array from those elements. So, my method that contained 4 to 5 lines of code went to 2 lines of code, pretty neat.

Another aspect of coding that I realized through this project was how the flow of a method works. If return is written as the last line of code, then Ruby will return whatever the last line of code is. For example, if I write a method that has a variable set as 1 + 3, I call the variable and then I call return 5, this will return 5 no matter what. However, if we write a method that contains a variable set as 1 + 3 and then I call that variable as the last line, I'll get 4.
This seems basic now but it can come back to haunt you in larger applications.


Berkley


