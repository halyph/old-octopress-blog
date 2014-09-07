---
title: "Groovy Notes: Pretty print JSON from the command line"
layout: "post"
permalink: "/2014/08/groovy-notes-pretty-print-json-from.html"
uuid: "8391203241795630785"
guid: "tag:blogger.com,1999:blog-7372777165432727866.post-8391203241795630785"
date: "2014-08-13 21:28:00"
updated: "2014-08-12 21:29:04"
description: 
blogger:
    siteid: "7372777165432727866"
    postid: "8391203241795630785"
    comments: "0"
categories: [groovy]
---
{% img center /images/blog/groovy.png %}
JSON pretty print it's common task while working with JSON from command line. There are many ways of doing this via Python, Ruby, node.js, but here I'd like to concentrate on Groovy one-liner:

{% codeblock %}
$ echo '{"foo": "lorem", "bar": "ipsum"}' | groovy -e 'import groovy.json.*; println JsonOutput.prettyPrint(System.in.text)'

{
    "foo": "lorem",
    "bar": "ipsum"
}
{% endcodeblock %}

We can slightly improve this one-liner via adding shell alias:
{% codeblock %}
$ alias pp="groovy -e 'import groovy.json.*; println JsonOutput.prettyPrint(System.in.text)'"
$ echo '{"foo": "lorem", "bar": "ipsum"}' | pp
{% endcodeblock %}

Also, we might use Groovy script which might be handy for simple JSON validation also:

{% codeblock lang:groovy %}
$ cat prettyJson.groovy 
import groovy.json.*

try {
  println JsonOutput.prettyPrint(System.in.text)
} catch (JsonException e) {
  println "ERROR: Not valid JSON"
  System.exit(1)
}

$ echo '{"foo: "lorem", ' | groovy prettyJson.groovy
ERROR: Not valid JSON
{% endcodeblock %}