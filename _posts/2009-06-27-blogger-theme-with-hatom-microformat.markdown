--- 
permalink: /2009/06/blogger-theme-with-hatom-microformat.html
layout: post
title: Blogger Theme with hAtom Microformat
tags: 
- microformats
- blogger
- hatom
- template
- garland
---
I just updated my theme to be <a href="http://www.blogcrowds.com/resources/view_template.php/garland_73">Garland</a> but I found that it didn't include the <a href="http://microformats.com/wiki/hatom">hAtom</a> <a href="http://microformats/">microformat</a>. So I tweaked it a little bit, and now I have a beautiful microformat. If anyone else wants to use it, just copy and paste this into the "edit template" part of your blogger layout.

<div style="border: 1px solid black; overflow: scroll; height: 300px;" id="garland_template"><pre><code>&lt;?xml version="1.0" encoding="UTF-8" ?&gt;
&lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"&gt;
&lt;html xmlns='http://www.w3.org/1999/xhtml' xmlns:b='http://www.google.com/2005/gml/b' xmlns:data='http://www.google.com/2005/gml/data' xmlns:expr='http://www.google.com/2005/gml/expr'&gt;
 &lt;head&gt;
   &lt;b:include data='blog' name='all-head-content'/&gt;
   &lt;title&gt;&lt;data:blog.pageTitle/&gt;&lt;/title&gt;
   &lt;b:skin&gt;&lt;![CDATA[/*
-----------------------------------------------
Blogger Template Style
Name:     Garland
Designer: Steven Wittens
URL:      http://acko.net/

Modified by: http://www.blogcrowds.com
Support:     http://www.blogcrowds.com
----------------------------------------------- */

a:link, a:visited {
color: #027ac6;
text-decoration: none;
}

a:hover {
color: #0062a0;
text-decoration: underline;
}

a:active, a.active {
color: #5895be;
}

body {
background: #edf5fa;
color: #494949;
font: 12px/170% Verdana, Arial, Helvetica, sans-serif;
margin: 0;
padding: 0;
}

body.sidebar-left  #footer {
margin-left: -210px;
}

/* So we move the #center container over the sidebars to compensate */
body.sidebar-left #center {
margin-left: -210px;
}

/* And add blanks left and right for the sidebars to fill */
body.sidebar-left #squeeze {
margin-left: 210px;
}

body.sidebar-right #center {
margin-right: -210px;
}

body.sidebar-right #footer {
margin-right: -210px;
}

body.sidebar-right #squeeze {
margin-right: 210px;
}

body.sidebars #center {
margin: 0 -210px;
}

body.sidebars #footer {
margin: 0 -210px;
}

body.sidebars #squeeze {
margin: 0 210px;
}

.meta{margin:0 0 30px 0}

.sidebar .widget{margin:0 0 20px 0}

dl {
margin: 0.5em 0 1em 1.5em;
}

dl dd {
margin: 0 0 .5em 1.5em;
}

dl dt {
}

h1 {
font-size: 170%;
}

h1, h2, h3, h4, h5, h6 {
font-family: Helvetica, Arial, sans-serif;
font-weight: normal;
margin: 0;
padding: 0;
}

h2 {
font-size: 160%;
line-height: 130%;
}

h3, .sidebar h2 {
font-size: 140%;
}

h4 {
font-size: 130%;
}

h5 {
font-size: 120%;
}

h6 {
font-size: 110%;
}

hr {
background: #5294c1;
border: none;
height: 1px;
margin: 0;
padding: 0;
}

img, a img {
border: none;
}

input {
color: #494949;
font: 12px/100% Verdana, Arial, Helvetica, sans-serif;
}

p {
margin: 0.6em 0 1.2em;
padding: 0;
}

textarea, select {
color: #494949;
font: 12px/160% Verdana, Arial, Helvetica, sans-serif;
}

.content ul {
margin: 0.5em 0 1em;
padding: 0;
}

.content ul li {
margin: 0.4em 0 0.4em 1.5em;
}

ul, quote, code, fieldset {
margin: .5em 0;
}

/**
* Primary navigation
*/
ul.primary-links {
float: right;
margin: 0;
padding: 0;
position: relative;
z-index: 4;
/* Hide links - no idea how to get rid of them */
       display : none;
}

ul.primary-links li {
background: none;
float: left;
margin: 0;
padding: 0;
}

ul.primary-links li a, ul.primary-links li a:link, ul.primary-links li a:visited {
background: transparent url("http://s61.photobucket.com/albums/h59/c_stavanger/garland/bg-navigation-item.png") no-repeat 50% 0;
color: #fff;
display: block;
margin: 0 1em;
padding: .75em 0 0;
}

ul.primary-links li a:hover, ul.primary-links li a.active {
background: transparent url("http://s61.photobucket.com/albums/h59/c_stavanger/garland/bg-navigation-item-hover.png") no-repeat 50% 0;
color: #fff;
}

.nextprev {
margin-bottom: 60px;
margin-top: 10px;
}

.alignleft {
float: left;
}

.alignright {
float: right;
clear: both;
}

.commentlist {
list-style: none;
margin: 1em 0 3em;
padding: 0;
}

.commentlist .alt {
background: #edf5fa;
}

.commentlist .avatar {
border: 1px dotted #ccc;
float: right;
margin-right: 25px;
padding: 2px;
}

.commentlist cite {
font-weight: bold;
}

