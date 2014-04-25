---
layout: post
title: 'Code interview challenge: ROT13'
cover: 13.jpg
date:   2014-04-24 06:45:00
categories: Ruby, Interviews
published: true
---

## Coding interview challenge

Recently I was asked to write a method that takes a string, and then encrypts or decrypts it using the [ROT13] cipher technique. The challenge was to allow encryption and decryption based on any number passed in with the string as arguments.

For simplicity's sake, let's just say that I'm only concerned with ROT-13, and not ROT-5, ROT-10, etc.

There may be some better ways to do it (I'm quite certain there are), but this is what I came up with:

{% highlight ruby %}
ALPHABET=%w{a b c d e f g h i j k l m n o p q r s t u v w x y z}

def rot13(string)
  string_array = string.split('')
  string_array.map! do |char|
    if /[A-Za-z]/ =~ char
      new_index = ALPHABET.index(char.downcase) + 13
      new_index = new_index - ALPHABET.length if new_index > ALPHABET.length-1
      /[a-z]/ =~ char ? char = ALPHABET[new_index] : char = ALPHABET[new_index].upcase
    else
      char
    end
  end
  string_array.join('')
end
{% endhighlight %}

## If you really want to wow your interviewer...

Now if you really want to go the extra mile and show your interviewer an even more secure ciper with many fewer lines of code, show them the code for ROT-26:

{% highlight ruby %}
def rot26(string)
  string
end
{% endhighlight %}

[rot13]:http://en.wikipedia.org/wiki/ROT13