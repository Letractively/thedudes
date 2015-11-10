# Introduction #

This topic will detail how to add <i>Movie Dude</i> support to new sites.

# Example definition (Amazon US) #
```
am_us: {
	name: "Amazon",
	xpath: "//b[@class='sans']",
	icon: "http://www.amazon.com/favicon.ico",
	link: "http://www.amazon.com/s/?url=search-alias%3Ddvd&field-keywords={search}", 
	scanURL:"amazon.com",
			
	validPage: function(pageTitle){return (pageTitle.indexOfAny(["DVD:", "movie info:"]) > -1);}
},
```

# Site properties #

A site definition object has the following properties:

  * `name`: The display name of this site. Used in the tooltip. _Required._
  * `xpath`: The xpath expression used to retreive the object title. _Optional._
  * `icon`: The URL of the icon to display in this site's link. Maybe be a `data:` URL. _Optional._
  * `link`: The URL used to link to this site. See link replacement vars. _One of: [link,form]._

# Link Replacement Variables #

**`{search}`**

A single variable, `{search}`, is provided for site link definitions. It is replaced with the URL-encoded title of the current object.