.commentlist li {
padding: 1em 2em;
}

.menu {
list-style: none;
margin: 0;
padding: 0;
}

.menu li li, .item-list ul li, li.leaf, .links li, .sidebar .li {
background: transparent url("http://s61.photobucket.com/albums/h59/c_stavanger/garland/menu-leaf.gif") no-repeat 0 .35em;
list-style-image: none;
list-style-type: none;
padding: 0 0 .3em 13px;
}

.post {
margin-bottom: 2em;
overflow: hidden;
}

#header h1, #header h1 a {
color: #fff;
font-size: 1.5em;
font-weight: normal;
text-decoration: none;
text-shadow: #1659ac 0px 1px 3px;
}

#navigation {
background: url("http://s61.photobucket.com/albums/h59/c_stavanger/garland/bg-navigation.png") repeat-x 50% 100%;
height: 1em;
}

#s {
margin-bottom: 5px;
}

/* Layout and images */
#wrapper {
background: url("http://s61.photobucket.com/albums/h59/c_stavanger/garland/body.png") #edf5fa repeat-x 50% 0;
height: 600px;
}

#wrapper #container {
margin: 0 auto;
max-width: 1270px;
padding: 0 20px;
}

/* We must define 100% width to avoid the body being too narrow for near-empty pages */
#wrapper #container #center {
float: left;
width: 100%;
}

/* Now we add the backgrounds for the main content shading */
#wrapper #container #center #squeeze {
background: url("http://s61.photobucket.com/albums/h59/c_stavanger/garland/bg-content.png") #fff repeat-x 50% 0;
}

#wrapper #container #center .right-corner {
background: transparent url("http://s61.photobucket.com/albums/h59/c_stavanger/garland/bg-content-right.png") no-repeat 100% 0;
left: 10px;
position: relative;
}

#wrapper #container #center .right-corner .left-corner {
background: transparent url("http://s61.photobucket.com/albums/h59/c_stavanger/garland/bg-content-left.png") no-repeat 0 0;
left: -10px;
margin-left: -10px;
min-height: 400px;
padding: 60px 25px 5em 35px;
position: relative;
}

#wrapper #container #footer {
clear: both;
color: #898989;
float: none;
margin: 4em 0 -3em;
text-align: center;
}

#wrapper #container #header {
height: 80px;
}

#wrapper #container #header #logo-floater {
position: absolute;
}

#wrapper #container #header h1, #wrapper #container #header h1 a:link, #wrapper #container #header h1 a:visited {
font-weight: bold;
line-height: 120px;
position: relative;
white-space: nowrap;
z-index: 2;
}

/* We ensure the sidebars are still clickable using z-index */
#wrapper #container .sidebar {
float: left;
margin: 60px 0 5em;
width: 208px;
z-index: 2;
}

body &gt; #wrapper #container .sidebar {
position: relative;
}

#sidebar-left li {
margin-right: 10px;
}

#sidebar-right ul {
margin-left: 20px;
}

#sidebar2 {margin:0 0 0 20px;}

#sidebar-right li ul {
margin-left: 0;
}

.sidebar ul {
margin-left: 0;
padding: 0;
}

.content img {
margin-left: 10px;
}

#comment {
width: 400px;
}

]]&gt;&lt;/b:skin&gt;
 &lt;/head&gt;

&lt;body class='sidebars'&gt;
 &lt;div id='navigation'/&gt;

&lt;div id='wrapper'&gt;
&lt;div class='clear-block' id='container'&gt;

   &lt;!-- skip links for text browsers --&gt;
   &lt;span id='skiplinks' style='display:none;'&gt;
     &lt;a href='#main'&gt;skip to main &lt;/a&gt; |
     &lt;a href='#sidebar'&gt;skip to sidebar&lt;/a&gt;
   &lt;/span&gt;

   &lt;div id='header'&gt;
     &lt;b:section class='header' id='header' maxwidgets='1' showaddelement='no'&gt;
&lt;b:widget id='Header1' locked='true' title='paulisageek (Header)' type='Header'&gt;
&lt;b:includable id='title'&gt;
 &lt;b:if cond='data:blog.url == data:blog.homepageUrl'&gt;
   &lt;data:title/&gt;
 &lt;b:else/&gt;
   &lt;a expr:href='data:blog.homepageUrl'&gt;&lt;data:title/&gt;&lt;/a&gt;
 &lt;/b:if&gt;
&lt;/b:includable&gt;
&lt;b:includable id='description'&gt;
 &lt;div class='descriptionwrapper'&gt;
   &lt;p class='description'&gt;&lt;span&gt;&lt;data:description/&gt;&lt;/span&gt;&lt;/p&gt;
 &lt;/div&gt;
&lt;/b:includable&gt;
&lt;b:includable id='main'&gt;
 &lt;div id='logo-floater'&gt;
   &lt;h1&gt;
      &lt;b:if cond='data:blog.url == data:blog.homepageUrl'&gt;
       &lt;a href='#'&gt;&lt;data:title/&gt;&lt;/a&gt;
     &lt;b:else/&gt;
       &lt;a expr:href='data:blog.homepageUrl'&gt;&lt;data:title/&gt;&lt;/a&gt;
     &lt;/b:if&gt;
   &lt;/h1&gt;
 &lt;/div&gt;
 &lt;ul class='links primary-links'&gt;
   &lt;li&gt;&lt;a expr:href='data:blog.homepageUrl'&gt;&lt;data:title/&gt;&lt;/a&gt;&lt;/li&gt;
 &lt;/ul&gt;
