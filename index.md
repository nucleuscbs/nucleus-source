---
layout: default
title: The Analytics Bay
videos: true
---
<html>
{% include showcase.html %}
</html><script src="https://kit.fontawesome.com/aef02ef4d3.js" crossorigin="anonymous"></script>
<link rel="stylesheet" href="https://kit-free.fontawesome.com/releases/latest/css/free-v4-font-face.min.css" media="all">
<style>
h3{
  color:#000;
}
</style>
<div class="container">
<hr style="border-top: .1rem solid white;">
<h1>Latest Blogs</h1>
{% for post in site.posts %}

{% if post.featured %}
  <div class="post post-web">


    <h1 class="post-title" style="margin-bottom: 0rem;"><a href="{{ post.url }}" style="font-family: Gotham XNarrow;color:#fff;">{{ post.title }}</a></h1>
    {% if post.description %}<p class="post-description post-description-web">{{ post.description }}<br><a href="{{ post.url }}"><button class="post-button">...Read more</button></a></p>{% endif %}

  </div>
  {% endif %}
{% endfor %}

</div>

<!--  -----------------------------------------------------------------------------------------------------  -->
<div id="what" style="background-color:#fff">
<div class="container" style="padding-top: 50px; 

padding-bottom: 50px; 
text-align: center;">
  <h1 style="font-size: 4rem;color:#000;"> How a Blog is Made? </h1>
  <h2 style="color:#000;">Blogging is something that has become quite common in these days. Still each blogger has something different in his creation. This is where we stand out from the crowd. Our theoretical concepts with their practical appreciation and relatable examples have worked quite well for us by now. How we do it? Ans. You have to learn rocket science first. Not really. Just 3 steps:- 
</h2>

<div class="row first-xs between-sm">
    <div class="col-xs-12 col-sm-4" markdown="1" style="text-align:center">

<div style="font-size: 6rem; color:#000;">1</div>
###  Thorough research 



  </div>

  <div class="col-xs-12 col-sm-4" markdown="1" style="text-align:center">

<div style="font-size: 6rem; color:#000;">2</div>
###  More research 

  </div>

  <div class="col-xs-12 col-sm-4" markdown="1" style="text-align:center">

<div style="font-size: 6rem; color:#000;">3</div>
###  Multiple reviews

  </div>

</div>
</div>

<!--              --------------------------------------------------------------------------------            -->
<div id="what-d" style="background-color:#181a1c">
<div class="container" style="padding-top: 50px; 

padding-bottom: 50px; 
text-align: center;">
  <h1 style="font-size: 4rem"> Why Analytics Bay? </h1>

<div class="row first-xs between-sm">
    <div class="col-xs-12 col-sm-4 col-lg-6" markdown="1" style="text-align:left">
Data Analysis has been gaining immense traction lately with an ever-increasing potential to grow and transform the Business world. Despite of a soaring need of T-shaped employees with well-honed broad skills, existing and emerging workers don’t have the full analytical competencies that the employers need.
We at Nucleus aim to grow and adapt to the dynamic skills landscape and create a synergy effect by exploring data science to further enhance our problem-solving capabilities. Our blog is an initiative to further our moto to bridge the gap between technology and business by expanding our community with our readers.
  </div>
  <div class="col-xs-0 col-sm-0 col-lg-2">
    

  </div>

  <div class="col-xs-12 col-sm-4 col-lg-4">
    
<img src="/logos.png" class="logosimage">
  </div>

</div>
<!-- ------------------------------------------------------------------------------------------------ -->
</div>
</div>


