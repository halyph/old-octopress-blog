---
layout: post
title: "How to use block comments in Bash Script"
date: 2014-10-09 22:39:25 +0300
comments: true
categories: [bash, shell]
---
{% img right /images/blog/bash.png %}
What is the simplest way to define block comment in Bash script?

I've selected two approaches for myself:

- Use here document
{% codeblock lang:bash %}
#!/usr/bin/env bash

echo "before block comment"
: <<'END'
Some long 
myltiline 
text
END
echo "after block comment"
{% endcodeblock %}

- Use **"if"** false block
{% codeblock lang:bash %}
#!/usr/bin/env bash

echo "before block comment"
if [ ]; then 
Some long 
myltiline 
text
fi
echo "after block comment"
{% endcodeblock %}