---
layout: slides
title: Open Data API 101 @ NYC 
---

<!-- ![Snuffie!](/presentations/img/snuffie_nyc_sod.png) -->

## _Open Data API 101_ with _Socrata_

===

# Who the _heck_ are _you_?

---


![Hello](/presentations/img/hello_world.png)

---

![Fullscreen](/presentations/img/at_table.jpg)

## We build _software_ to make data _more useful_ to _more people_

<!-- https://www.flickr.com/photos/hyku/2497370097 -->
--- 

![Fullscreen](/presentations/img/city.jpg)

<h2>We believe that _greater access_ to _public data_ makes cities _better places to live_</h2>

---

![Fullscreen](/presentations/img/city_hall.jpg)

<h2>We make it _easy_ for _governments_ to share their public data with _civic hackers_</h2>

===

## _civic hacker_ _(n)_

_One who collaborates with others_ to create, build, and invent open source solutions using publicly-released data, code and technology _to solve social, economic, and environmental challenges_ relevant to their _neighborhood, city, state, or country_.

---

## _Hacking_ drives _civic innovation_

![Innovate](/presentations/img/innovate.png)

---

## _Help_ your _community_!

![Help!](https://media2.giphy.com/media/IvlKeD6BEA1hu/200.gif)

---

## _Network_ and _have fun_!

![#openbeers](/presentations/img/openbeers.jpg)

===

# How can I _get involved?_

---

<img class="fullscreen-img" src="/presentations/img/hackathon.jpg" />

## Attend _events_ and _meetups_
<h3 class="fragment">... because civic hackathons are special</h3>

---

<img class="fullscreen-img" src="/presentations/img/community_meeting.jpg"/>

## Involve your _community_
<h3 class="fragment">... because they know where the pain is</h3>

<!-- https://www.flickr.com/photos/usacehq/14358340888 -->

---

<img class="fullscreen-img" src="/presentations/img/mayor_emmanuel.jpg"/>

## Work with the _government_
<h3 class="fragment">... and push them to do better</h3>

<!-- https://www.flickr.com/photos/juggernautco/5172631566 -->

---

<img class="fullscreen-img" src="/presentations/img/shoveling_shit.jpg"/>

## _Clean_ &amp; _sanitize_ data
<h3 class="fragment">... because it's hard and it sucks</h3>

<!-- https://www.flickr.com/photos/asplund/14000712061/in/photostream/ -->

---

<img class="fullscreen-img" src="/presentations/img/chalkboard.jpg"/>

## Show _your work_
<h3 class="fragment">... and share your code</h3>

---

<img class="fullscreen-img" src="/presentations/img/aqueduct.jpg"/>

## Build for the _long term_
<h3 class="fragment">... but don't be afraid to try things out!</h3>

===


# The _Socrata_
# _Open Data APIs_

---

## _Finding_ _Data_

### [odata.cityofnewyork.us](http://data.cityofnewyork.us/)
### [opendatanetwork.com](http://www.opendatanetwork.com)

---

### In the _Dataset View_

![Sidebar](http://dev.socrata.com/img/sidebar.gif)

---

## In _Data Lens_

![Data Lens](http://dev.socrata.com/img/data_lens.png)

---

## Example: Legally Operating Businesses

[data.cityofnewyork.us/d/w7w3-xahh](https://data.cityofnewyork.us/Business/Legally-Operating-Businesses/w7w3-xahh)

---

## Simple Filters

<code>
/resource/p2mh-mrfv.json?<span class="toy-store-blue">license_category</span>=<span class="golden">Laundry Jobber</span>
</code>

<pre><code data-trim contenteditable class="javascript">
[ {
"address_borough": "Manhattan",
"address_building": "250",
"address_city": "NEW YORK",
"address_state": "NY",
"address_street_name": "E 40TH ST",
"address_zip": "10016",
"business_name": "QUIET WATERS CLEANER INC",
"business_name_2": "HIGH POINT CLEANERS",
"contact_phone": "2129221075",
"latitude": "40.748710030908676",
"lic_expir_dd": "2017-12-31T00:00:00.000",
"license_category": "Laundry Jobber",
"license_nbr": "2044909-DCA",
"license_type": "Business",
"longitude": "-73.9735670320491"
}, ...]
</code></pre>

---

## SoQL Queries

<code>
/resource/p2mh-mrfv.json?<br/>
<span class="toy-store-blue">$where</span>=<span class="golden">business_name LIKE '%METCALF%'</span>
</code>

<small style="padding-top: 5em">For more details see <a href="http://dev.socrata.com">dev.socrata.com</a></small>

---

## Aggregating Data

<code>
/resource/p2mh-mrfv.json?<br/>
<span class="toy-store-blue">$select</span>=<span class="golden">COUNT(*)</span><br>
<span class="toy-store-blue">license_category</span>=<span class="golden">Laundry Jobber</span><br>
</code>

<pre class="fragment"><code data-trim contenteditable class="javascript">
[ { "count": "1612" } ]
</code></pre>

---

## Paging Through Data

<code contenteditable>
/resource/p2mh-mrfv.json?<br/>
<span class="toy-store-blue">$limit</span>=<span class="golden">50</span><br/>
&amp;<span class="toy-store-blue">$offset</span>=<span class="golden">100</span>
</code>

---

## Application Tokens

1. Register at [http://dev.socrata.com/register](http://dev.socrata.com/register)
2. Include as:
  - _`X-App-Token: $token`_ HTTP Header or ... 
  - The _`$$app_token`_`=`_`$token`_ URL parameter
3. Profit!!! (from more API requests)

===

# Help!

---

## Developer Portal

# [dev.socrata.com](http://dev.socrata.com)

<div class="footnote">Community powered! Learn how to <a href="http://dev.socrata.com/contributing.html">contribute</a>.</div>

---

## Libraries &amp; SDKs

<img src="/presentations/img/socrata-heart-opensource.png"/>

### [dev.socrata.com/libraries/](http://dev.socrata.com/libraries/)

<div class="footnote"><a href="http://socrata.github.io/soda-ruby/">Ruby</a>, <a href="https://github.com/socrata/soda-scala">Scala</a>, <a href="http://socrata.github.io/soda-java/">Java</a>, <a href="https://github.com/socrata/soda-ios-sdk">ObjectiveC</a>, <a href="https://github.com/Chicago/RSocrata">R</a>, <a href="https://github.com/socrata/soda-swift">Swift</a>, etc.</div>

--- 

## Getting Help

![Getting Help](/presentations/img/live-support.gif)

- Track me down!
- IRC: [dev.socrata.com/irc.html](http://dev.socrata.com/irc.html)
- Stack Overflow: [soda](http://stackoverflow.com/questions/tagged/soda) or [socrata](http://stackoverflow.com/questions/tagged/socrata)

===

![Let's get this party started!](/presentations/img/lets_get_this_party_started.gif)

## [bit.ly/nyc-sod-apis](http://bit.ly/nyc-sod-apis)

===

![Fullscreen](/presentations/img/work_tounge.gif)

## One more thing...

<h1 class="fragment" data-fragment-index="0">We're hiring!</h1>

<h2 class="fragment" data-fragment-index="1"><a href="http://careers.socrata.com">careers.socrata.com</a></h2>

===

# _Thanks!_

![Snuffie!](/presentations/img/snuffie_nyc_sod.png)
