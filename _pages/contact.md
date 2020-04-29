---
title: "Contact"
permalink: /contact/
date: 2019-02-15
---

{% assign author = page.author | default: page.authors[0] | default: site.author %} {% assign author = site.data.authors[author] | default: author %} 
{% if author.avatar %} 
{% if author.avatar contains "://" %} {% assign author_src = author.avatar %} {% else %} {% assign author_src = author.avatar | relative_url %} {% endif %} {% if author.home %} {% if author.home contains "://" %} {% assign author_link = author.home %} {% else %} {% assign author_link = author.home | relative_url %} {% endif %}  {% else %}  {% endif %} 
{% endif %} 
{% if author.home %} 
{{ author.name }}
{% else %} 
{{ author.name }}
{% endif %} {% if author.bio %} 
{{ author.bio }} 
{% endif %} 
{{ site.data.ui-text[site.locale].follow_label | remove: ":" | default: "Follow" }} 
{% if author.location %} 
{{ author.location }} 
{% endif %} {% if author.links %} {% for link in author.links %} {% if link.label and link.url %} 
{{ link.label }}
{% endif %} {% endfor %} {% endif %} {% if author.uri %} 
{{ site.data.ui-text[site.locale].website_label | default: "Website" }} 
{% endif %} {% if author.email %} 
{{ site.data.ui-text[site.locale].email_label | default: "Email" }} 
{% endif %} {% if author.keybase %} 
Keybase 
{% endif %} {% if author.twitter %} 
Twitter 
{% endif %} {% if author.facebook %} 
Facebook 
{% endif %} {% if author.google_plus %} 
Google+ 
{% endif %} {% if author.linkedin %} 
LinkedIn 
{% endif %} {% if author.xing %} 
XING 
{% endif %} {% if author.instagram %} 
Instagram 
{% endif %} {% if author.tumblr %} 
Tumblr 
{% endif %} {% if author.bitbucket %} 
Bitbucket 
{% endif %} {% if author.github %} 
GitHub 
{% endif %} {% if author.gitlab %} 
GitLab 
{% endif %} {% if author.stackoverflow %} 
Stack Overflow 
{% endif %} {% if author.lastfm %} 
Last.fm 
{% endif %} {% if author.dribbble %} 
Dribbble 
{% endif %} {% if author.pinterest %} 
Pinterest 
{% endif %} {% if author.foursquare %} 
Foursquare 
{% endif %} {% if author.steam %} 
Steam 
{% endif %} {% if author.youtube %} {% if author.youtube contains "://" %} 
YouTube 
{% else author.youtube %} 
YouTube 
{% endif %} {% endif %} {% if author.soundcloud %} 
SoundCloud 
{% endif %} {% if author.weibo %} 
Weibo 
{% endif %} {% if author.flickr %} 
Flickr 
{% endif %} {% if author.codepen %} 
CodePen 
{% endif %} {% if author.vine %} 
Vine 
{% endif %} {% include author-profile-custom-links.html %} 
