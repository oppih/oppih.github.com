---
layout: post
title: "Railscasts-China 1-2讲学习笔记"
category: rails
tags: [Rails, Railscast, tutorial, notes]
---
{% include JB/setup %}

[围观 Railscasts-China.com](http://railscasts-china.com)

## [2012-01-13] 初次接触 Rails，跟完001

周末闲着，就开始捣鼓，下载了视频，开始跟做 demo，照着 001 做出了 blog 的基本框架。

因为也看过 Django 的 guide，但是很遗憾没能接着做下去。我也说不清为什么，感觉有点复杂。虽然像我这样的入门者应该是没什么话语权来讨论这两个框架的优劣或者差异的，不过我还是想说，Rails 给我的印象是**成熟度**更高一些。

寒假陆陆续续看了点 Ruby 的基本语法，没能看完 RPL，现在还在抽时间看。基本入门材料还是要看完的。另外也在接触一些其他的 Ruby 学习资料，比如 [Rubywarrior](http://github.com/oppih/rubywarrior-solve)，做起来还是比较有意思的。

添加 comments 这里做的很自然（以一个不会web开发的小白的视角来看），具体的话，要上代码：

**post.rb**

    class Post < ActiveRecord::Base
  	  validates :title, :presence => true, :uniqueness => true
  	  validates :content, :presence => true
  
  	  has_many :comments
	end

**comments.rb**

	class Comment < ActiveRecord::Base
  	  belongs_to :post
	end

而 render 出 comments 的 template 也比较简洁：

	<%= form_for [@post, Comment.new] do |f| %>
	<p>
		<%= f.label :content, "New Comment" %>
		<%= f.text_area :content %>
	</p>
	<p>
		<%= f.submit "Add comment" %>
	</p>
	<% end %>

同时。在此次体验中，还见识了 rails console 以及 rails server 的强大。

----
## [2012-02-08] 继续，跟完002

今天（2012-02-08），还是决定继续跟做 Rails 的 demo，不然感觉总是在那看基本语法不知要到什么时候去了……

另外也是出于增加一下这里的内容的考虑，学习的同时要做好学习笔记，对吧？

今天学习的是做 authentication，特别注意到的地方是：密码处理（generate_password）的方法。要加 salt。Terry还特意强调不应该使用时间做为 salt 的原因。

    private
  	def generate_password(pass)
      # salt = Time.to_s <= it's weak
      salt = Array.new(10){rand(1024).to_s(36)}.join
      self.salt, self.hashed_password =
      salt, Digest::SHA256.hexdigest(pass + salt) # MD% is weak
  	end

·salt = Time.to_s· 这样的方法太弱了，同时， MD5 的 hash 方法也被证明会遭到破解，所以采用 SHA256.

再看 Rails 的 redirect_to,相当 cool 啊：

	def create
      @user =User.authentication(params[:login], params[:password])
      if @user
        session[:user_id] = @user.id
        flash[:notice] = "Welcome #{@user.login}"
        redirect_to posts_path
      else
        flash[:notice] = "The login or password is not correct :("
        redirect_to new_session_path
      end
    end

对我这样没有受过正经训练的新手来说，MVC 模式在这里体现的很明了。

想起大一的高数老师说过，学东西，可以先别管那么多“为什么”，直接往下学，等一定时间以后，回头看，就会发现某些当时完全不知道为什么的东西，到后来就变得完全不需要解释了——随着学习的深入，原本不知所谓的那些基本概念已经深入脑海了，“不解释”就是自然而然的了。

虽然我不知道这样的事情发生在我身上要多久，不过既然开始了，那就要继续下去。

----
哦，对了， repo [放在 GitHub 上了](https://github.com/oppih/rblog)