---
layout: post
title: Blockapidia
feature-img: "img/blockapidia.png"
thumbnail-path: "/img/blockapidia.png"
short-description: Blockapidia is a Wikipedia clone made with Ruby on Rails.

---

                                    Blockapidia

Blocapidia is a Wikipedia clone made with Ruby on Rails.  Wikis are a great way to share information because
of the way users can collaborate.

Giving the users the ability to sign into their account and create wikis to share either publicly or privately
seemed to be a practical project with far-reaching implications.  From authentication to defining models and relationships this would be a great way to get hands-on experience.

To address the ability for users to log into an account and manage their wikis I chose to use the Devise gem.  Devise was great because it allowed me to construct the log in quickly by generating views and routes.  With a
little modification in the application_policy.rb

{% highlight ruby %}

class ApplicationPolicy
  attr_reader :user, :record

  def initialize(user, record)
    @user = user
    @record = record
  end

  def index?
    false
  end

  def show?
    scope.where(id: record.id).exists?
  end

  def create?
    false
  end

  def new?
    create?
  end

  def update?
    @user.admin? || is_owner?
  end

  def edit?
    update?
  end

  def destroy?
    false
  end

  def scope
    Pundit.policy_scope!(@user, @record.class)
  end

  class Scope
    attr_reader :user, :scope

    def initialize(user, scope)
      @user = user
      @scope = scope
    end

    def resolve
      @scope
    end
  end

  private

  def is_owner?
    @user && @user == @record.user
  end
end

{% endhighlight %}

I was able to create a robust authentication system for the users.  The creation of joins table because of the has_many :through relationship was a challenging concept but rewarding to understand.

{% highlight ruby %}

class CreateCollaborators < ActiveRecord::Migration[5.1]
  def change
    create_table :collaborators do |t|
      t.references :user, foreign_key: true
      t.references :wikis, foreign_key: true

      t.timestamps
    end
  end
end

{% endhighlight %}

I also used Docker set up the work environment for this project.  I enjoy using Docker and I try to work it into my projects so when I work with other people our environments match.
