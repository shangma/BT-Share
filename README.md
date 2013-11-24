# funny resource share via BT

It is a funny bt search engine...hmm , not really funny if you cant find what you want XD...

I hope the tech stack don't scare you, and if you find the protocol documents just hard to read, just read the code or read the inspired ones...


features(alpha)
--------
- seed search with the help of [DHT][4] collecters and violent crawlers.


code structure
-------------
- web

   Web module is built on tornado, and use it to provide seed search at 80 port.
- [crawler][11]

   Crawler module runs a lot of spiders to crawl bittorents from serveral famous web sites.
- [mdht][12]

   MDHT module is built on [twisted][3], and use it as a fake bittorent client to collect resouces' hashinfo from the [dht][4] network.


tech detail
-----------
- FrontEnd
  - JQ
  - requirejs
  - bootstrap
  - less
  - coffeescript

- BackEnd
  - tornado
  - twisted
  - mondodb
  - redis
  - gevent


todo
----
* take it on linode
* add a changer scripts to make magnet to bitorrent
* spider routine
  * script
  * better
    * scrapy
    * based on gevent
* dht protocol
  * write test
  * write document(wiki)
* distributed spiders
  * rewrite it into gevent
  * write documents
  * write test
* mem cached
* error check
  * custom erro type, like NoneExitError/EmptyResultError...
* security check
  * search input (go check wordpress)
  * xss
* manage
  * process monitor(maybe)
  * backend manage(refer the lixian.xunlei UI)
  * warm sys
* full text search(maybe sphinx?)
  * chinese search
  * description search
* community features
  * session support
  * the thrid login
  * comment(anonymous is ok)
  * share(twitter/weibo/google+)
  * IRC chat server demo??
* change linode py to pypy


dev log
--------
* `2013.11.24`
  * dht protocol, make the collecter work
* `2013.11.14`
  * tornado async request how-to
  * mongodb async request how-to
* `2013.11.11`
  * reconstruct model layers to hold data within the life of application
  * make a connection pool
  * redesing the seed table
    * page id
    * data transfer
  * add error handling, a weak type
* `2013.11.9-2013.11.10`
  * add model layer
  * fix page error bug
* `2013.11.1`
  * reconstruct the code and remove the gruntJS support to make it easy to build
* `2013.10.31` integrate the [mdht][1]
* `2013.09.08` get time to dev my spider
* `2013.4.17`  make it happen


inspired by
-----------
- [xiaoxia][2]

   he has made a search engine, based on dht, but no open sources.
- [gsko/mdht][6]

   i build my mdht based on his implementation.
- [kevinlynx/dhtcrawler][7]

    thanks to kevinlynx,his dhtcrwaler code really helps me to make understand what those f**king documents was saying.
- [daydayfree/diggit][8]

   i try to simulate the code structure from daydayfree's code, specially how to add the model layer and db layer to tornado.
- [3n1b-com/3n1b.com][9]

   i learned how to make my handlers live longer in the app life cycle and more.
- [lvyaojia/crawler][10]

   i use the code to implement the crawler module and change it to suit my need.
   May rewrite it to gevent by my own.


[1]: https://github.com/zhkzyth/mdht
[2]: http://xiaoxia.org/2013/05/11/magnet-search-engine/
[3]: http://en.wikipedia.org/wiki/Twisted_%28software%29
[4]: http://www.bittorrent.org/beps/bep_0005.html
[6]: https://github.com/gsko/mdht
[7]: https://github.com/kevinlynx/dhtcrawler
[8]: https://github.com/daydayfree/diggit
[9]: https://github.com/3n1b-com/3n1b.com
[10]: https://github.com/lvyaojia/crawler
[11]: https://github.com/zhkzyth/a-super-fast-crawler
[12]: https://github.com/zhkzyth/mdht