&lt;/b:includable&gt;
&lt;/b:widget&gt;
&lt;/b:section&gt;
   &lt;/div&gt;

   &lt;div class='sidebar' id='sidebar-left'&gt;&lt;b:section class='side' id='sidebar1' preferred='yes'&gt;
&lt;b:widget id='Feed1' locked='false' title='FriendFeed - ptarjan' type='Feed'&gt;
&lt;b:includable id='main'&gt;
   &lt;h2&gt;&lt;data:title/&gt;&lt;/h2&gt;
   &lt;div class='widget-content' expr:id='data:widget.instanceId + "_feedItemListDisplay"'&gt;
     &lt;span style='filter: alpha(25); opacity: 0.25;'&gt;
       &lt;a expr:href='data:feedUrl'&gt;&lt;data:loadingMsg/&gt;&lt;/a&gt;
     &lt;/span&gt;
   &lt;/div&gt;
   &lt;b:include name='quickedit'/&gt;
 &lt;/b:includable&gt;
&lt;/b:widget&gt;
&lt;b:widget id='BlogArchive1' locked='false' title='Blog Archive' type='BlogArchive'&gt;
&lt;b:includable id='main'&gt;
 &lt;b:if cond='data:title'&gt;
   &lt;h2&gt;&lt;data:title/&gt;&lt;/h2&gt;
 &lt;/b:if&gt;
 &lt;div class='widget-content'&gt;
 &lt;div id='ArchiveList'&gt;
 &lt;div expr:id='data:widget.instanceId + "_ArchiveList"'&gt;
   &lt;b:if cond='data:style == "HIERARCHY"'&gt;
    &lt;b:include data='data' name='interval'/&gt;
   &lt;/b:if&gt;
   &lt;b:if cond='data:style == "FLAT"'&gt;
     &lt;b:include data='data' name='flat'/&gt;
   &lt;/b:if&gt;
   &lt;b:if cond='data:style == "MENU"'&gt;
     &lt;b:include data='data' name='menu'/&gt;
   &lt;/b:if&gt;
 &lt;/div&gt;
 &lt;/div&gt;
 &lt;b:include name='quickedit'/&gt;
 &lt;/div&gt;
&lt;/b:includable&gt;
&lt;b:includable id='flat' var='data'&gt;
 &lt;ul&gt;
   &lt;b:loop values='data:data' var='i'&gt;
     &lt;li class='archivedate'&gt;
       &lt;a expr:href='data:i.url'&gt;&lt;data:i.name/&gt;&lt;/a&gt; (&lt;data:i.post-count/&gt;)
     &lt;/li&gt;
   &lt;/b:loop&gt;
 &lt;/ul&gt;
&lt;/b:includable&gt;
&lt;b:includable id='menu' var='data'&gt;
 &lt;select expr:id='data:widget.instanceId + "_ArchiveMenu"'&gt;
   &lt;option value=''&gt;&lt;data:title/&gt;&lt;/option&gt;
   &lt;b:loop values='data:data' var='i'&gt;
     &lt;option expr:value='data:i.url'&gt;&lt;data:i.name/&gt; (&lt;data:i.post-count/&gt;)&lt;/option&gt;
   &lt;/b:loop&gt;
 &lt;/select&gt;
&lt;/b:includable&gt;
&lt;b:includable id='interval' var='intervalData'&gt;
 &lt;b:loop values='data:intervalData' var='i'&gt;
     &lt;ul&gt;
       &lt;li expr:class='"archivedate " + data:i.expclass'&gt;
         &lt;b:include data='i' name='toggle'/&gt;
         &lt;a class='post-count-link' expr:href='data:i.url'&gt;&lt;data:i.name/&gt;&lt;/a&gt;
           &lt;span class='post-count' dir='ltr'&gt;(&lt;data:i.post-count/&gt;)&lt;/span&gt;
         &lt;b:if cond='data:i.data'&gt;
           &lt;b:include data='i.data' name='interval'/&gt;
         &lt;/b:if&gt;
         &lt;b:if cond='data:i.posts'&gt;
           &lt;b:include data='i.posts' name='posts'/&gt;
         &lt;/b:if&gt;
       &lt;/li&gt;
     &lt;/ul&gt;
 &lt;/b:loop&gt;
&lt;/b:includable&gt;
&lt;b:includable id='toggle' var='interval'&gt;
 &lt;b:if cond='data:interval.toggleId'&gt;
 &lt;b:if cond='data:interval.expclass == "expanded"'&gt;
   &lt;a class='toggle' expr:href='data:widget.actionUrl + "&amp;action=toggle" +       "&amp;dir=close&amp;toggle=" + data:interval.toggleId +       "&amp;toggleopen=" + data:toggleopen'&gt;
       &lt;span class='zippy toggle-open'&gt;▼ &lt;/span&gt;
   &lt;/a&gt;
 &lt;b:else/&gt;
   &lt;a class='toggle' expr:href='data:widget.actionUrl + "&amp;action=toggle" +         "&amp;dir=open&amp;toggle=" + data:interval.toggleId +         "&amp;toggleopen=" + data:toggleopen'&gt;
         &lt;span class='zippy'&gt;
           &lt;b:if cond='data:blog.languageDirection == "rtl"'&gt;
             ◄
           &lt;b:else/&gt;
             ►
           &lt;/b:if&gt;
         &lt;/span&gt;
   &lt;/a&gt;
 &lt;/b:if&gt;
