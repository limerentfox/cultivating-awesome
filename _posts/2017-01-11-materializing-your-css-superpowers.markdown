---
layout: post
title:  Materializing Your CSS SuperPowers
date:   2016-12-20 06:35:12
description:
---
When developing a new Rails application, it is often hard to separate back-end functionality with front-end styling. In essence, what our app will look like is completely separate from what our app will do functionally.

<figure class="app_pic_container">
  <img class="app_pic center" src="{{ site.baseurl }}/img/frontend-vs-backend-web-development.jpg">
</figure>

Out of the box, the default style settings on a Rails application are slightly torturous.

<figure class="app_pic_container">
  <img class="app_pic center" src="{{ site.baseurl }}/img/torture.gif">
</figure>


Wouldn't it be nice if we could add some basic styling to our entire app without having to suddenly become masters at CSS and web design?


... This is where style frameworks like MaterializeCSS come to the rescue!

<figure class="app_pic_container">
  <img class="app_pic center" src="{{ site.baseurl }}/img/materialize-windows.png">
</figure>

MaterializeCSS is a responsive front-end framework based on Google's Material Design that "simplifies life for developers and the users they serve by speeding up development, focusing on user experience, and being easy to work with."

<figure class="app_pic_container">
  <img class="app_pic center" src="{{ site.baseurl }}/img/source.gif">
</figure>

And it is extremely easy to add to an existing Rails application.

#Here's How:

<figure class="app_pic_container">
  <img class="app_pic center" src="{{ site.baseurl }}/img/how.gif">
</figure>


###First
In your Gemfile add the materialize-sass gem:

```
gem 'materialize-sass'
```

###Next
go to your terminal and run:

```
$ bundle install
```

To import all of the base styling (fonts, layouts, and mixins) go into your app directory to your application stylesheet:

```
 app/assets/stylesheets/application.css
```

 and change the ```.css``` file extension to ```.scss```

 (This is change turns the CSS file into a Sass file, which is necessary for using the ```materialiaze-sass``` gem )

 in ```app/assets/stylesheets/application.scss```:

```
 @import "materialize";
```

 ```@import``` is essentially adding all of the styles and superpowers of MaterializeCSS directly into your Rails app.

 Let's see what happens to our login screen.

 Out of the box our login page looked like this:

 <figure class="app_pic_container">
   <img class="app_pic center" src="{{ site.baseurl }}/img/login.png">
 </figure>

 But after adding the gem and importing materialize into our application master stylesheet it now looks like this:

 <figure class="app_pic_container">
   <img class="app_pic center" src="{{ site.baseurl }}/img/login-materialize.png">
 </figure>

 #MAGIC!

 <figure class="app_pic_container">
   <img class="app_pic center" src="{{ site.baseurl }}/img/magic.gif">
 </figure>

 Materialize not only gives you base styling but if you go to the documentation, you can see there are pre-made components you can plug directly into your application and customize to suite your needs:

 <figure class="app_pic_container">
   <img class="app_pic center" src="{{ site.baseurl }}/img/buttons.png">
 </figure>

 For example, let's take a look at adding a nav bar to our application.

 By selecting one of the pre-made html nav bar snippets I can create a partial (```_nav.html.erb```) and save it in a file called shared in my views directory. This will allow me to import my nav bar into the ```application.html.erb``` file in the layouts directory and give all the pages of my application access to the nav bar styling.

 #code example

 Back to the ```_nav.html.erb``` partial, this is what the code looks like:

 <figure class="app_pic_container">
   <img class="app_pic center" src="{{ site.baseurl }}/img/nav-code.png">
 </figure>

 As you can see there are pre-populated classes that make up the materialize styling.

 After customizing the nav our login screen now looks like this:

 <figure class="app_pic_container">
   <img class="app_pic center" src="{{ site.baseurl }}/img/login-nav.png">
 </figure>

 But what if I don't like the colors?

 If you are not happy with the out of the box colors of materialize you can change them by adding this code to your ```application.scss``` file:


```
@import "materialize/components/color";
$primary-color: color("your choice", "variation of that color") !default;
$secondary-color: color("your choice", "variation of that color") !default;
@import 'materialize';
```

I recommend downloading the Sass source files for MaterializeCSS and looking at the ```_colors.scss``` components file to better understand the color naming and variation style conventions.

<figure class="app_pic_container">
  <img class="app_pic center" src="{{ site.baseurl }}/img/colors.png">
</figure>


Conclusion:

MaterializeCSS allows you to add beautiful base styling to your projects so you can focus on finishing features and functionality instead of nitpicking how ugly everything looks.

One could even say, MaterializeCSS gives you magical CSS superpowers.

<figure class="app_pic_container">
  <img class="app_pic center" src="{{ site.baseurl }}/img/cat-power.gif">
</figure>


Diving into the framework further, it gives you CSS superpowers for quickly making your project look great.
