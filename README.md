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
            1. Everything in site meta below
        1. User stuff
            1. My public profile (Public nickname, photo, on/off show your rank, etc)
            1. My private profile (Do I want to be told about tourneys?  Do I block this person? etc)
            1. Preferences (language, timezone, etc)
        1. Star user stuff
            1. These are not staff, but recognized users who help org the community
            1. They get abusive comment removal rights, censure rights, etc
        1. Admin stuff
            1. CRUD, event fab, ban, pass reset, etc
        1. Owner stuff
            1. Promote/demote user
            1. Every nuclear button
1. Ability to play games
    1. Knows the rules to at least basic chess
        1. Can refuse illegal moves
        1. Knows when a game is over
        1. Does it need alternates like FRC or whatever?
    1. Has a UI for:
        1. New games
        1. Making moves
            1. Reversing moves
            1. Looking at move history
        1. Concede
        1. Saving and restoring games
        1. Viewing historic games
            1. Yours
            1. Tournaments
            1. Famous games
    1. PbEM support?
        1. Specify Live
        1. Over long time periods
        1. Allow time limit clock 
    1. Can export to standard chess notations like FEN+
    1. Can play multiple concurrent games
    1. Clocks
        1. Game clock
        1. Move clock
        1. Revert clock
    1. Rankings
        1. Exposition games
        1. Ladder games
            1. How does SLO get measured
            1. External lockstep with FISA, etc
        1. Ranked games
            1. How does SLO get measured
        1. Tournament games
            1. This would be explored in a real spec but I don't know chess well enough
        1. Title games
            1. This would be explored in a real spec but I don't know chess well enough
        1. Team games
            1. This would be explored in a real spec but I don't know chess well enough
1. Has a teaching mode
    1. Lockdown UI that forces specific moves
        1. Also needs explanatory dialog boxes
        1. Backup is a special case of undo
    1. Tutorials to get through the basic game
        1. Each piece in moves
        1. Pawn promotion
            1. Holy shit is that two queens?
        1. Castling
        1. En passant
        1. Deadlock draw
        1. 50-move rule
        1. Three-repeats rule
    1. Endgame puzzles
    1. Opening game puzzles
    1. Tactical weighting
    1. Classical studies
1. Web frontend
    1. Focus on speed (ideally no lag, no waiting on responses)
    1. User needs
        1. Ready for very large screens, average screens, very small (eg phone) screens
        1. Ready for mouse interaction, keyboard interaction, touch interaction
        1. Ready for users with major 7 types of colorblindness
        1. Ready for blind users (wa-aria or some competitor)
        1. Ability to specify pronouns; good faith to implement those in the UI (this won't be easy)
    1. No loads to do things (AJAX or XML islands or websockets or whatever instead)
    1. Ready for computers
        1. Mouse controls
        1. Keyboard controls
        1. Large screen
        1. Small screen
    1. Ready for phones
        1. Touch controls
    1. Ready for tablets
    1. Ready for consoles
        1. D-Pad controller controls
    1. Ready for special-needs control rigs
1. Site meta
    1. Landing page
    1. Intro page
    1. Rules page
    1. Login hotpath
    1. Game world status
        1. Public ladder
        1. Upcoming / current tournaments
        1. Events
    1. Outreach pages
        1. For Schools
        1. For Organizations
        1. For Governments
    1. Pricing
    1. Legal, ToS, disclaimers, COPA/COPPA, other site bs
        1. Ask a suit to sign off
1. Internationalization
    1. Internationalization is a ***very big deal*** for this project and must be taken very seriously
        1. Bulk populations are English speaking, Russian, French, Japanese, German, Portuguese, Polish, Korean
        1. Good god what a complex technical spread for linguistics, though
        1. Getting sir/ma'am right is a good idea here; these people think they're royalty
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
        
