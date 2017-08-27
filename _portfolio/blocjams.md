---
layout: post
title: BlocJams
feature-img: "img/bloc_jams_bg.jpg"
thumbnail-path: "{{ site.baseurl }}/img/bjam-pic.png"
short-description: BlocJams is an awesome music player!

---

                                        BlocJams

BlocJams is a music player that uses HTML, CSS, Javascript, jQuery and Angular to create a user interface that allows the user to play music.

![]({{ site.baseurl }}/img/bjam-pic.png)

I was assigned the BlocJams music player project and set to work on it to expand my knowledge of practical web design.  I was responsible for following directions and encouraged to try my own hand at implementing features to make BlocJams a success.  


In creating BlocJams I was tasked with putting together a functional music player that had an enjoyable user interface and would be usable across multiple device's.  This was new territory for me as I had never made something that was responsive to screen sizes and used this much Javascript.  Using Javascript to make HTML templates was something I had never done so when I saw code like :

{% highlight javascript %}

var buildCollectionItemTemplate = function() {
  var template =
    '<div class="collection-album-container column fourth">'
  + '  <img src="assets/images/album_covers/01.png"/>'
  + '  <div class="collection-album-info caption">'
  + '    <p>'
  + '      <a class="album-name" href="album.html"> The Colors </a>'
  + '      <br/>'
  + '      <a href="album.html"> Pablo Picasso </a>'
  + '      <br/>'
  + '      X songs'
  + '      <br/>'
  + '    </p>'
  + '  </div>'
  + '</div>'
  ;
  return $(template);
};

{% endhighlight %}
It was exciting to see how much power could be wielded with Javascript.   

After every line of code added to BlocJams a series of test was needed to make sure it was all working as intended.I spent a lot of time in the browser console to make sure that each new line added didn't give me errors that couldn't be explained.  I also learned that not all errors are bad and if an error doesn't effect the user experience it may be ok to leave it in.    

I learned a great deal about how to organize my code and to make sure to use documentation while writing it.  I've found out a lot about knowing my limits and when to take a break from projects.  If I could go back and do it over Id want to take more time examining how the code I was writing worked and know when to push forward or take a break.  One of the best part of this project in my opinion was learning about myself and how I work on projects.

![]({{ site.baseurl }}/img/thumbs-up.jpg)
