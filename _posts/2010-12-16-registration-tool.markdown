---
layout: post
title: Facebook Registration Tool
tags:
- facebook
---
*Republished from [Facebook Developer's Blog](http://developers.facebook.com/blog/post/440)*

Today we're launching a new [registration tool][1] that gives website owners the ability to offer quick, easy and social options for sign-up.

It is an excellent alternative to using [Facebook Login (formerly Facebook Connect)][2] when: 
*   you want to provide an option for users without Facebook accounts 
*   your site needs additional information that Facebook doesn't provide
*   a traditional HTML form suits your site more

By minimizing the friction associated with signing up for a new account and making it easy for people to bring their friends with them, we've seen that people are more likely to complete the sign up process, stay on sites longer, share more content, and come back more often. For example, in beta tests with [FriendFeed][3], Facebook sign ups increased 300%.

![][4] 

## How it works
The [registration tool][5] is an iframe that websites can add with just one line of code, and customize to request the specific fields required to create an account. When a user is logged into Facebook and arrives at the registration tool on a website, they'll see that the form is prefilled with the relevant information he or she has already shared on their Facebook profile. Users can see the specific information the site is requesting of them, giving them more control to decide whether to sign up. 

The site can request information stored on Facebook (e.g., name, verified email address, current location, etc.) or custom information (e.g., text fields, checkboxes, dropdown menus, security checks, typeaheads, etc.). Users can decide whether to share their information with the site by clicking "Register," or if a Facebook account isn't required by the site, select an option to fill out the form manually. Because the tool works through an iframe, no data is shared with the website until the user clicks "Register."

When a user registers for the site with their Facebook account (similar to Facebook Login), the site is given permission to access the user's basic information on Facebook in addition to the data presented in the form, and in turn can provide the user with a personalized and social experience.

## Getting started
To integrate the registration tool, simply add the iframe or XFBML to your site:

Using iframe:

    <iframe src="http://www.facebook.com/plugins/registration.php?
                 client_id=113869198637480&
                 redirect_uri=http%3A%2F%2Fdevelopers.facebook.com%2Ftools%2Fecho%2F&
                 fields=name,birthday,gender,location,email" 
            scrolling="auto" 
            frameborder="no" 
            style="border:none;" 
            allowTransparency="true"
            width="100%" 
            height="310px">
    </iframe>

The `redirect-uri` should point to the page which will process your `signed_request`. You can customize the `fields` attribute to suit your needs. See the [docs][6] for a list of valid fields.

Using XFBML:

    <fb:registration 
      fields="name,birthday,gender,location,email" 
      redirect-uri="http://developers.facebook.com/tools/echo/">
    </fb:registration>

The `redirect-uri` and `fields` are identical to above. You must use your own [app_id][7] for the `redirect-uri` to be on your domain.

For more details on getting started with your implementation, please visit our [technical documentation][5]. 

We hope you'll try it out and let us know what you think.

*Paul, an engineer on the Platform team, will register for your site if you use this tool. 1 more user!*

 [1]: http://www.facebook.com/about/login
 [2]: http://developers.facebook.com/docs/guides/web#login
 [3]: https://friendfeed.com/account/create?formonly=1
 [4]: http://developers.facebook.com/attachment/registration_tool_blog_example.png
 [5]: http://developers.facebook.com/docs/user_registration
 [6]: http://developers.facebook.com/docs/user_registration#named_fields
 [7]: http://www.facebook.com/developers/
