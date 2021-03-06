# Kibana3 With Support for Elasticsearch Aggregations and Version 2.x


__NOTE__: You have reached a forked Kibana 3 repository created with the intent to be compatible with Elasticsearch 
version 2.x. Support has been added to remove the deprecated facets approach and leverage the power of Elasticsearch 
aggregations instead.  While Kibana 4 is a powerful analytics tool there is something to be said for the simplicity and 
ease of data exploration in Kibana 3 while also allowing for rapid creation of visualizations. This is an ongoing project 
to allow Kibana 3 features to remain compatible with the evolution of Elasticsearch itself.
 
You can find the Kibana 3 community repository at [https://github.com/kibana-community/kibana3](https://github.com/kibana-community/kibana3)

More information about Kibana 3 can be found at [http://www.elasticsearch.org/overview/kibana/](http://www.elasticsearch.org/overview/kibana/)

## Overview

Kibana is an open source (Apache Licensed), browser based analytics and search interface to Logstash
and other timestamped data sets stored in ElasticSearch. With those in place Kibana is a snap to
setup and start using (seriously). Kibana strives to be easy to get started with, while also being
flexible and powerful

### Requirements
* Elasticsearch 1.1 or above
* A modern web browser. The latest version of Chrome, Safari and Firefox have all been tested to
work. IE9 and greater should work. IE8 does not.
* A webserver. No extensions are required, as long as it can serve plain html it will work
* A browser reachable Elasticsearch server. Port 9200 must be open, or a proxy configured to allow
access to it.

### Docs

Documentation, panel options and tutorials can be found at 
[http://www.elasticsearch.org/guide/en/kibana/current/](http://www.elasticsearch.org/guide/en/kibana/current/)

### Installation

1. Download and extract [http://download.elasticsearch.org/kibana/kibana/kibana-latest.zip](http://download.elasticsearch.org/kibana/kibana/kibana-latest.zip) to your webserver.
2. Edit config.js in your deployed directory to point to your elasticsearch server. This should __not be
http://localhost:9200__, but rather the fully qualified domain name of your elasticsearch server.
The url entered here _must be reachable_ by your browser.
3. Point your browser at your installation. If you're using Logstash with the default indexing
configuration the included Kibana logstash interface should work nicely.

### FAQ
__Q__: Why doesnt it work? I have http://localhost:9200 in my config.js, my webserver and elasticsearch
server are on the same machine  
__A__: Kibana 3 does not work like previous versions of Kibana. To ease deployment, the server side
component has been eliminated. Thus __the browser connects directly to Elasticsearch__. The default
config.js setup works for the webserver+Elasticsearch on the same machine scenario. Do not set it
to http://localhost:9200 unless your browser and elasticsearch are on the same machine

__Q__: How do I secure this? I don't want to leave 9200 open.  
__A__: A simple nginx virtual host and proxy configuration can be found in the sample/nginx.conf

__Q__: How to run the grunt build process.  
__A__: Steps to follow 
        a)Install node & npm 
        b)npm install -g grunt-cli
        c)npm install in kibana folder
        d)grunt build
        
        Useful links:
        	https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager
        	https://npmjs.org/doc/install.html
        	http://www.ghosthorses.co.uk/production-diary/installing-grunt-on-os-x-and-windows-7/

### Support

If you have questions or comments the best place to reach me is #logstash or #elasticsearch on irc.freenode.net

### Contributing

Please see [CONTRIBUTING.md](https://github.com/elasticsearch/kibana/blob/master/CONTRIBUTING.md). 
If you have a bugfix or new feature that you would like to contribute to Kibana, **please find or open an issue 
about it first.** 
