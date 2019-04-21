Created Erlang for building fault-tolerant systems.
The last iteration of his [blog]([https://joearms.github.io) was a Quine implemented as a TiddlyWiki.

He passed away on April 20, 2019: https://news.ycombinator.com/item?id=19706514

Interesting tidbits of knowledge:

- [First impressions on Elixir](https://elixirforum.com/t/learning-elixir-frst-impressions-plz-dont-kill-me/16424/52)
Joe highlights how C++ and Java got the idea behind OOP confused. It's about getting objects to do things by passing messages to them and not about structuring code into classes and methods.
> OO programming is all about objects. Objects are things that respond to messages (or should be) - to get an object to do something you send it a message - how it does it is totally irrelevant - think of objects as black boxes, to get them to do something you send them a message, they reply by sending a message back.
> 
> How they work is irrelevant - whether the code in the black box is functional or imperative is irrelevant - all that is important is that they do what they are supposed to do.
>
>Unfortunately the first big OO language based on this model (smalltalk) talked about objects and messages but messages in smalltalk were not real messages but disguised synchronous function calls - this mistake was repeated in C++ and Java and the “idea” of OO programming morphed into some weird idea that OO programming had something to do with the organisation of code into classes and methods.

Erlang and Elixir's central thesis:
> Erlang and Elixir support the lightweight creation of millions of isolated processes - everything works by messaging between processes - the design of a system involves observing the concurrency you want in your application and mapping it onto processes.
> A web server in Elixir for 10,000 users is not “one web server with 10,000 users” (like Apache or Jigsaw or all the rest) it’s “10,000 web servers with one user each” - this is a radicle departure from conventional practise.

Erlang is OOP in the true [Alan Kay](http://wiki.c2.com/?AlanKayOnMessaging) sense:

> For a long time I’ve said “Erlang is the only true OO language” (now I guess I can add Elixir).
> 
> The basis of OO programs are:
> 
>  - isolation between objects (we do this)
>  - late binding (we decide what to do when a message arrives at a process)
>  - polymorphism (all objects can respond to the same message, for example, you could think of sending a "print-yourself" message to any object and it would know how to do it)
>  Of lesser importance is
> 
> - division into classes and methods
> - syntax
> - the programming model (ie functional or imperative) 

On why Fault-Tolerance is easy with Erlang:

> What Erlang (and Elixir) added to programming was the idea of the link. This was Mike Williams idea - this extends error handling over process boundaries and with links and process we have all we need to build supervision trees and so on.
> 
> Supervisors, gen_servers and all that jazz are just simple libraries that hide a bit of detail from the user - they are just built in a rather simple way with links and parallel processes.
> 
> Erlang was not designed as a FP language - but as a tool for building long-lived fault-tolerant systems.
> 
> Central to fault-tolerance is the notion of remote error handling. If an entire machine fails the fault must be corrected on a DIFFERENT machine. It cannot be corrected locally because the local machine is dead.

Any fault-tolerant system will end up looking like Erlang:

> This means that to program for fault-tolerance we need distribution and messaging to be easy to program - so basically any design for fault-tolerance will end up looking like Erlang.
> 
> The whole point of Erlang was to make it easy to program fault-tolerant systems, a side effect is that it’s also easy to program scalable systems.

Advice on how to market Erlang/Elixir:
> The differentiator between Erlang and Elixir and “All the rest” is the concurrency and fault-tolerence mechanisms - it not about Monads and Syntax and whether it’s a pure FPL.
>
> Now would you like to handle 10,000 users in a single thread using callbacks to emulate concurrency or would you like to make 10,000 concurrent processes, each of which is simple and has no callbacks.
>
> Each process waits for a message that it is interested in then performs a computation and sleeps waiting for the next message.
>
> I think a big problem in evangelising Erlang/Elixir is that you have to explain how having large numbers of parallel processes solving you problem helps. Since no other common languages support concurrency in any meaningful way the need for it is not understood.
>
> “But I can do everything in callbacks in a single thread” they’ll say - and they do - and it is painfully difficult - and you ask “what happens if the callback gets into a loop or raises an exception” - if they don’t understand the question you’ll have some explaining to do - if they do understand the question then you can tell them that in a strange far off land where was a was to program concurrency that did not involve callbacks.

> Please don’t sell Elixir as an FPL - it’s not it’s a CPL (Concurrent Programming Language)
> Don’t get into “my FPL is purer than yours” arguments. Don’t even think about talking about Monads. Change the subject.
>
> “What’s a CPL?”
> “You know, the kind of stuff the WhatsApp servers are written in …”

And all this knowledge form a single forum post!