&lt;/b:if&gt;
&lt;/b:includable&gt;
&lt;b:includable id='posts' var='posts'&gt;
 &lt;ul class='posts'&gt;
   &lt;b:loop values='data:posts' var='i'&gt;
     &lt;li&gt;&lt;a expr:href='data:i.url'&gt;&lt;data:i.title/&gt;&lt;/a&gt;&lt;/li&gt;
   &lt;/b:loop&gt;
 &lt;/ul&gt;
&lt;/b:includable&gt;
&lt;/b:widget&gt;
&lt;b:widget id='AdSense1' locked='false' title='' type='AdSense'&gt;
&lt;b:includable id='main'&gt;
 &lt;div class='widget-content'&gt;
   &lt;data:adCode/&gt;
 &lt;/div&gt;
&lt;/b:includable&gt;
&lt;/b:widget&gt;
&lt;/b:section&gt;&lt;/div&gt;

     &lt;div id='crosscol-wrapper' style='text-align:center'&gt;
       &lt;b:section class='crosscol' id='crosscol' showaddelement='no'/&gt;
     &lt;/div&gt;

     &lt;div id='center'&gt;&lt;div id='squeeze'&gt;&lt;div class='right-corner'&gt;&lt;div class='left-corner'&gt;
     &lt;!-- begin content --&gt;
     &lt;div class='node'&gt;
       &lt;b:section class='main' id='main' showaddelement='no'&gt;
&lt;b:widget id='Blog1' locked='true' title='Blog Posts' type='Blog'&gt;
&lt;b:includable id='nextprev'&gt;
 &lt;div class='blog-pager hentry' id='blog-pager'&gt;
   &lt;b:if cond='data:newerPageUrl'&gt;
     &lt;span id='blog-pager-newer-link'&gt;
     &lt;a class='blog-pager-newer-link' expr:href='data:newerPageUrl' expr:id='data:widget.instanceId + "_blog-pager-newer-link"' expr:title='data:newerPageTitle'&gt;&lt;data:newerPageTitle/&gt;&lt;/a&gt;
     &lt;/span&gt;
   &lt;/b:if&gt;

   &lt;b:if cond='data:olderPageUrl'&gt;
     &lt;span id='blog-pager-older-link'&gt;
     &lt;a class='blog-pager-older-link' expr:href='data:olderPageUrl' expr:id='data:widget.instanceId + "_blog-pager-older-link"' expr:title='data:olderPageTitle'&gt;&lt;data:olderPageTitle/&gt;&lt;/a&gt;
     &lt;/span&gt;
   &lt;/b:if&gt;

   &lt;b:if cond='data:blog.homepageUrl != data:blog.url'&gt;
     &lt;a class='home-link' expr:href='data:blog.homepageUrl'&gt;&lt;data:homeMsg/&gt;&lt;/a&gt;
     &lt;b:else/&gt;
     &lt;b:if cond='data:newerPageUrl'&gt;
       &lt;a class='home-link' expr:href='data:blog.homepageUrl'&gt;&lt;data:homeMsg/&gt;&lt;/a&gt;
     &lt;/b:if&gt;
   &lt;/b:if&gt;

 &lt;/div&gt;
 &lt;div class='clear'/&gt;
&lt;/b:includable&gt;
&lt;b:includable id='backlinks' var='post'&gt;
 &lt;a name='links'/&gt;&lt;h4&gt;&lt;data:post.backlinksLabel/&gt;&lt;/h4&gt;
 &lt;b:if cond='data:post.numBacklinks != 0'&gt;
   &lt;dl class='comments-block' id='comments-block'&gt;
     &lt;b:loop values='data:post.backlinks' var='backlink'&gt;
       &lt;div class='collapsed-backlink backlink-control'&gt;
         &lt;dt class='comment-title'&gt;
           &lt;span class='backlink-toggle-zippy'&gt; &lt;/span&gt;
           &lt;a expr:href='data:backlink.url' rel='nofollow'&gt;&lt;data:backlink.title/&gt;&lt;/a&gt;
           &lt;b:include data='backlink' name='backlinkDeleteIcon'/&gt;
         &lt;/dt&gt;
         &lt;dd class='comment-body collapseable'&gt;
           &lt;data:backlink.snippet/&gt;
         &lt;/dd&gt;
         &lt;dd class='comment-footer collapseable'&gt;
           &lt;span class='comment-author'&gt;&lt;data:post.authorLabel/&gt; &lt;data:backlink.author/&gt;&lt;/span&gt;
           &lt;span class='comment-timestamp'&gt;&lt;data:post.timestampLabel/&gt; &lt;data:backlink.timestamp/&gt;&lt;/span&gt;
         &lt;/dd&gt;
       &lt;/div&gt;
     &lt;/b:loop&gt;
   &lt;/dl&gt;
 &lt;/b:if&gt;
 &lt;p class='comment-footer'&gt;
   &lt;a class='comment-link' expr:href='data:post.createLinkUrl' expr:id='data:widget.instanceId + "_backlinks-create-link"' target='_blank'&gt;&lt;data:post.createLinkLabel/&gt;&lt;/a&gt;
 &lt;/p&gt;
