# toy_chess_example_spec

This is an example of what a simple spec for a piece of software can look like.  Better specs exist; this is a minimum.

Be clear: if someone gave me this spec, I'd be pretty annoyed.  This is definitely phoning it in tier.  Built On Not Good Technology &trade; .

My goal is to establish more of a watermark "if it's less than this, you done screwed up."



<br/><br/>

## What is inside?

This "specification" (lol) regards a simple chess game SaaS webserver.  The client is an html client the server ships.  An API is provided for
native clients, but none of the native clients are specified in this document.

This SaaS webserver establishes a chess server which can play games either live or over weeks, as well as maintain a player ranking, archives
of past matches, simple chat services also live or protracted, an observer mechanism for big matches, classes, and a client API.

> It is important to notice that this spec does not attempt to define how the work is being done; only what work needs to be handled before
> the job may be considered complete.  It's okay to pre-define implementations if you need to, but that goes in a technical guide, not a 
> specification.  A spec should be as close to an exhaustive checklist as is practical.  So, no choosing languages, or libraries, or 
> standards except when there's a legal driver.  That's for other docs.  Don't cross the streams.

Because the goal is to define the scope of the work, most of the attention that has been paid is towards two topics: 

1. making sure all the things we know about that need to go in are mentioned, and
1. organizing it in groupings that are easy to keep in mind at once



<br/><br/>

# Specification

This system will need:

