---
layout: post
title: Example post
cover: cover.jpg
date:   2013-12-09 12:00:00
categories: posts
published: false
---

## Introducing Flex, a Jekyll theme

Flex is a minimalist, responsive theme based on the website, [The Development](http://thedevelopment.co).

## Open Sourced on GitHub

Flex is open sourced on GitHub and is licensed under the [MIT License](http://opensource.org/licenses/MIT). Feel free to contribute to it anytime!

## Code Highlighting

{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}