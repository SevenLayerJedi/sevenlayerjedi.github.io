---
layout: single
title: Control - Hack The Box
excerpt: "A Google dork query is a search string that uses advanced search operators to find information that is not readily available on a website. Google dorking, also known as Google hacking, can return information that is difficult to locate through simple search queries.
In this tutorial we will using Google to gather more sensitive information about target."
date: 2020-04-29
classes: wide
header:
  teaser: /assets/images/google-dorks-cheat-sheet/m1.jpg
  teaser_home_page: true
  icon: /assets/images/thumbs-up-icon.png
categories:
  - cheat sheet
tags:
  - cheat sheet
  - google dork
---

![](/assets/images/google-dorks-cheat-sheet/m1.jpg)

## SUMMARY

A Google dork query is a search string that uses advanced search operators to find information that is not readily available on a website. Google dorking, also known as Google hacking, can return information that is difficult to locate through simple search queries.
In this tutorial we will using Google to gather more sensitive information about target.

## REFERENCES
  - https://hydrasky.com/network-security/information-gathering-use-google-dork/
  - https://www.exploit-db.com/google-hacking-database/
  - https://www.blackhat.com/presentations/bh-europe-05/BH_EU_05-Long.pdf
  - http://securityidiots.com/Web-Pentest/Information-Gathering/Part-2-information-Gathering-with-Google.html

## GOOGLE DORK QUERY

### INURL
InUrl is used to search for any text inside the uri. Many times used by hackers to search for vulnerable scripts and plugins or sensitive information in the website.
Example: inurl:/status?full=true will return all url contain keyword “tatus?full=true”

### ALLINURL
If you search with allinurl: Google restricts results to those containing all the query terms you specify in the URL.
Example: allinurl:google dork will return all url contain keyword “google” and “dork”

### INTEXT
InText is used to search for any text in the body or the source code of the website. It is many times used by hackers to search for particular version of application which is exploitable.
Example: intext: google dork will return website contain keyword “google dork” in html page.

### ALLINTEXT
If you search with allintext: Google restricts results to those containing all the query terms you specify in the text of the page.

### FILETYPE
FileType is used to search for any type of file which you want to locate in a particualr website or on any particular subject or you can search for any type of file freely. Used by hackers to search for files containing Sensitive information for exploit the websites.

### INTITLE
InTitle is used to search for titles of the webpages. Hackers use to to search for vulnerable pages or the indexing on a website.

### ALLINTITLE
If search with allinurl: Google restricts results to those containing all the query terms you specify in the title.

### SITE
Using this dork you can minimize the area of search to a particular website. Hackers use it to target and search sentive information in a website.

### LINK
This dork checks other websites containing links to a website. Hackers use to search any other information related to thier target.

### CACHE
url will display Google’s cached version of a web page, instead of the current version of the page.

## EXAMPLES

### Getting Open Index or Insecure Information
```
intitle:"index of /" Parent Directory site:example.com
```

### Search for admin directories
```
intitle:"Index of /admin" site:example.com
```

### Search for password directories
```
intitle:"Index of /password" site:example.com
```

### Search for mail directories
```
intitle:"Index of /mail" site:example.com
```

### Search for files like passwd
```
intitle:"Index of /" passwd site:example.com
```

### Search for password.txt files
```
intitle:"Index of /" password.txt site:example.com
```

### Search for htaccess file
```
intitle:"Index of /" .htaccess site:example.com
```

### Search for diffrent extensions.
```
intitle:"index of ftp" .mdb site:example.com

### Search admin pages or the login functionalities
```
Intitle: "login" "admin" site:example.com
```

### Search for Admin Login Functionality on target
```
inurl:admin site:example.com
```

### Search for Login Functionality on target
```
inurl:login site:example.com
```

### Searching for text files containing passwd in URL on target
```
inurl:passwd filetype:txt site:example.com
```

### Searching for db files containing admin in URL on target
```
inurl:admin filetype:db site:example.com
```

### Searching for logs on target domain
```
filetype:log site:example.com
```

### Searching for Excel and csv files on target
```
filetype:xls csv site:example.com
```
