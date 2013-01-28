---
layout: post
title: Generating Bar Charts with SQL
---

[jerakeen](http://jerakeen.org) pointed me to a post showing how you could <a href="http://www.squarebits.com/blog/2006/11/generate_simple.html">Generate Simple Bar Charts From a MySQL Prompt</a>. It's a neat trick for quickly getting a feel for the distribution of values in a database. The post is MySQL centric, but you can do the same thing in any database. PostgreSQL's `REPEAT` is very particular about being passed an INT, however, so you may have to cast the second argument:

    SELECT foo_id, REPEAT('#', COUNT(*)::INT)
    FROM bar
    GROUP BY 1;
