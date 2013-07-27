# pillowtalk

Asynchronous RESTful API
[Austin Clojure Meetup]

Pillow Talk is a Bastion REST App Server. To that end, it excels at asynchronously servicing a large number of secure requests from both single page web apps and mobile apps. It coordinates the bastion business logic and interactions with other REST services. You can sleep easy using Pillow Talk to coordinate your REST App's requests.


## Requirements

1) Latest JVM.
2) As few outside the project Clojure libraries as possible. (Yes, this means more work. It also means we can articulate some important security and performance promises. A REST stack is a highly specialized form of the HTTP stack. It is a lot less code than you might think. GET, PUT and DELETE may be all we need. [We may need POST for the web app folks.] If you wish, we can take existing libraries and cut them to the minimum. But we will probably have to do a security pass on each line of code. Hence, we will be wanting the paths to be a simple as possible. Options are a secure server's nightmare. The more security issues we can pass off to Oracle/IBM the better. Stay as close to the bare byte codes as possible.)

More to come...

I'm sure you'll be pushing back on the vision statement. Lets refine it together.



## Prerequisites

* You will need [Leiningen][1] 1.7.0 or above installed.
* [core.async](http://clojure.com/blog/2013/06/28/clojure-core-async-channels.html)
* [core.async examples](https://github.com/clojure/core.async/tree/master/examples)
* [CSP](https://github.com/clojure/core.async/tree/master/examples)

[1]: https://github.com/technomancy/leiningen

## Experiments

* Playing around with [async in the repl](some-async.md)

## Reading material

* Check out [Aleph](https://github.com/ztellman/aleph/wiki) and 
  [Lamina](https://github.com/ztellman/lamina/wiki/Connections)

## Running

To start a web server for the application, run:

    lein ring server

## License

Copyright © 2013 FIXME