&lt;/b:includable&gt;
&lt;b:includable id='post' var='post'&gt;
  &lt;div class="hentry post"&gt;
   &lt;a expr:name='data:post.id'/&gt;
   &lt;b:if cond='data:post.title'&gt;
     &lt;h2 class="entry-title post-title"&gt;
    &lt;b:if cond='data:post.link'&gt;
      &lt;a expr:href='data:post.link' rel="bookmark"&gt;&lt;data:post.title/&gt;&lt;/a&gt;
    &lt;b:else/&gt;
       &lt;b:if cond='data:post.url'&gt;
         &lt;a expr:href='data:post.url' rel="bookmark"&gt;&lt;data:post.title/&gt;&lt;/a&gt;
       &lt;b:else/&gt;
         &lt;data:post.title/&gt;
       &lt;/b:if&gt;
    &lt;/b:if&gt;
     &lt;/h2&gt;
   &lt;/b:if&gt;
  
   &lt;span class='submitted'&gt;
     Posted On &lt;data:post.dateHeader/&gt;
     &lt;b:if cond='data:top.showTimestamp'&gt;
       at
       &lt;data:top.timestampLabel/&gt;
       &lt;b:if cond='data:post.url'&gt;
         &lt;a class='timestamp-link' expr:href='data:post.url' rel='bookmark' title='permanent link'&gt;&lt;abbr class='published' expr:title='data:post.timestampISO8601'&gt;&lt;data:post.timestamp/&gt;&lt;/abbr&gt;&lt;/a&gt;
       &lt;/b:if&gt;
     &lt;/b:if&gt; by &lt;span class="vcard author fn"&gt;&lt;data:post.author/&gt;&lt;/span&gt;
    
       &lt;!-- email post links --&gt;
       &lt;b:if cond='data:post.emailPostUrl'&gt;
         &lt;span class='item-action'&gt;
         &lt;a expr:href='data:post.emailPostUrl' expr:title='data:top.emailPostMsg'&gt;
           &lt;span class='email-post-icon'&gt; &lt;/span&gt;
         &lt;/a&gt;
         &lt;/span&gt;
       &lt;/b:if&gt;

       &lt;!-- quickedit pencil --&gt;
       &lt;b:include data='post' name='postQuickEdit'/&gt;
    
   &lt;/span&gt;

   &lt;div class='content entry-content'&gt;
     &lt;p&gt;&lt;data:post.body/&gt;&lt;/p&gt;
     &lt;div style='clear: both;'/&gt; &lt;!-- clear for photos floats --&gt;
   &lt;/div&gt;
  
   &lt;div class='meta'&gt;
       Posted in  &lt;b:if cond='data:post.labels'&gt;
         &lt;data:postLabelsLabel/&gt;
         &lt;b:loop values='data:post.labels' var='label'&gt;
           &lt;a expr:href='data:label.url' rel='tag'&gt;&lt;data:label.name/&gt;&lt;/a&gt;&lt;b:if cond='data:label.isLast != "true"'&gt;,&lt;/b:if&gt;
         &lt;/b:loop&gt;
       &lt;/b:if&gt; |

       &lt;b:if cond='data:blog.pageType != "item"'&gt;

         &lt;b:if cond='data:post.allowComments'&gt;
           &lt;a class='comment-link' expr:href='data:post.addCommentUrl' expr:onclick='data:post.addCommentOnclick'&gt;&lt;b:if cond='data:post.numComments == 1'&gt;1 &lt;data:top.commentLabel/&gt;&lt;b:else/&gt;&lt;data:post.numComments/&gt; &lt;data:top.commentLabelPlural/&gt;&lt;/b:if&gt;&lt;/a&gt;
         &lt;/b:if&gt;
       &lt;/b:if&gt;
  

      &lt;!-- backlinks --&gt;
        &lt;b:if cond='data:blog.pageType != "item"'&gt;
          &lt;b:if cond='data:post.showBacklinks'&gt;
            &lt;a class='comment-link' expr:href='data:post.url + "#links"'&gt;&lt;data:top.backlinkLabel/&gt;&lt;/a&gt;
          &lt;/b:if&gt;
        &lt;/b:if&gt;
   &lt;/div&gt;
  &lt;/div&gt;
&lt;/b:includable&gt;
&lt;b:includable id='commentDeleteIcon' var='comment'&gt;
 &lt;span expr:class='"item-control " + data:comment.adminClass'&gt;
   &lt;a expr:href='data:comment.deleteUrl' expr:title='data:top.deleteCommentMsg'&gt;
     &lt;span class='delete-comment-icon'&gt; &lt;/span&gt;
   &lt;/a&gt;
 &lt;/span&gt;
&lt;/b:includable&gt;
&lt;b:includable id='status-message'&gt;
 &lt;b:if cond='data:navMessage'&gt;
 &lt;div class='status-msg-wrap'&gt;
   &lt;div class='status-msg-body'&gt;
     &lt;data:navMessage/&gt;
   &lt;/div&gt;
   &lt;div class='status-msg-border'&gt;
     &lt;div class='status-msg-bg'&gt;
       &lt;div class='status-msg-hidden'&gt;&lt;data:navMessage/&gt;&lt;/div&gt;
     &lt;/div&gt;
   &lt;/div&gt;
 &lt;/div&gt;
 &lt;div style='clear: both;'/&gt;
 &lt;/b:if&gt;
