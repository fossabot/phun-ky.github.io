---
layout: page
title: lover of life, technologist at heart
tagline: The world from my point of view, and some pedantic creativity
---
{% include JB/setup %}

<div class="container">
  <div class="row">
    <div class="col-md-12">
      <div class="well about_the_author clearfix">
        <h3>About the author</h3>
        <img width="220" height="220" src="https://secure.gravatar.com/avatar/e4885fa3c6db55194cb2eb9e81dac456?s=220" class="avatar" alt="Image of the author, Alexander"/>
        <p>
          Hi! My name is Alexander, and I write about open source, frontend development, technological stuff and everything in between.
        </p>
        <p>
          If you want to know more about me, here is some links you might want to check out: <a href="https://github.com/phun-ky">GitHub</a>, <a href="https://twitter.com/phun_ky">Twitter</a>, <a href="https://nb-no.facebook.com/phunky.net">Facebook</a>, <a href="http://no.linkedin.com/in/alexanderroyne">LinkedIn</a>, <a href="http://codepen.io/phun-ky/">CodePen</a>, <a href="https://plus.google.com/109212745239771225705/posts">Google +</a>, <a href="http://osrc.dfm.io/phun-ky">My open source report card</a>, <a href="https://www.vizify.com/alexander-vassbotn-ryne-helgesen/">Vizify</a>, <a href="https://geekli.st/ph001">Geeklist</a>, <a href="https://launchpad.net/~alexander-phun-ky">Launchpad</a>, <a href="http://slid.es/phun_ky/">Slid.es</a>, <a href="https://www.npmjs.org/~phun-ky">npm</a>, <a href="http://www.flickr.com/photos/phun-ky/">Flickr</a>
        </p>
      </div>
    </div>
  </div>
  <div class="row">
    <div class="col-md-12">

      <h3>All my posts</h3>

      <ul class="posts">
        {% for post in site.posts %}
          <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
        {% endfor %}
      </ul>

    </div>
  </div>
</div>
