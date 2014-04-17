---
layout: post
title: Adding AJAX Instant Search to Isotope JS
cover: isotope_ajax_search.png
date:   2014-04-17 00:36:00
categories: Web Development, JavaScript, AJAX
published: true
---

## Introducing Isotope JS

[Isotope JS] is an easy-to-implement JavaScript library that allows you to make [Pinterest]-style responsive grid layouts. It allows you to choose among different grid layouts as well as gives you the option to easily implement sorting and filtering of the elements in your grid.

While Isotope's documentation contains some useful information regarding how to filter your elements based on predefined categories, the documentation does not contain anything regarding how to implement search with the library.

I'm going to help you out with that!

## Implementing AJAX instant search

[Demo and Sourcecode]

This tutorial will assume you have basic knowledge of how to implement Isotope and are just needing to extend its functionality and add search to it. That said, it is actually incredibly easy to add AJAX search functionality to Isotope!

First, you'll want to add a search bar anywhere on your page:

{% highlight html %}
<!-- *.html -->
<input type="text" id="search" placeholder="Search here" />
{% endhighlight %}
<br />

Then, you'll want to add the following code in your javascript file, or just include it within your html file between `script` tags:

{% highlight javascript %}
// *.js
$('#search').keyup(function () {
  $search_input = $('#search').val();

  $container.isotope({
    filter: function() {
      var name = $(this).find('.name').text();
      var regex = new RegExp($search_input, 'gi');
      return name.match(regex);
    }
  });
});
{% endhighlight %}
<br />

The jQuery function will get the value of your input with every key press, and call an Isotope filter function. The Isotope filter function finds all of the elements within the $container and gets their names, then using regexp we can return all elements whose names match our search input. That's it. Super clean and super easy!

[isotope js]:http://isotope.metafizzy.co/
[pinterest]:https://www.pinterest.com/
[demo and sourcecode]:http://codepen.io/mjyoung/pen/IqEpw