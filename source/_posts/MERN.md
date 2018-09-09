---
title: MERN Stack - Part I 
date: 2018-09-07 21:36:57
tags:
---


<br>
![MERN Stack](https://lh3.googleusercontent.com/b2k7lununvYVlZ1vDVGHOv2dfqVWo6FjYMim4XTX9poT_wEJw2pkI3hI7bhcIflFQVknfkdwlqqmuNuzUknNu_MwOJ1v-uy7yKc2vzK3BBLj3xGxRLZIutoFCKmhLeavCFJJ3vBcCg=w2400 "Logo Title Text 1")

<p style='line-height: 26px; font-size: 18px;'>I know this blog's motto is 'everything Node'. And I stand by that -it's a fine motto in fact. But I think it's about time to think outside the box! What this means for us is that we are going to dive into a full-fledged MERN stack application, complete with an Express framework, JSON Web token and a MongoDB database via mLab! Are you excited? I sure am! </p>

<p style='line-height: 26px; font-size: 18px;'>In sticking with the standard practice of <em>tldr;</em>, I have decided to break up this post into a couple of different sections. How many sections? 
Well, that is a good question as there are a lot of moving parts to a MERN stack application. 
But for now, we'll get started with getting set up with Mongo DB via mLab.  
</p>

![MLab](https://lh3.googleusercontent.com/WHIGlct0tnqcwdq_nbE4DKIa7loZQ8CMkdMA8kb9bfWkzvg8bcdzrlIaBC-5hQmaffCbLqqN6mqXvgiFiqLZvAgGNafTFVdCo-hc2hpI0OvKviP640cHJzq8QnZoook3QV3Am_ujAQ=w2400 "Logo Title Text 1")

<h2>Getting Started with MongoDB and mLab</h2>

<p style='line-height: 26px; font-size: 18px;'>So what exactly is mLab? In the simplist of terms, mLab is a remote MongoDB database or cloud database. Your database in mLab is easy to set up (you don't have to worry about configuring MongoDB on different platforms) and it provides a place for our database to live. For our purposes the free sandbox option will work just fine, however, if you were to crete a production application, you may want to check out a pay tier. <p> 
<hr>
<p style='line-height: 26px; font-size: 18px;'>So let's get to it. Click on the following link to set up an account. [mLab Website](https://mlab.com/ "mLab Website").

After your account is set up, crete a new deployment by selecting the "create new" button. 

From the next screen we can choose our cloud provider (Amazon Web Services) and our plan type (Sandbox --Free).

![Sandbox](https://lh3.googleusercontent.com/ai9kwzacX-gNe3owD1nN3_2TIXVvsT-HMJqEDaJ254Ez5eI5WILyd_TrPuP7H5dJO1repd5LgfLyb7jdCDDUDtym73crvru7vuxS6YHZJSSfK4WJhbO9Ng4hdvS7_l08XvW8qVfB1A=w2400 "Logo Title Text 1")

You will have to choose an AWS Region. I choose US East (Virginia) (us-east-1) and you can select the most appropriate region for yourself. 

Once you select your region and hit the continue button you are now ready to name your database. You can call it whatever you'd like. 

Once you submit your order you will now have a MongoDB URI.

![URI](https://lh3.googleusercontent.com/wslJZXs9ktkI95OL_-U4qnVQxGxB1gcnX8eMuTlwsGYHxrvYCo6k_8Gpsq0U9HQ0Scu3hW1zqdZN9cGwXReojlk-vyqjwIyWsviSYS5Gdw7KrB-TATUuy4j5qBVojU_xCeNbmExJHw=w2400 "Logo Title Text 1")

</p>




