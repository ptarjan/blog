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

{% highlight html %}
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns='http://www.w3.org/1999/xhtml' xmlns:b='http://www.google.com/2005/gml/b' xmlns:data='http://www.google.com/2005/gml/data' xmlns:expr='http://www.google.com/2005/gml/expr'>
 <head>
   <b:include data='blog' name='all-head-content'/>
   <title><data:blog.pageTitle/></title>
   <b:skin><![CDATA[/*
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

body > #wrapper #container .sidebar {
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

]]></b:skin>
 </head>

<body class='sidebars'>
 <div id='navigation'/>

<div id='wrapper'>
<div class='clear-block' id='container'>

   <!-- skip links for text browsers -->
   <span id='skiplinks' style='display:none;'>
     <a href='#main'>skip to main </a> |
     <a href='#sidebar'>skip to sidebar</a>
   </span>

   <div id='header'>
     <b:section class='header' id='header' maxwidgets='1' showaddelement='no'>
<b:widget id='Header1' locked='true' title='paulisageek (Header)' type='Header'>
<b:includable id='title'>
 <b:if cond='data:blog.url == data:blog.homepageUrl'>
   <data:title/>
 <b:else/>
   <a expr:href='data:blog.homepageUrl'><data:title/></a>
 </b:if>
</b:includable>
<b:includable id='description'>
 <div class='descriptionwrapper'>
   <p class='description'><span><data:description/></span></p>
 </div>
</b:includable>
<b:includable id='main'>
 <div id='logo-floater'>
   <h1>
      <b:if cond='data:blog.url == data:blog.homepageUrl'>
       <a href='#'><data:title/></a>
     <b:else/>
       <a expr:href='data:blog.homepageUrl'><data:title/></a>
     </b:if>
   </h1>
 </div>
 <ul class='links primary-links'>
   <li><a expr:href='data:blog.homepageUrl'><data:title/></a></li>
 </ul>
</b:includable>
</b:widget>
</b:section>
   </div>

   <div class='sidebar' id='sidebar-left'><b:section class='side' id='sidebar1' preferred='yes'>
<b:widget id='Feed1' locked='false' title='FriendFeed - ptarjan' type='Feed'>
<b:includable id='main'>
   <h2><data:title/></h2>
   <div class='widget-content' expr:id='data:widget.instanceId + "_feedItemListDisplay"'>
     <span style='filter: alpha(25); opacity: 0.25;'>
       <a expr:href='data:feedUrl'><data:loadingMsg/></a>
     </span>
   </div>
   <b:include name='quickedit'/>
 </b:includable>
</b:widget>
<b:widget id='BlogArchive1' locked='false' title='Blog Archive' type='BlogArchive'>
<b:includable id='main'>
 <b:if cond='data:title'>
   <h2><data:title/></h2>
 </b:if>
 <div class='widget-content'>
 <div id='ArchiveList'>
 <div expr:id='data:widget.instanceId + "_ArchiveList"'>
   <b:if cond='data:style == "HIERARCHY"'>
    <b:include data='data' name='interval'/>
   </b:if>
   <b:if cond='data:style == "FLAT"'>
     <b:include data='data' name='flat'/>
   </b:if>
   <b:if cond='data:style == "MENU"'>
     <b:include data='data' name='menu'/>
   </b:if>
 </div>
 </div>
 <b:include name='quickedit'/>
 </div>
</b:includable>
<b:includable id='flat' var='data'>
 <ul>
   <b:loop values='data:data' var='i'>
     <li class='archivedate'>
       <a expr:href='data:i.url'><data:i.name/></a> (<data:i.post-count/>)
     </li>
   </b:loop>
 </ul>
</b:includable>
<b:includable id='menu' var='data'>
 <select expr:id='data:widget.instanceId + "_ArchiveMenu"'>
   <option value=''><data:title/></option>
   <b:loop values='data:data' var='i'>
     <option expr:value='data:i.url'><data:i.name/> (<data:i.post-count/>)</option>
   </b:loop>
 </select>
</b:includable>
<b:includable id='interval' var='intervalData'>
 <b:loop values='data:intervalData' var='i'>
     <ul>
       <li expr:class='"archivedate " + data:i.expclass'>
         <b:include data='i' name='toggle'/>
         <a class='post-count-link' expr:href='data:i.url'><data:i.name/></a>
           <span class='post-count' dir='ltr'>(<data:i.post-count/>)</span>
         <b:if cond='data:i.data'>
           <b:include data='i.data' name='interval'/>
         </b:if>
         <b:if cond='data:i.posts'>
           <b:include data='i.posts' name='posts'/>
         </b:if>
       </li>
     </ul>
 </b:loop>
</b:includable>
<b:includable id='toggle' var='interval'>
 <b:if cond='data:interval.toggleId'>
 <b:if cond='data:interval.expclass == "expanded"'>
   <a class='toggle' expr:href='data:widget.actionUrl + "&amp;action=toggle" +       "&amp;dir=close&amp;toggle=" + data:interval.toggleId +       "&amp;toggleopen=" + data:toggleopen'>
       <span class='zippy toggle-open'>▼ </span>
   </a>
 <b:else/>
   <a class='toggle' expr:href='data:widget.actionUrl + "&amp;action=toggle" +         "&amp;dir=open&amp;toggle=" + data:interval.toggleId +         "&amp;toggleopen=" + data:toggleopen'>
         <span class='zippy'>
           <b:if cond='data:blog.languageDirection == "rtl"'>
             ◄
           <b:else/>
             ►
           </b:if>
         </span>
   </a>
 </b:if>
</b:if>
</b:includable>
<b:includable id='posts' var='posts'>
 <ul class='posts'>
   <b:loop values='data:posts' var='i'>
     <li><a expr:href='data:i.url'><data:i.title/></a></li>
   </b:loop>
 </ul>
</b:includable>
</b:widget>
<b:widget id='AdSense1' locked='false' title='' type='AdSense'>
<b:includable id='main'>
 <div class='widget-content'>
   <data:adCode/>
 </div>
</b:includable>
</b:widget>
</b:section></div>

     <div id='crosscol-wrapper' style='text-align:center'>
       <b:section class='crosscol' id='crosscol' showaddelement='no'/>
     </div>

     <div id='center'><div id='squeeze'><div class='right-corner'><div class='left-corner'>
     <!-- begin content -->
     <div class='node'>
       <b:section class='main' id='main' showaddelement='no'>
<b:widget id='Blog1' locked='true' title='Blog Posts' type='Blog'>
<b:includable id='nextprev'>
 <div class='blog-pager hentry' id='blog-pager'>
   <b:if cond='data:newerPageUrl'>
     <span id='blog-pager-newer-link'>
     <a class='blog-pager-newer-link' expr:href='data:newerPageUrl' expr:id='data:widget.instanceId + "_blog-pager-newer-link"' expr:title='data:newerPageTitle'><data:newerPageTitle/></a>
     </span>
   </b:if>

   <b:if cond='data:olderPageUrl'>
     <span id='blog-pager-older-link'>
     <a class='blog-pager-older-link' expr:href='data:olderPageUrl' expr:id='data:widget.instanceId + "_blog-pager-older-link"' expr:title='data:olderPageTitle'><data:olderPageTitle/></a>
     </span>
   </b:if>

   <b:if cond='data:blog.homepageUrl != data:blog.url'>
     <a class='home-link' expr:href='data:blog.homepageUrl'><data:homeMsg/></a>
     <b:else/>
     <b:if cond='data:newerPageUrl'>
       <a class='home-link' expr:href='data:blog.homepageUrl'><data:homeMsg/></a>
     </b:if>
   </b:if>

 </div>
 <div class='clear'/>
</b:includable>
<b:includable id='backlinks' var='post'>
 <a name='links'/><h4><data:post.backlinksLabel/></h4>
 <b:if cond='data:post.numBacklinks != 0'>
   <dl class='comments-block' id='comments-block'>
     <b:loop values='data:post.backlinks' var='backlink'>
       <div class='collapsed-backlink backlink-control'>
         <dt class='comment-title'>
           <span class='backlink-toggle-zippy'> </span>
           <a expr:href='data:backlink.url' rel='nofollow'><data:backlink.title/></a>
           <b:include data='backlink' name='backlinkDeleteIcon'/>
         </dt>
         <dd class='comment-body collapseable'>
           <data:backlink.snippet/>
         </dd>
         <dd class='comment-footer collapseable'>
           <span class='comment-author'><data:post.authorLabel/> <data:backlink.author/></span>
           <span class='comment-timestamp'><data:post.timestampLabel/> <data:backlink.timestamp/></span>
         </dd>
       </div>
     </b:loop>
   </dl>
 </b:if>
 <p class='comment-footer'>
   <a class='comment-link' expr:href='data:post.createLinkUrl' expr:id='data:widget.instanceId + "_backlinks-create-link"' target='_blank'><data:post.createLinkLabel/></a>
 </p>
</b:includable>
<b:includable id='post' var='post'>
  <div class="hentry post">
   <a expr:name='data:post.id'/>
   <b:if cond='data:post.title'>
     <h2 class="entry-title post-title">
    <b:if cond='data:post.link'>
      <a expr:href='data:post.link' rel="bookmark"><data:post.title/></a>
    <b:else/>
       <b:if cond='data:post.url'>
         <a expr:href='data:post.url' rel="bookmark"><data:post.title/></a>
       <b:else/>
         <data:post.title/>
       </b:if>
    </b:if>
     </h2>
   </b:if>
  
   <span class='submitted'>
     Posted On <data:post.dateHeader/>
     <b:if cond='data:top.showTimestamp'>
       at
       <data:top.timestampLabel/>
       <b:if cond='data:post.url'>
         <a class='timestamp-link' expr:href='data:post.url' rel='bookmark' title='permanent link'><abbr class='published' expr:title='data:post.timestampISO8601'><data:post.timestamp/></abbr></a>
       </b:if>
     </b:if> by <span class="vcard author fn"><data:post.author/></span>
    
       <!-- email post links -->
       <b:if cond='data:post.emailPostUrl'>
         <span class='item-action'>
         <a expr:href='data:post.emailPostUrl' expr:title='data:top.emailPostMsg'>
           <span class='email-post-icon'> </span>
         </a>
         </span>
       </b:if>

       <!-- quickedit pencil -->
       <b:include data='post' name='postQuickEdit'/>
    
   </span>

   <div class='content entry-content'>
     <data:post.body/></p>
     <div style='clear: both;'/> <!-- clear for photos floats -->
   </div>
  
   <div class='meta'>
       Posted in  <b:if cond='data:post.labels'>
         <data:postLabelsLabel/>
         <b:loop values='data:post.labels' var='label'>
           <a expr:href='data:label.url' rel='tag'><data:label.name/></a><b:if cond='data:label.isLast != "true"'>,</b:if>
         </b:loop>
       </b:if> |

       <b:if cond='data:blog.pageType != "item"'>

         <b:if cond='data:post.allowComments'>
           <a class='comment-link' expr:href='data:post.addCommentUrl' expr:onclick='data:post.addCommentOnclick'><b:if cond='data:post.numComments == 1'>1 <data:top.commentLabel/><b:else/><data:post.numComments/> <data:top.commentLabelPlural/></b:if></a>
         </b:if>
       </b:if>
  

      <!-- backlinks -->
        <b:if cond='data:blog.pageType != "item"'>
          <b:if cond='data:post.showBacklinks'>
            <a class='comment-link' expr:href='data:post.url + "#links"'><data:top.backlinkLabel/></a>
          </b:if>
        </b:if>
   </div>
  </div>
</b:includable>
<b:includable id='commentDeleteIcon' var='comment'>
 <span expr:class='"item-control " + data:comment.adminClass'>
   <a expr:href='data:comment.deleteUrl' expr:title='data:top.deleteCommentMsg'>
     <span class='delete-comment-icon'> </span>
   </a>
 </span>
</b:includable>
<b:includable id='status-message'>
 <b:if cond='data:navMessage'>
 <div class='status-msg-wrap'>
   <div class='status-msg-body'>
     <data:navMessage/>
   </div>
   <div class='status-msg-border'>
     <div class='status-msg-bg'>
       <div class='status-msg-hidden'><data:navMessage/></div>
     </div>
   </div>
 </div>
 <div style='clear: both;'/>
 </b:if>
</b:includable>
<b:includable id='feedLinks'>
 <b:if cond='data:blog.pageType != "item"'> <!-- Blog feed links -->
   <b:if cond='data:feedLinks'>
     <div class='blog-feeds'>
       <b:include data='feedLinks' name='feedLinksBody'/>
     </div>
   </b:if>

   <b:else/> <!--Post feed links -->
   <div class='post-feeds'>
     <b:loop values='data:posts' var='post'>
       <b:if cond='data:post.allowComments'>
         <b:if cond='data:post.feedLinks'>
           <b:include data='post.feedLinks' name='feedLinksBody'/>
         </b:if>
       </b:if>
     </b:loop>
   </div>
 </b:if>
</b:includable>
<b:includable id='comment-form' var='post'>
 <div class='comment-form'>
   <a name='comment-form'/>
   <h4 id='comment-post-message'><data:postCommentMsg/></h4>
   <data:blogCommentMessage/></p>
   <data:blogTeamBlogMessage/>
   <a expr:href='data:post.commentFormIframeSrc' id='comment-editor-src'/>
   <iframe allowtransparency='true' class='blogger-iframe-colorize blogger-comment-from-post' frameborder='0' height='275' id='comment-editor' name='comment-editor' scrolling='no' src='' width='100%'/>
   <data:post.friendConnectJs/>
   <data:post.cmtfpIframe/>
   <script type='text/javascript'>
     BLOG_CMT_createIframe('<data:post.appRpcRelayPath/>', '<data:post.communityId/>');
   </script>
 </div>
</b:includable>
<b:includable id='backlinkDeleteIcon' var='backlink'>
 <span expr:class='"item-control " + data:backlink.adminClass'>
   <a expr:href='data:backlink.deleteUrl' expr:title='data:top.deleteBacklinkMsg'>
     <span class='delete-comment-icon'> </span>
   </a>
 </span>
</b:includable>
<b:includable id='feedLinksBody' var='links'>
 <div class='feed-links'>
 <data:feedLinksMsg/>
 <b:loop values='data:links' var='f'>
    <a class='feed-link' expr:href='data:f.url' expr:type='data:f.mimeType' target='_blank'><data:f.name/> (<data:f.feedType/>)</a>
 </b:loop>
 </div>
</b:includable>
<b:includable id='postQuickEdit' var='post'>
 <b:if cond='data:post.editUrl'>
   <span expr:class='"item-control " + data:post.adminClass'>
     <a expr:href='data:post.editUrl' expr:title='data:top.editPostMsg'>
       <span class='quick-edit-icon'> </span>
     </a>
   </span>
 </b:if>
</b:includable>
<b:includable id='comments' var='post'>
   <a name='comments'/>
   <b:if cond='data:post.allowComments'>
     <h3 id='comments'>
       <b:if cond='data:post.numComments == 1'>
         1 <data:commentLabel/>:
       <b:else/>
         <data:post.numComments/> <data:commentLabelPlural/>:
       </b:if>
     </h3>

     <ol class='commentlist'>
       <b:loop values='data:post.comments' var='comment'>
         <li>
           <a expr:name='"comment-" + data:comment.id'/>
           <cite>
           <b:if cond='data:comment.authorUrl'>
             <a expr:href='data:comment.authorUrl' rel='nofollow'><data:comment.author/></a>
           <b:else/>
             <data:comment.author/>
           </b:if>
           </cite> Says:
           <small class='commentmetadata'><a expr:href='"#comment-" + data:comment.id' title='comment permalink'>
               <data:comment.timestamp/>
             </a>
             <b:include data='comment' name='commentDeleteIcon'/>
           </small>
             <b:if cond='data:comment.isDeleted'>
             <span class='deleted-comment'><data:comment.body/></span>
           <b:else/>
             <data:comment.body/></p>
           </b:if>
         </li>
       </b:loop>
     </ol>

     <p class='comment-footer'>
       <a expr:href='data:post.addCommentUrl' expr:onclick='data:post.addCommentOnclick'><data:postCommentMsg/></a>
     </p>
   </b:if>

   <div id='backlinks-container'>
   <div expr:id='data:widget.instanceId + "_backlinks-container"'>
      <b:if cond='data:post.showBacklinks'>
        <b:include data='post' name='backlinks'/>
      </b:if>
   </div>
   </div>
</b:includable>
<b:includable id='main' var='top'>
 <!-- posts -->
 <div class='post hfeed'>

   <b:include data='top' name='status-message'/>

   <b:loop values='data:posts' var='post'>
     <b:include data='post' name='post'/>
     <b:if cond='data:blog.pageType == "item"'>
       <b:include data='post' name='comments'/>
     </b:if>
   </b:loop>
 </div>

 <!-- navigation -->
 <b:include name='nextprev'/>

 <!-- feed links -->
 <b:include name='feedLinks'/>
</b:includable>
</b:widget>
</b:section></div><!-- end content --><!-- spacer for skins that want sidebar and main to be the same height--><div class='clear'> </div><div id='footer-wrapper'><b:section class='footer' id='footer'/></div></div></div></div></div> <!-- /.left-corner, /.right-corner, /#squeeze, /#center --><div class='sidebar' id='sidebar-right'><b:section class='side' id='sidebar2' preferred='yes'>
<b:widget id='Profile1' locked='false' title='About Me' type='Profile'>
<b:includable id='main'>
   <b:if cond='data:title != ""'>
     <h2><data:title/></h2>
   </b:if>
   <div class='widget-content'>
   <b:if cond='data:team == "true"'> <!-- team blog profile -->
     <ul>
       <b:loop values='data:authors' var='i'>
         <li><a expr:href='data:i.userUrl'><data:i.display-name/></a></li>
       </b:loop>
     </ul>

     <b:else/> <!-- normal blog profile -->

     <b:if cond='data:photo.url != ""'>
       <a expr:href='data:userUrl'><img class='profile-img' expr:alt='data:photo.alt' expr:height='data:photo.height' expr:src='data:photo.url' expr:width='data:photo.width'/></a>
     </b:if>

     <dl class='profile-datablock'>
       <dt class='profile-data'><data:displayname/></dt>

       <b:if cond='data:showlocation == "true"'>
         <dd class='profile-data'><data:location/></dd>
       </b:if>

       <b:if cond='data:aboutme != ""'><dd class='profile-textblock'><data:aboutme/></dd></b:if>
     </dl>
     <a class='profile-link' expr:href='data:userUrl'><data:viewProfileMsg/></a>
   </b:if>

    <b:include name='quickedit'/>
   </div>
 </b:includable>
</b:widget>
<b:widget id='HTML1' locked='false' title='My Other Internet Stuff' type='HTML'>
<b:includable id='main'>
 <!-- only display title if it's non-empty -->
 <b:if cond='data:title != ""'>
   <h2 class='title'><data:title/></h2>
 </b:if>
 <div class='widget-content'>
   <data:content/>
 </div>

 <b:include name='quickedit'/>
</b:includable>
</b:widget>
<b:widget id='Followers1' locked='false' title='Followers' type='Followers'>
<b:includable id='main'>
 <b:if cond='data:title != ""'>
   <b:if cond='data:codeSnippet != ""'>
     <h2 class='title'><data:title/></h2>
   <b:else/>
     <b:if cond='data:totalFollowerCount != ""'>
       <h2 class='title'><data:title/> (<data:totalFollowerCount/>)</h2>
     </b:if>
   </b:if> 
 </b:if>
 <div class='widget-content'>
   <div expr:id='data:widget.instanceId + "-wrapper"'>
     <b:if cond='data:codeSnippet != ""'>
       <div style='margin-right:2px;'>
         <data:codeSnippet/>
       </div>
     <b:else/>
       <b:if cond='data:totalFollowerCount == ""'>
         <span class='item-control following-not-admin'>
           <b><data:failureSnippet/></b>
         </span>
         <span class='item-control blog-admin'>
           <b><data:adminFailureSnippet/></b>
         </span>
       <b:else/>
         <b:if cond='data:followingLinkPresent'>
           <div class='follow-this profile-link item-control following-follow-this'>
             <a expr:href='"javascript:_FollowersView._openPopup(\"" + data:followUri + "\");"'>
               <data:followThisMessage/>
             </a>
           </div>
           <div class='follow-this profile-link item-control following-stop-following-this'>
             <a expr:href='"javascript:_FollowersView._openPopup(\"" + data:followUri + "\");"'>
               <data:stopFollowingMessage/>
             </a>
           </div>
         </b:if>

         <div class='followers-grid'>
           <b:if cond='data:totalFollowerCount == 0'>
             <div class='profile-link item-control following-follow-this'>
               <data:emptyFollowersMessage/>
             </div>
           </b:if>
           <!--
           Relies on the js written out in navbar.gxp
           -->
           <b:loop values='data:followers' var='follower'>
             <div class='follower'>
               <a expr:href='data:follower.profileUrl' expr:title='data:follower.displayName' rel='nofollow'>
               <img class='follower-img' expr:alt='data:follower.displayName' expr:height='data:follower.imageHeight' expr:onerror='"this.onerror=null;this.src=\"" + data:anonFollowerImageUrl + "\";"' expr:onload='"setAttributeOnload(this, \"src\", \"" + data:follower.imageUrl + "\")"' expr:width='data:follower.imageWidth' src='http://img1.blogblog.com/img/blank.gif'/>
               </a>
             </div>
           </b:loop>
           <div class='clear'/>
         </div>

         <div class='followers-canvas profile-link'>
           <data:followersFooterMessage/>
           <span class='item-control following-not-admin'>
             <a expr:href='data:followersUri'>
               <data:viewAllMessage/>
             </a>
           </span>
           <span class='item-control blog-admin'>
             <a expr:href='data:manageFollowersUri'>
               <data:manageFollowersMessage/>
             </a>
           </span>
         </div>
         </b:if>
     </b:if>
   </div>
   <b:include name='quickedit'/>
 </div>
</b:includable>
</b:widget>
</b:section><p style='margin:0 0 0 20px'/></div>
  
   </div> <!-- /container -->
   </div>

</body>
</html>
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
{% endhighlight %}