&lt;/b:includable&gt;
&lt;b:includable id='feedLinks'&gt;
 &lt;b:if cond='data:blog.pageType != "item"'&gt; &lt;!-- Blog feed links --&gt;
   &lt;b:if cond='data:feedLinks'&gt;
     &lt;div class='blog-feeds'&gt;
       &lt;b:include data='feedLinks' name='feedLinksBody'/&gt;
     &lt;/div&gt;
   &lt;/b:if&gt;

   &lt;b:else/&gt; &lt;!--Post feed links --&gt;
   &lt;div class='post-feeds'&gt;
     &lt;b:loop values='data:posts' var='post'&gt;
       &lt;b:if cond='data:post.allowComments'&gt;
         &lt;b:if cond='data:post.feedLinks'&gt;
           &lt;b:include data='post.feedLinks' name='feedLinksBody'/&gt;
         &lt;/b:if&gt;
       &lt;/b:if&gt;
     &lt;/b:loop&gt;
   &lt;/div&gt;
 &lt;/b:if&gt;
&lt;/b:includable&gt;
&lt;b:includable id='comment-form' var='post'&gt;
 &lt;div class='comment-form'&gt;
   &lt;a name='comment-form'/&gt;
   &lt;h4 id='comment-post-message'&gt;&lt;data:postCommentMsg/&gt;&lt;/h4&gt;
   &lt;p&gt;&lt;data:blogCommentMessage/&gt;&lt;/p&gt;
   &lt;data:blogTeamBlogMessage/&gt;
   &lt;a expr:href='data:post.commentFormIframeSrc' id='comment-editor-src'/&gt;
   &lt;iframe allowtransparency='true' class='blogger-iframe-colorize blogger-comment-from-post' frameborder='0' height='275' id='comment-editor' name='comment-editor' scrolling='no' src='' width='100%'/&gt;
   &lt;data:post.friendConnectJs/&gt;
   &lt;data:post.cmtfpIframe/&gt;
   &lt;script type='text/javascript'&gt;
     BLOG_CMT_createIframe('&lt;data:post.appRpcRelayPath/&gt;', '&lt;data:post.communityId/&gt;');
   &lt;/script&gt;
 &lt;/div&gt;
&lt;/b:includable&gt;
&lt;b:includable id='backlinkDeleteIcon' var='backlink'&gt;
 &lt;span expr:class='"item-control " + data:backlink.adminClass'&gt;
   &lt;a expr:href='data:backlink.deleteUrl' expr:title='data:top.deleteBacklinkMsg'&gt;
     &lt;span class='delete-comment-icon'&gt; &lt;/span&gt;
   &lt;/a&gt;
 &lt;/span&gt;
&lt;/b:includable&gt;
&lt;b:includable id='feedLinksBody' var='links'&gt;
 &lt;div class='feed-links'&gt;
 &lt;data:feedLinksMsg/&gt;
 &lt;b:loop values='data:links' var='f'&gt;
    &lt;a class='feed-link' expr:href='data:f.url' expr:type='data:f.mimeType' target='_blank'&gt;&lt;data:f.name/&gt; (&lt;data:f.feedType/&gt;)&lt;/a&gt;
 &lt;/b:loop&gt;
 &lt;/div&gt;
&lt;/b:includable&gt;
&lt;b:includable id='postQuickEdit' var='post'&gt;
 &lt;b:if cond='data:post.editUrl'&gt;
   &lt;span expr:class='"item-control " + data:post.adminClass'&gt;
     &lt;a expr:href='data:post.editUrl' expr:title='data:top.editPostMsg'&gt;
       &lt;span class='quick-edit-icon'&gt; &lt;/span&gt;
     &lt;/a&gt;
   &lt;/span&gt;
 &lt;/b:if&gt;
&lt;/b:includable&gt;
&lt;b:includable id='comments' var='post'&gt;
   &lt;a name='comments'/&gt;
   &lt;b:if cond='data:post.allowComments'&gt;
     &lt;h3 id='comments'&gt;
       &lt;b:if cond='data:post.numComments == 1'&gt;
         1 &lt;data:commentLabel/&gt;:
       &lt;b:else/&gt;
         &lt;data:post.numComments/&gt; &lt;data:commentLabelPlural/&gt;:
       &lt;/b:if&gt;
     &lt;/h3&gt;

     &lt;ol class='commentlist'&gt;
       &lt;b:loop values='data:post.comments' var='comment'&gt;
         &lt;li&gt;
           &lt;a expr:name='"comment-" + data:comment.id'/&gt;
           &lt;cite&gt;
           &lt;b:if cond='data:comment.authorUrl'&gt;
             &lt;a expr:href='data:comment.authorUrl' rel='nofollow'&gt;&lt;data:comment.author/&gt;&lt;/a&gt;
           &lt;b:else/&gt;
             &lt;data:comment.author/&gt;
           &lt;/b:if&gt;
           &lt;/cite&gt; Says:
           &lt;small class='commentmetadata'&gt;&lt;a expr:href='"#comment-" + data:comment.id' title='comment permalink'&gt;
               &lt;data:comment.timestamp/&gt;
             &lt;/a&gt;
             &lt;b:include data='comment' name='commentDeleteIcon'/&gt;
           &lt;/small&gt;
             &lt;b:if cond='data:comment.isDeleted'&gt;
             &lt;span class='deleted-comment'&gt;&lt;data:comment.body/&gt;&lt;/span&gt;
           &lt;b:else/&gt;
             &lt;p&gt;&lt;data:comment.body/&gt;&lt;/p&gt;
           &lt;/b:if&gt;
         &lt;/li&gt;
       &lt;/b:loop&gt;
     &lt;/ol&gt;

     &lt;p class='comment-footer'&gt;
       &lt;a expr:href='data:post.addCommentUrl' expr:onclick='data:post.addCommentOnclick'&gt;&lt;data:postCommentMsg/&gt;&lt;/a&gt;
     &lt;/p&gt;
   &lt;/b:if&gt;

   &lt;div id='backlinks-container'&gt;
   &lt;div expr:id='data:widget.instanceId + "_backlinks-container"'&gt;
      &lt;b:if cond='data:post.showBacklinks'&gt;
        &lt;b:include data='post' name='backlinks'/&gt;
      &lt;/b:if&gt;
   &lt;/div&gt;
   &lt;/div&gt;
