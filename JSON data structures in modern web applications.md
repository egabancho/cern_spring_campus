#JSON data structures in modern web applications

##Overview

Web and mobile applications are growing in todays digital world. Ten years ago XML was the primary data interchange format but it’s no a secret that in the last few years JSON has become more and more popular among web and mobile developers. This talk will introduce JSON in a basic way comparing it with XML and will show some use cases where JSON is commonly use in todays software development.

##Introduction
JSON is a data interchange format it is base on _Javascript_ object. Actually its name comes from _JavaScript Object Notation_.
JSON is made out key,value pairs. Where the key is a quoted string and the value could be a `string`, an `integer`, `true`, `false`, `null`, an `array` [ordered] or other `object`.

An object is an unordered set of name/value pairs.
![image](http://json.org/object.gif)

An array is an ordered collection of values.
![image](http://json.org/array.gif)

![image](http://json.org/value.gif)

It looks like this:

```    
{
  "menu": {
    "id": "file",
    "value": "File",
    "popup": {
      "menuitem": [
        {"value": "New", "onclick": "CreateNewDoc()"},
        {"value": "Open", "onclick": "OpenDoc()"},
        {"value": "Close", "onclick": "CloseDoc()"}
      ]
    }
   }
}
```	
More information about JSON and the standard it self could e found in <http://json.org>

##XML vs JSON
For a while, XML was the only choice for open data sharing. There were no other open formats available and XML was meant to be the do-everything solution to data sharing problems.

Now that other options have become available, XML can be overkill in a lot of ways. Today, we are often faced with the choice between JSON and XML when creating data files. If you’re learning to be a web developer, you should learn about both.

###Simplicity, Openness, & Interoperability
In terms of simplicity, openness, and interoperability, JSON and XML are tied. Sure, you’ll find people on both sides of each of these issues arguing for their favourite. However, when you strip away their opinions and dig down to the facts, there isn’t much difference between JSON and XML in terms of simplicity, openness, and interoperability.

###Self-Describing Data & Internationalization
Another common trait that JSON and XML share is the implementation of self-describing data and internationalization. Both of these standards use Unicode standards and they both create data in a way the allows generic tools to manipulate the data. This makes these formats very easy to distribute to a wide range of users.

###Extensibility
With JSON, you are limited to only storing classical data like text and numbers. However, XML allows you to store any data type you can come up with. The ability to extend the attributes of the data stored in XML files is what allows it to be more flexible than JSON. However, it also makes it more difficult to read. This makes XML more extensible, but that may not be a good thing. This depends on the type of information you are trying to transfer. Documents require extensibility to manage images, charts, graphs, and other elements of formatting. However, classical data does not require this extensibility and can benefit from the simplicity of JSON.

###Human Readable
Both XML and JSON files are said to be human readable. At least, they are understandable to programmers that work with these file formats. However, JSON files are more restrictive and therefore slightly more readable. This is because the number of data formats supported by JSON if much smaller than with XML. Additionally, the structure of the data is more standardised with JSON files due to the fact that there are fewer options when compared with XML formatting.

###Complete Integration Of All Formats
With XML it is possible to attach any file of any format. On the other hand, JSON only supports traditional data formats. This means it is possible to include photos, audio, video, and other files within an XML file. While this may seem like a good thing at first, it can also be dangerous. That’s because you could also include an executable file which could have dangerous consequences to security. The simplicity of the data structures that JSON supports makes this exploit impossible using this format.

###Sharing Traditional Data
JSON is the best tool for sharing data. This is because the data is stored in arrays and records while XML stores data in trees. Both have their advantages, but data transfers are much easier when the data is stored in a structure that is familiar to object-oriented languages. This makes it very easy to import data from a JSON file into Perl, Ruby, Javascript, Python, and many other languages.
In order to do the same thing with XML, you would need to first transform the data before it can be imported. For this reason, JSON is a superior file format for web APIs.

###Sharing Documents
When you want to share documents, XML is the right tool for the job. This is because it allows you to include data types like images, charts, and graphs. Additionally, XML offers options for transferring the structure, or format, of the data along with the actual data. JSON only offers options for transferring data without formatting, and only using traditional data formats. This makes XML the superior format for documents.

###Why use JSON?
- It is very easy to read and write
- It is also fast and compact (although we can argue a lot about this point)
- Ideal for data that could be represented as [ordered] lists or key, value pairs. i.e. `arrays`, `hash tables`, etc.
- Maps perfectly topmost programming languages with `arrays` and `hash tables`

Real-life differences:

```
<record>
    <datafield tag="041" ind1=" " ind2=" ">
      <subfield code="a">eng</subfield>
    </datafield>
    <datafield tag="080" ind1=" " ind2=" ">
      <subfield code="a">519.2</subfield>
    </datafield>
    <datafield tag="080" ind1=" " ind2=" ">
      <subfield code="a">518.5:519.2</subfield>
    </datafield>
    <datafield tag="100" ind1=" " ind2=" ">
      <subfield code="a">Burford, Roger L</subfield>
      <subfield code="u">Indiana University</subfield>
    </datafield>
    <datafield tag="245" ind1=" " ind2=" ">
      <subfield code="a">Statistics</subfield>
      <subfield code="b">a computer approach</subfield>
    </datafield>
    <datafield tag="260" ind1=" " ind2=" ">
      <subfield code="a">Columbus, OH</subfield>
      <subfield code="b">Merrill</subfield>
      <subfield code="c">1968</subfield>
    </datafield>
    <datafield tag="300" ind1=" " ind2=" ">
      <subfield code="a">814 p</subfield>
    </datafield>
    <datafield tag="909" ind1="C" ind2="0">
      <subfield code="y">1968</subfield>
    </datafield>
    <datafield tag="909" ind1="C" ind2="0">
      <subfield code="b">21</subfield>
    </datafield>
    <datafield tag="909" ind1="C" ind2="1">
      <subfield code="c">1990-01-27</subfield>
      <subfield code="l">00</subfield>
      <subfield code="m">2002-04-12</subfield>
      <subfield code="o">BATCH</subfield>
    </datafield>
    <datafield tag="909" ind1="C" ind2="S">
      <subfield code="s">m</subfield>
      <subfield code="w">198606</subfield>
    </datafield>
    <datafield tag="980" ind1=" " ind2=" ">
      <subfield code="a">BOOK</subfield>
    </datafield>
  </record>
```	  
Same information in JSON:

```
{u'authors': [
	{u'affiliation': u'Indiana University',
     u'first_name': u'Roger L',
     u'full_name': u'Burford, Roger L',
     u'last_name': u'Burford'},],
 u'cited_by_count': None,
 u'collections': [{u'primary': u'BOOK'}],
 u'creation_date': u'2014-04-02T18:13:58.206004',
 u'files': [],
 u'imprint': {
 	u'date': u'1968',
    u'place': u'Columbus, OH',
    u'publisher_name': u'Merrill'},
 u'language': u'eng',
 u'modification_date': u'2014-04-02T18:13:58.206936',
 u'newer_version': [],
 u'number_of_authors': 1,
 u'number_of_comments': None,
 u'number_of_reviews': None,
 u'physical_description': {u'pagination': u'814 p'},
 u'recid': 1,
 u'title': {
 	u'subtitle': u'a computer approach',
 	u'title': u'Statistics'},
 u'udc': [u'519.2', u'518.5:519.2'],
 u'version_history': []}
``` 
##What can I use JSON for?

JSON could be used for a wide variety of purposes, we will cover a few of them but for sure there are more.

###Configuration Files
So far all configuration files are usually INIT files, but JSON syntax allow richer configuration files.
Using JSON allow the programer to organise the config file easily and oblige the user/client to user this organised way.

One strong competitor to JSON could be [YAML](www.yaml.org/).

There are already some stabilised applications which are using JSON as format for their configuration files, like for example [Transmission](http://www.transmissionbt.com/)

We could think about this INIT file:

```
DATABASE_HOST=localhost
DATABASE_PORT=3996
DATABASE_USER=db
DATABASE_PASSWORD=myAwesomePass
```	

And the JSON way of representing the same information:

```
{
  'DataBase':{
   	'host': 'localhost',
   	'port': '3996',
   	'user': 'db',
   	'password': 'xxxxx'
  }
}
```

###APIs
Believed or not only 20% (approximately) of todays internet comes from humans interacting directly with a computer. The remaining 80% of the traffic is happening behind the scene, typically via API.

Because of this important fact building a good API can't be ignored when developing a web application (maybe any kind of application ...).

This has created a scenario in which organisations like Twitter, Facebook, LinkedIn, and millions of others essentially offer information-based services in exchange for data and increasingly have an interest in opening up a wide variety of information to third parties. This data usually never sees the light of day, that's the 80% of the online traffic.

XML is still a major player in the world of APIs, but that JSON’s star is rising fast. Twitter’s API went JSON-only almost two years ago.

APIs have become first class citizen of the web. On top of that, *REST* is replacing SOAP as a data transfer protocol. 

####REST APIs
REST stands for Representational State Transfer, and it was proposed in a [doctorate dissertation](http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm) (the hole [thesis](http://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)). It uses the four HTTP methods `GET`, `POST`, `PUT` and `DELETE` to execute different operations. This in contrast to SOAP for example, which creates new arbitrary commands (verbs) like `getAccounts()` or `applyDiscount()`.

A REST API is a set of operations that can be invoked by means of any the four verbs, using the actual URI as parameters for your operations.

As an example we can take Twitter's API (as mentioned above).
In order to access your own data, you must create an application, and generate your own access token, more informations on the [Twitter API Getting Started](https://dev.twitter.com/start).

Before starting we need two python packages:

```
pip install requests requests_oauthlib
```

This is the code that we will be using:

```
# -*- encoding: utf-8 -*-
from __future__ import unicode_literals
import requests
from requests_oauthlib import OAuth1
from urlparse import parse_qs

REQUEST_TOKEN_URL = "https://api.twitter.com/oauth/request_token"
AUTHORIZE_URL = "https://api.twitter.com/oauth/authorize?oauth_token="
ACCESS_TOKEN_URL = "https://api.twitter.com/oauth/access_token"

CONSUMER_KEY = "YOUR_CONSUMER_KEY"
CONSUMER_SECRET = "YOUR CONSUMER_SECRET"

OAUTH_TOKEN = ""
OAUTH_TOKEN_SECRET = ""


def setup_oauth():
    """Authorize your app via identifier."""
    # Request token
    oauth = OAuth1(CONSUMER_KEY, client_secret=CONSUMER_SECRET)
    r = requests.post(url=REQUEST_TOKEN_URL, auth=oauth)
    credentials = parse_qs(r.content)

    resource_owner_key = credentials.get('oauth_token')[0]
    resource_owner_secret = credentials.get('oauth_token_secret')[0]

    # Authorize
    authorize_url = AUTHORIZE_URL + resource_owner_key
    print 'Please go here and authorize: ' + authorize_url

    verifier = raw_input('Please input the verifier: ')
    oauth = OAuth1(CONSUMER_KEY,
                   client_secret=CONSUMER_SECRET,
                   resource_owner_key=resource_owner_key,
                   resource_owner_secret=resource_owner_secret,
                   verifier=verifier)

    # Finally, Obtain the Access Token
    r = requests.post(url=ACCESS_TOKEN_URL, auth=oauth)
    credentials = parse_qs(r.content)
    token = credentials.get('oauth_token')[0]
    secret = credentials.get('oauth_token_secret')[0]

    return token, secret


def get_oauth():
    oauth = OAuth1(CONSUMER_KEY,
                client_secret=CONSUMER_SECRET,
                resource_owner_key=OAUTH_TOKEN,
                resource_owner_secret=OAUTH_TOKEN_SECRET)
    return oauth

if __name__ == "__main__":
    if not OAUTH_TOKEN:
        token, secret = setup_oauth()
        print "OAUTH_TOKEN: " + token
        print "OAUTH_TOKEN_SECRET: " + secret
        print
    else:
        oauth = get_oauth()
        r = requests.get(url="https://api.twitter.com/1.1/statuses/mentions_timeline.json", auth=oauth)
        print r.json()
```

Go to [https://dev.twitter.com/](https://dev.twitter.com/) and register a new appp, fill everything but leave the Callback URL empty if you want call the API without setting up a web server.

The API will give us an URL to get an identifier, so we don't need callback.

Set your CONSUMER_KEY and CONSUMER_SECRET on the script an run it to generate the OAUTH tokens.

Next time we run it we will get our las mentions.

You can get the official Twitter REST API documentation [here](https://dev.twitter.com/docs/api/1.1).

###Big Data
All the data shared with the APIs from the previous section must be stored somewhere.

The rise of JSON as a key player in database technologies is another bad sign for XML. As it stands, Big Data does not have a preferred data interchange format per se. But the claim that I’d like to make about Big Data and JSON is a bit more specific. What I’d like to argue is that JSON is emerging as a preferred format in web-centric, so-called “NoSQL” databases. 

Typically this kind of databases are: 

1. Intended to accommodate massive scalability
2. Designed to deal with data that often does not seamlessly conform to a columnar/relational model
3. to be web-oriented at their very core.

The most well-known examples of databases of this sort are [MongoDB](http://www.mongodb.org), [CouchDB](http://couchdb.apache.org), and recently [PostgreSQL](http://www.postgresql.org/).

Coming back to the XML comparation , there are a few databases out there that are XML-based (such as MarkLogic), but there isn’t any movement in this sphere analogous to what we’re seeing involving the rapid adoption of JSON-based storage models.

MongoDB is one of the most commonly use JSON oriented data base, everybody more or less knows how to use it. Because of that, lets take a look at how PostgreSQL deals with JSON using its hybrid approach with document-relational databases which can store JSON documents, and JSON functions which convert array and row data into JSON.
Lets do an easy example using PostgreSQL as data base engine (Assuming you are running OS X and Homebrew with postgreSQL 9.3 installed).

Start the DB daemon, create a new database for testing and start the postgreSQL shell:

```
$ pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start
$createdb css_test
$psql css_test
```

We can get the help by typing `\h`.
Lets put some sample data:

```
css_test=# CREATE TABLE books ( id integer, data json );
CREATE TABLE
css_test=# INSERT INTO books VALUES (1, { "name": "Book the First", "author": { "first_name": "Bob", "last_name": "White" } }');
INSERT 0 1
css_test=# INSERT INTO books VALUES (2, '{ "name": "Book the Second", "author": { "first_name": "Charles", "last_name": "Xavier" } }');
INSERT 0 1
css_test=# INSERT INTO books VALUES (3,'{ "name": "Book the Third", "author": { "first_name": "Jim", "last_name": "Brown" } }');
INSERT 0 1
```

Selecting, you can use the JSON operators to pull values out of JSON columns:

```
css_test=# SELECT id, data->>'name' AS name FROM books;
 id |      name
----+-----------------
  1 | Book the First
  2 | Book the Second
  3 | Book the Third
(3 rows)
```

The -> operator returns the original JSON type (which might be an object), whereas ->> returns text. You can use the -> to return a nested object and thus chain the operators:

```
css_test=# SELECT id, data->'author'->>'first_name' as author_first_name FROM books;
 id | author_first_name
----+-------------------
  1 | Bob
  2 | Charles
  3 | Jim
(3 rows)
```

Filtering, of course, you can also select rows based on a value inside your JSON:

```
css_test=# SELECT * FROM books WHERE data->>'name' = 'Book the First';
 id |                                         data
----+---------------------------------------------------------------------------------------
  1 | { "name": "Book the First", "author": { "first_name": "Bob", "last_name": "White" } }
(1 row)
```

You can also find rows based on the value of a nested JSON object:

```
css_test=# SELECT * FROM books WHERE data->'author'->>'first_name' = 'Charles';
 id |                                            data
----+---------------------------------------------------------------------------------------------
  2 | { "name": "Book the Second", "author": { "first_name": "Charles", "last_name": "Xavier" } }
(1 row)
```
`Ctrl+C` to exit and now we drop the DB and stop the daemon.

```
$dropdb css_test
$ pg_ctl -D /usr/local/var/postgres stop
```

There’s a whole lot of other JSON operators and functions I didn’t cover here, for example to work with JSON arrays too. I recommend you check out the [official documentation](http://www.postgresql.org/docs/9.3/static/functions-json.html) to see what other cool stuff is possible.

####Indexing Big Data
This data, once is stored, needs to be indexed to allow the users/clients make fast queries to it.
Today we have several option to do this task, one of them is [ElasticSearch](www.elasticsearch.org) which is base on [Lucene](https://lucene.apache.org) and, of course, it uses JSON as output data for any query result.

Lets see how it works (Assuming you are running OS X and Homebrew with ES installed).
To work with ES in _developer mode_ there is one plugin for Google Chrome that I recommend, [Sense](https://chrome.google.com/webstore/detail/doinijnbnggojdlcjifpdckfokbbfpbo) Sense provides a simple user interface specifically for using ElasticSearch's REST API. It also has a number of convenient features such as autocomplete for ElasticSearch's query syntax and copying and pasting requests in curl format, making it easy to run examples from the documentation.

First start the server:"

```
elasticsearch --config=/usr/local/opt/elasticsearch/config/elasticsearch.yml
```

Now lets put some data on it, using Sense interface is very simple, just type this and execute the query:

```
PUT /movies/movie/1
{
    "title": "The Godfather",
    "director": "Francis Ford Coppola",
    "year": 1972
}
```

The response object contains information about the indexing operation, such as whether it was successful ("ok") and the documents ID which can be of interest if we don't specify that ourselves.

```
{
   "_index": "movies",
   "_type": "movie",
   "_id": "1",
   "_version": 1,
   "created": true
}
```

Now that we've got a movie in our index let's look at how we can update it, adding a list of genres to it. In order to do that we simply index it again using the same ID. In other words, we make the exact same indexing request as as before but with an extended JSON object containing genres.

```
PUT /movies/movie/1
{
    "title": "The Godfather",
    "director": "Francis Ford Coppola",
    "year": 1972,
    "genres": ["Crime", "Drama"]
}
```

And that's indexing JSON objects with ES (there is more behind the scene but ...).

Accessing by ID and deleting elements is very simple:

```
GET /movies/movie/1

DELETE /movies/movie/1
```

So lets move to searching, before we need to put a few more movies so we can play a bit:

```
PUT /movies/movie/1
{
    "title": "The Godfather",
    "director": "Francis Ford Coppola",
    "year": 1972,
    "genres": ["Crime", "Drama"]
}

PUT /movies/movie/2
{
    "title": "Lawrence of Arabia",
    "director": "David Lean",
    "year": 1962,
    "genres": ["Adventure", "Biography", "Drama"]
}

PUT /movies/movie/3
{
    "title": "To Kill a Mockingbird",
    "director": "Robert Mulligan",
    "year": 1962,
    "genres": ["Crime", "Drama", "Mystery"]
}

PUT /movies/movie/4
{
    "title": "Apocalypse Now",
    "director": "Francis Ford Coppola",
    "year": 1979,
    "genres": ["Drama", "War"]
}

PUT /movies/movie/5
{
    "title": "Kill Bill: Vol. 1",
    "director": "Quentin Tarantino",
    "year": 2003,
    "genres": ["Action", "Crime", "Thriller"]
}

PUT /movies/movie/6
{
    "title": "The Assassination of Jesse James by the Coward Robert Ford",
    "director": "Andrew Dominik",
    "year": 2007,
    "genres": ["Biography", "Crime", "Drama"]
}
```

The request body should be a JSON object which, among other things, can contain a property named "query" in which we can use [ElasticSearch's query DSL](http://www.elasticsearch.org/guide/reference/query-dsl/).

This is a basic free text query:

```
POST /_search
{
    "query": {
        "query_string": {
            "query": "kill"
        }
    }
}
```

And we will get:

```
{
   "took": 9,
   "timed_out": false,
   "_shards": {
      "total": 5,
      "successful": 5,
      "failed": 0
   },
   "hits": {
      "total": 2,
      "max_score": 0.095891505,
      "hits": [
         {
            "_index": "movies",
            "_type": "movie",
            "_id": "3",
            "_score": 0.095891505,
            "_source": {
               "title": "To Kill a Mockingbird",
               "director": "Robert Mulligan",
               "year": 1962,
               "genres": [
                  "Crime",
                  "Drama",
                  "Mystery"
               ]
            }
         },
         {
            "_index": "movies",
            "_type": "movie",
            "_id": "5",
            "_score": 0.095891505,
            "_source": {
               "title": "Kill Bill: Vol. 1",
               "director": "Quentin Tarantino",
               "year": 2003,
               "genres": [
                  "Action",
                  "Crime",
                  "Thriller"
               ]
            }
         }
      ]
   }
}
```

This is just very basic stuff, just to proof that JSON is used for indexing. If you want to learn more about ElasticSearch there are plenty of places to look about [search requests](http://www.elasticsearch.org/guide/reference/api/search/), use [highlighting](http://www.elasticsearch.org/guide/reference/api/search/highlighting/), get [spelling suggestions](http://www.elasticsearch.org/guide/reference/api/search/suggest/) and much more.


###The Internet of Things
The Internet of Things (IoT) is a scenario in which objects, animals or people are provided with unique identifiers and the ability to automatically transfer data over a network without requiring human-to-human or human-to-computer interaction.

A _thing_, in the Internet of Things, can be a person with a heart monitor implant, a farm animal with a biochip transponder, an automobile that has built-in sensors to alert the driver when tire pressure is low -- or any other natural or man-made object that can be assigned an IP address and provided with the ability to transfer data over a network.

Typically all the devices, _things_, involved in the Internet of Things have limited capabilities of both memory and processor. Therefore using a lightweight structure, like JSON, to represent the information that the work with makes sense.

For example, there is a library using [JSON on the Arduino](http://interactive-matter.eu/blog/2010/08/14/ajson-handle-json-with-arduino/) board.

Besides the limited capabilities of all the _things_, JSON can be parsed to JavaScript objects without moving a muscle, this makes it ideal candidate for integration into Web Mashups.

I'm not going to present any example in this section as it is very dificult to pick only one, and good, example.


###Full-stack JavaScript
In addition with everything mentioned before we can't forget that JSON is essentially a JavaScript Object.

JavaScript is the new hotness and that probably won’t change anytime soon. New client-side JavaScript libraries are coming along every single day, JavaScript is already the [lingua franca of the web](http://blog.codinghorror.com/javascript-the-lingua-franca-of-the-web/).

But todays JavaScript is not longer only about client-side web interfaces with mic effects. 
Nowadays we have JavaScript on the server side with [node.js](http://nodejs.org) and we have to admit that it has gone mainstream and the community surrounding it is rabidly productive.

And JavaScript, and therefore JSON, is not only about web development any more. There is a huge market in the mobile world.
Is well known that there are two main mobile OS, Android and iOS, developing native applications for each of then is an option but we might be in a situation where we don't have the resources or the budget to do it.
In this kind of situation using a JavaScript framework and API to develop a mobile app might be the solution. There are some nice solutions out there like [Apache Cordoba](https://cordova.apache.org), which is basically a set of device APIs that allow a mobile app developer to access native device function such as the camera or accelerometer from JavaScript. Combined with a UI framework such as [jQuery Mobile](http://jquerymobile.com‎) or [LimeJS](http://www.limejs.com/), allows a smartphone app to be developed with just HTML, CSS, and JavaScript.

##JSON-LD
One last thing that I want to remark, as I think is a key element of the fact JSON will supersede XML which is [JSON-LD](http://json-ld.org/).
JSON-LD is a lightweight Linked Data format. It is easy for humans to read and write. It is based on our friend JSON  and provides a way to help JSON data interoperate at Web-scale. JSON-LD is an ideal data format for programming environments, REST Web services, and unstructured databases such as CouchDB and MongoDB.

JSON-LD allows to encode RDF graphs in JSON, for this to be possible, the specification defines a number of keywords, all preceded by the "@" token; the most commonly used ones are:
- @context: used to define the keys and possibly values employed inside the JSON document; for example, if JSON is used to describe a person identified by a name, the context could specify that the "name" field has the meaning as stipulated in a standard ontology. The context is itself a JSON object, where the keys are the various elements used inside the main document and the values are identifiers.- @id: used to uniquely identify JSON elements; coming back to the above example, the person could be uniquely identified by a homepage such as http://example.com/JohnDoe/.• @type: used to specify the data type of values (or more generally of RDF nodes); for example, person names have string type.- @value: used to specify the actual data associated with a property in the RDF graph. In the example above, the "name" property could have the value "John Doe".
A JSON-LD document example describing a person could be something like this:
```
{	"@context": {		"name": "http://xmlns.com/foaf/spec/#term_name",
		"Person": "http://xmlns.com/foaf/spec/#term_Person",
		"dc": "http://purl.org/dc/dcmitype/",		"knows": "http://xmlns.com/foaf/spec/#term_knows"	},	"@id": "http://example.com/JohnDoe", "@type": "Person",	"name": {		"@type": "dc:Text",		"@value": "John Doe" },		"knows": [ 			{				"@id": "http://example.com/JaneDoe",				"@type": "Person",				"name": {					"@type": "dc:Text",					"@value": "Jane Doe" }
			}
		]
	}```
You can find more about JSON-LD in its web page [http://json-ld.org/](http://json-ld.org/)
#*That's all folks!*