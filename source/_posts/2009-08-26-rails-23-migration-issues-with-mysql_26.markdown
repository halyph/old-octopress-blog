---
title: "Rails 2.3 migration issues with MySQL 5.1.3"
layout: "post"
permalink: "/2009/08/rails-23-migration-issues-with-mysql_26.html"
uuid: "2772777033509564413"
guid: "tag:blogger.com,1999:blog-7372777165432727866.post-2772777033509564413"
date: "2009-08-26 00:13:00"
updated: "2009-08-29 00:28:40"
description: 
blogger:
    siteid: "7372777165432727866"
    postid: "2772777033509564413"
    comments: "12"
categories: [rails]
---

```
depot&gt;rake db:migrate --trace
(in D:/Projects/RoR/depot)
** Invoke db:migrate (first_time)
** Invoke environment (first_time)
** Execute environment
** Execute db:migrate
rake aborted!
Mysql::Error: query: not connected: CREATE TABLE `schema_migrations` (`version`
varchar(255) NOT NULL) ENGINE=InnoDB
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/connetion_adapters/abstract_adapter.rb:212:in `log'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/connetion_adapters/mysql_adapter.rb:320:in `execute'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/connetion_adapters/abstract/schema_statements.rb:114:in `create_table'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/connetion_adapters/mysql_adapter.rb:473:in `create_table'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/connetion_adapters/abstract/schema_statements.rb:320:in `initialize_schema_migration_table'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/migraion.rb:436:in `initialize'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/migraion.rb:400:in `new'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/migraion.rb:400:in `up'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/activerecord-2.3.3/lib/active_record/migraion.rb:383:in `migrate'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rails-2.3.3/lib/tasks/databases.rake:116
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:636:in `call'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:636:in `execute'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:631:in `each'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:631:in `execute'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:597:in `invoke_with call_chain'
d:/tools/Ruby/lib/ruby/1.8/monitor.rb:242:in `synchronize'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:590:in `invoke_with call_chain'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:583:in `invoke'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:2051:in `invoke_tas'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:2029:in `top_level'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:2029:in `each'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:2029:in `top_level'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:2068:in `standard_exception_handling'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:2023:in `top_level'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:2001:in `run'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:2068:in `standard_exception_handling'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/lib/rake.rb:1998:in `run'
d:/tools/Ruby/lib/ruby/gems/1.8/gems/rake-0.8.7/bin/rake:31
d:/Tools/Ruby/bin/rake:19:in `load'
d:/Tools/Ruby/bin/rake:19
```

As I understood the client MySQL library doesn't work well with Rails 2.3. We can resolve this by using the older MySQL client library (libmySQL.dll). You can get it here [http://instantrails.rubyforge.org/svn/trunk/InstantRails-win/InstantRails/mysql/bin/libmySQL.dll](http://instantrails.rubyforge.org/svn/trunk/InstantRails-win/InstantRails/mysql/bin/libmySQL.dll).
Just put it in <span style="font-family: Courier New;">&lt;ruby base dir&gt;\bin\</span> and restart MySQL service.