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

1. Identity
    1. Login
        1. Login with email
        1. Login with credential (app, etc)
        1. Login with social (facebook, etc)
        1. Recover login
        1. Logout
    1. Authorization
        1. Non-id user stuff
        1. User stuff
        1. Star user stuff
        1. Admin stuff
        1. Owner stuff
1. Ability to play games
    1. Knows the rules to at least basic chess
        1. Does it need alternates like FRC or whatever?
    1. Has a UI for:
        1. New games
        1. Making moves
        1. Saving and restoring games
    1. PbEM support?
        1. Specify Live
        1. Over long time periods
        1. Allow time limit clock 
1. Web frontend
    1. Focus on speed (ideally no lag, no waiting on responses)
    1. User needs
        1. Ready for very large screens, average screens, very small (eg phone) screens
        1. Ready for mouse interaction, keyboard interaction, touch interaction
        1. Ready for users with major 7 types of colorblindness
        1. Ready for blind users (wa-aria or some competitor)
        1. Ability to specify pronouns; good faith to implement those in the UI (this won't be easy)
1. Internationalization
    1. Internationalization is a very big deal for this project and must be taken very seriously
    1. Criteria
        1. A successful internationalization system is easy for the translator
        1. A successful internationalization system is comparatively low maintenance
        1. A successful internationalization system is easy for the developer
    1. Must handle
        1. Strings with inclusions
        1. Names (John Haugeland vs JOHN Haugeland vs Haugeland JOHN vs J.Haugeland per culture)
            1. The ability to write your name in another language 
            1. Fang's name should be in Chinese for first-Chinese speakers and English where else appropriate; etc
            1. Sort by reader's preference order
        1. Numbers (omg crore)
        1. Ordinals, esp. ranking ordinals (5th vs 3rd)
        1. Gendering of in-game words (boards are male in Russian and female in Turkish)
        1. Punycode
        1. Ability to record your own name for other people to listen to from your profile (this is so nice at work)
        1. Times and dates both with and without time zones; also unix microtime
    1. Must offer
        1. Some or another straightforward mechanism for translators (upload json?  web ui?  proz?  whatever, but, something)
        1. A clear tutorial for translators on getting a flat string, then a formatted string, into place, start to finish
            1. This tutorial must be kept up to date!  Fortunately this seems likely to never change
        1. A zero or near-zero effort mechanism for developers to update a language build (maybe just a CI action or something?)
        