&lt;/b:includable&gt;
&lt;b:includable id='main' var='top'&gt;
 &lt;!-- posts --&gt;
 &lt;div class='post hfeed'&gt;

   &lt;b:include data='top' name='status-message'/&gt;

   &lt;b:loop values='data:posts' var='post'&gt;
     &lt;b:include data='post' name='post'/&gt;
     &lt;b:if cond='data:blog.pageType == "item"'&gt;
       &lt;b:include data='post' name='comments'/&gt;
     &lt;/b:if&gt;
   &lt;/b:loop&gt;
 &lt;/div&gt;

 &lt;!-- navigation --&gt;
 &lt;b:include name='nextprev'/&gt;

 &lt;!-- feed links --&gt;
 &lt;b:include name='feedLinks'/&gt;
&lt;/b:includable&gt;
&lt;/b:widget&gt;
&lt;/b:section&gt;&lt;/div&gt;&lt;!-- end content --&gt;&lt;!-- spacer for skins that want sidebar and main to be the same height--&gt;&lt;div class='clear'&gt; &lt;/div&gt;&lt;div id='footer-wrapper'&gt;&lt;b:section class='footer' id='footer'/&gt;&lt;/div&gt;&lt;/div&gt;&lt;/div&gt;&lt;/div&gt;&lt;/div&gt; &lt;!-- /.left-corner, /.right-corner, /#squeeze, /#center --&gt;&lt;div class='sidebar' id='sidebar-right'&gt;&lt;b:section class='side' id='sidebar2' preferred='yes'&gt;
&lt;b:widget id='Profile1' locked='false' title='About Me' type='Profile'&gt;
&lt;b:includable id='main'&gt;
   &lt;b:if cond='data:title != ""'&gt;
     &lt;h2&gt;&lt;data:title/&gt;&lt;/h2&gt;
   &lt;/b:if&gt;
   &lt;div class='widget-content'&gt;
   &lt;b:if cond='data:team == "true"'&gt; &lt;!-- team blog profile --&gt;
     &lt;ul&gt;
       &lt;b:loop values='data:authors' var='i'&gt;
         &lt;li&gt;&lt;a expr:href='data:i.userUrl'&gt;&lt;data:i.display-name/&gt;&lt;/a&gt;&lt;/li&gt;
       &lt;/b:loop&gt;
     &lt;/ul&gt;

     &lt;b:else/&gt; &lt;!-- normal blog profile --&gt;

     &lt;b:if cond='data:photo.url != ""'&gt;
       &lt;a expr:href='data:userUrl'&gt;&lt;img class='profile-img' expr:alt='data:photo.alt' expr:height='data:photo.height' expr:src='data:photo.url' expr:width='data:photo.width'/&gt;&lt;/a&gt;
     &lt;/b:if&gt;

     &lt;dl class='profile-datablock'&gt;
       &lt;dt class='profile-data'&gt;&lt;data:displayname/&gt;&lt;/dt&gt;

       &lt;b:if cond='data:showlocation == "true"'&gt;
         &lt;dd class='profile-data'&gt;&lt;data:location/&gt;&lt;/dd&gt;
       &lt;/b:if&gt;

       &lt;b:if cond='data:aboutme != ""'&gt;&lt;dd class='profile-textblock'&gt;&lt;data:aboutme/&gt;&lt;/dd&gt;&lt;/b:if&gt;
     &lt;/dl&gt;
     &lt;a class='profile-link' expr:href='data:userUrl'&gt;&lt;data:viewProfileMsg/&gt;&lt;/a&gt;
   &lt;/b:if&gt;

    &lt;b:include name='quickedit'/&gt;
   &lt;/div&gt;
 &lt;/b:includable&gt;
&lt;/b:widget&gt;
&lt;b:widget id='HTML1' locked='false' title='My Other Internet Stuff' type='HTML'&gt;
&lt;b:includable id='main'&gt;
 &lt;!-- only display title if it's non-empty --&gt;
 &lt;b:if cond='data:title != ""'&gt;
   &lt;h2 class='title'&gt;&lt;data:title/&gt;&lt;/h2&gt;
 &lt;/b:if&gt;
 &lt;div class='widget-content'&gt;
   &lt;data:content/&gt;
 &lt;/div&gt;

 &lt;b:include name='quickedit'/&gt;
