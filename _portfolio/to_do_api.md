---
layout: post
title: To Do API
feature-img: "img/to_do_api.png"
thumbnail-path: "/img/neo.jpg"
short-description: a to do list api made with Ruby on Rails and RESTful architecture.

---

                            To Do API

The To Do API I have created with Ruby on Rails uses RESTful architecture to deliver information as JSON so the information can be manipulated in the DOM.

This project really helped me understand some of the fundamentals about RESTful conventions and the way the internet works as a whole.  I think sometimes we get so involved in the power of frameworks and libraries that it's easy to forget about the fundamentals.  Whats a GET request?  Whats a URL?  Whats HTTP?  As someone new to Web Development, these things got glossed over for me until this project.

Using serializers was a new concept and I found it enjoyable and easy to implicate.  Just add the GEM:

{% highlight ruby %}

gem 'active_model_serializers', '~> 0.10.0'

{% endhighlight %}

You can use it to save time with a simple :

{% highlight ruby %}

rails g serializer *model name*

{% endhighlight %}

And it's easy to change the serializer attributes:

{% highlight ruby %}

class InsecureUserSerializer < ActiveModel::Serializer
  attributes :id, :email, :password, :full_name

  def full_name
    object.full_name
  end
end

{% endhighlight %}

This project was a lot of fun and really gave me insight into how much I like back-end development.
