---
layout: post
title: "SaaS 第一周作业完成"
category: 
tags: [Saas, Ruby, MetaProgramming]
---
{% include JB/setup %}

这周同小王子一起开始跟 UC Berkeley 的 [《Software Engineering for Software as a Service》Spring 2012](www.coursera.org/saas/ "SaaS") 课程，

> This course is an opinionated path through the bewildering array of methodologies, languages, tools, and artifact types that collectively make up “software engineering.” The goal is to instill good software habits—testability, software architecture, modularity, and reusability—while providing the gratification of building a working deployed artifact in the cloud in just 5 weeks. We teach Agile Development in the context of building and deploying a Software-as-a-Service application implemented using Ruby on Rails.

----
另外 SaaS 也提供了一个内部论坛，提供相关讨论，我在里面看到了一个 [wiki](http://www.aiqus.com/wiki/Software_Engineering_for_Software_as_a_Service)，在这里面能看到不少 Ruby 的起步学习资料（因为有不少学生和我一样，觉得一下上来就直接这种程度的作业有点基础不够的感觉）。同时，相关资讯可以在 [这里](http://www.aiqus.com/tags/%23saas/) 找到。

----
我自己的作业存到了 [GitCafe](http://gitcafe.com/oppih/SaaS_hw) 上。仅供围观 XD

** 简单对这次作业做个总结：**

这次作业的一半是自己完成的，第1題做字符处理，貌似是我首次真正使用正则表达式（惭愧惭愧），参考的是[Ruby正则表达式操作参考](http://qianjigui.iteye.com/blog/1390067)，接着应该把[Intro to Regular Expressions (Ruby)](http://jimmy-li.net/blog/programming/hello-world/)看了吧。

第2題，自己完成了part a，part b 是从网上看来的，特别赞这样的迭代处理方式：

    def rps_tournament_winner(game)
      if game[0][1].class == String # it's a colever solution!
        rps_game_winner(game)
      else
        p1 = rps_tournament_winner(game[0])
        p2 = rps_tournament_winner(game[1])
        rps_tournament_winner([p1, p2])
      end
    end

第3题，属于基本功力问题，自己逻辑抽象能力欠佳，不能将问题转化为编程的问题……所以看了别人写的答案（感觉不是那么的ruby味……）

----
** 关于 Metaprogramming **

4、5 两題，涉及面向对象以及元编程，对我这个水平来说是相当抽象的东西了，看了 《Ruby Programming Language》 中第八章的的 `class_eval` 相关内容，还不足以做作业，另外找到的一些学习资料：[Metaprogramming in Ruby](http://ruby-metaprogramming.rubylearning.com/html/ruby_metaprogramming_3.html) 

----
** 关于测试 **

在自己写代码的过程中，因为要反复测试自己写出的代码是否能正常工作，所以就一直用 puts 语句来做，直到看到在 [这里](https://github.com/tapichu/saas-class)（GitHub） 有位同学写了测试。对我来说就是用来看源代码学习如何写测试用例。

----
看看能不能坚持做完这个系列的课程。