&lt;/b:includable&gt;
&lt;/b:widget&gt;
&lt;b:widget id='Followers1' locked='false' title='Followers' type='Followers'&gt;
&lt;b:includable id='main'&gt;
 &lt;b:if cond='data:title != ""'&gt;
   &lt;b:if cond='data:codeSnippet != ""'&gt;
     &lt;h2 class='title'&gt;&lt;data:title/&gt;&lt;/h2&gt;
   &lt;b:else/&gt;
     &lt;b:if cond='data:totalFollowerCount != ""'&gt;
       &lt;h2 class='title'&gt;&lt;data:title/&gt; (&lt;data:totalFollowerCount/&gt;)&lt;/h2&gt;
     &lt;/b:if&gt;
   &lt;/b:if&gt; 
 &lt;/b:if&gt;
 &lt;div class='widget-content'&gt;
   &lt;div expr:id='data:widget.instanceId + "-wrapper"'&gt;
     &lt;b:if cond='data:codeSnippet != ""'&gt;
       &lt;div style='margin-right:2px;'&gt;
         &lt;data:codeSnippet/&gt;
       &lt;/div&gt;
     &lt;b:else/&gt;
       &lt;b:if cond='data:totalFollowerCount == ""'&gt;
         &lt;span class='item-control following-not-admin'&gt;
           &lt;b&gt;&lt;data:failureSnippet/&gt;&lt;/b&gt;
         &lt;/span&gt;
         &lt;span class='item-control blog-admin'&gt;
           &lt;b&gt;&lt;data:adminFailureSnippet/&gt;&lt;/b&gt;
         &lt;/span&gt;
       &lt;b:else/&gt;
         &lt;b:if cond='data:followingLinkPresent'&gt;
           &lt;div class='follow-this profile-link item-control following-follow-this'&gt;
             &lt;a expr:href='"javascript:_FollowersView._openPopup(\"" + data:followUri + "\");"'&gt;
               &lt;data:followThisMessage/&gt;
             &lt;/a&gt;
           &lt;/div&gt;
           &lt;div class='follow-this profile-link item-control following-stop-following-this'&gt;
             &lt;a expr:href='"javascript:_FollowersView._openPopup(\"" + data:followUri + "\");"'&gt;
               &lt;data:stopFollowingMessage/&gt;
             &lt;/a&gt;
           &lt;/div&gt;
         &lt;/b:if&gt;

         &lt;div class='followers-grid'&gt;
           &lt;b:if cond='data:totalFollowerCount == 0'&gt;
             &lt;div class='profile-link item-control following-follow-this'&gt;
               &lt;data:emptyFollowersMessage/&gt;
             &lt;/div&gt;
           &lt;/b:if&gt;
           &lt;!--
           Relies on the js written out in navbar.gxp
           --&gt;
           &lt;b:loop values='data:followers' var='follower'&gt;
             &lt;div class='follower'&gt;
               &lt;a expr:href='data:follower.profileUrl' expr:title='data:follower.displayName' rel='nofollow'&gt;
               &lt;img class='follower-img' expr:alt='data:follower.displayName' expr:height='data:follower.imageHeight' expr:onerror='"this.onerror=null;this.src=\"" + data:anonFollowerImageUrl + "\";"' expr:onload='"setAttributeOnload(this, \"src\", \"" + data:follower.imageUrl + "\")"' expr:width='data:follower.imageWidth' src='http://img1.blogblog.com/img/blank.gif'/&gt;
               &lt;/a&gt;
             &lt;/div&gt;
           &lt;/b:loop&gt;
           &lt;div class='clear'/&gt;
         &lt;/div&gt;

         &lt;div class='followers-canvas profile-link'&gt;
           &lt;data:followersFooterMessage/&gt;
           &lt;span class='item-control following-not-admin'&gt;
             &lt;a expr:href='data:followersUri'&gt;
               &lt;data:viewAllMessage/&gt;
             &lt;/a&gt;
           &lt;/span&gt;
           &lt;span class='item-control blog-admin'&gt;
             &lt;a expr:href='data:manageFollowersUri'&gt;
               &lt;data:manageFollowersMessage/&gt;
             &lt;/a&gt;
           &lt;/span&gt;
         &lt;/div&gt;
         &lt;/b:if&gt;
     &lt;/b:if&gt;
   &lt;/div&gt;
   &lt;b:include name='quickedit'/&gt;
 &lt;/div&gt;
&lt;/b:includable&gt;
&lt;/b:widget&gt;
&lt;/b:section&gt;&lt;p style='margin:0 0 0 20px'/&gt;&lt;/div&gt;
  
   &lt;/div&gt; &lt;!-- /container --&gt;
   &lt;/div&gt;

&lt;/body&gt;
&lt;/html&gt;
</code></pre></div>

<script>
function fnSelect(objId)
{
   fnDeSelect();
   if (document.selection) 
   {
      var range = document.body.createTextRange();
      range.moveToElementText(document.getElementById(objId));
      range.select();
   }
   else if (window.getSelection) 
   {
      var range = document.createRange();
      range.selectNode(document.getElementById(objId));
      window.getSelection().addRange(range);
   }
}
function fnDeSelect() 
{
   if (document.selection)
             document.selection.empty();
   else if (window.getSelection)
              window.getSelection().removeAllRanges();
} 

var id = "garland_template";
document.getElementById(id).onclick = function() {
  fnSelect(id);
}
</script>
<!-- Script by hscripts.com -->
