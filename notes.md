## WILICAPAWHITN

## Disclaimer

Hi! I'm Michelle.

The title of my talk was probably what brought you here, since it's pretty long
and seems relevant to your interests.

However, full disclosure: the basis of this talk is entirely my own experiences
and beliefs.

You probably have a  whole different set of goals and experiences from mine.

So, I'll give you the best advice I have up front before diving into my life:



Now...

How many of you are freshmen and don't have an internship this summer?

How many of you have been to a hackathon before?

How many of you have interned at Google/Facebook/Twitter?


Great, you're already on track to forming preconceptions about jobs and
programming.

Regardless of whether those preconceptions are correct or not, there's one thing
that I'm confident you need to know:

Learning to learn is perhaps the best thing you can do for yourself. And you're probably already doing it.
You can take a PE class to try to
get fit, but until you run a mile yourself, you won't get much out of the class.

[fish]()

It's the give a person a fish v. teaching a person to fish thign you've always heard
, but i don't think most
people take it to heart, because they've never been given a fish and fishing is
not for everyone.

But you've take a PE class, and probably a CS class. And you know whether you cruised through it or
copied a homework or actually tried to make the best of each assignment.

You calibrated your working style to suit the class, optimized for how much
you think the topic will benefit you, and ran a mile when you really needed to.

And that's the best skill you can possibly learn in college--to know when you
want to just be given the fish , and know when to
learn to fish or run the mile, or whatever metaphor you choose to adopt. 


[angler]()

learn to adapt, whether it's the bottom of the ocean, or a new job, or a new
class that you're just taking to graduate.

[title slide]()

# Story of my life 

## Texas

I went to high school in texas, at a pre-pre-med high school called Health
Careers High School.


## Berkeley

I then attended Berkeley, where I switched majors from pre-med to EECS.

Classes I took were very theoretical. I took our one software engineering class but we
used Rails, so I snickered at it. We also learned pair programming, test driven
development, version control, the agile development process, and SAMOSAs
[slide about samosas]()

The class became a bit of a joke because of things like SAMOSAs.

overly heavy concepts for something we consider pretty simple in
college--writing a CRUD app.


And then there were the exciting classes:
  optimize matrix multiply by unrolling loops,
  bicker with my friends about editors and how to do things in the fewest lines
    of code
  and build reliable data transport on top of UDP.
  solve life's great problems (pacman) with machine learning and game theory


[google slide w/ shinies]()
## My first internship was at Google

You may have heard of it.

Here I was on the Google Docs team building copy/paste for Google docs tables.[table slide]()

A whole month and a half of my internship was dedicated to writing a design doc
about how i'd implement pasting some cells from one part of a table to another
part of the same table or a different table.

It ended up being over 20 pages, and i had to rescope my project, not once, but
twice.

which devastated me.[table
flip]()


## Quizlet [quizlet]()

I then worked part-time at Quizlet, back then with only 5 people, in my last semester
of school. Here I worked on a product that was never released, built up all sorts of nasty
feelings about coffeescript and php and felt grossly overpaid because of how little i
felt I was contributing. I would
I work longer hours to make up for that, and had the constant fear that I'd be fired.


## Stripe

This fear carried on to my first few months at Stripe as a new grad. [stripe slide]()

I'm on the product team right now, building out the API at Stripe. Often I feel
like my job description is "code janitor" and what I'm learning most is how to
rescope things and how to create realistic milestones, which turn out to be 1/10
of what I actually feel like I can do.

And to this day I'm still learning how to get better at these things.


## title

Without further ado:
10 things I believed about programming in college.

Hopefully #3 will shock you.


# 9. Most problems should be solved with things I learned in my AI class.

Unfortunately, most problems are not Pacman. 

Usually you want to think buying data sets, or mechanical-turk-like solutions.


# 8. git commit -am "lol"

Writing a good commit message is one of the more important things i've learned
since college.

In college when using version control our commit messages are usually one line.
I blame this on the fact that the most basic git tutorials tell us to use "-am",
and that makes us feel like messages should only be one line.

git rage story.


# 7. I don't want to join a startup or do my own thing because I want to learn at a big company first.


This is something I've heard often from really smart friends when I ask them why they don't
join a smaller startup or do their own startup (and they've mentioned they're
interested before)

I think this idea comes from learning so much as an intern at bigger companies.
When you're an intern at a smaller company, you're often not paid attention to.

However, your experience at a big company as an intern will not be the same as your
experience at a big company as a full time employee.

You know right off the bat because interns get free backpacks and hoodies, and
fulltime employees get a t-shirt.

You already know how to code. The experience that's most important is how to
greenlight a project, how to make design decisions, how to convince other people
of your design decisions, how to disagree productively; and oftentimes a big company
will abstract that all away from you because you're coding to a spec.


# 6. [testing, design docs, pair programming] is silly/a pain.

Testing/design docs/pair programming is silly/a pain


# 5. * is silly/a pain.

This homework is a pain, this spec is a pain, HTML is dumb, the HTTP protocol is
silly.

This is often a legitimate thing to think, especially when * is something that comes from legacy
systems. 

E.g. banks still only accept faxes rather than email.

But it's only a legitimate belief if you don't end that sentence there, and give
a why.




# 4.  Optimization is important, and optimization means less & faster. Storing less data, having less lines of code, unrolling

I remember bickering with my project partners as a freshman about whether a
suffixed ++, a prefixed ++, or
+= 1 was faster in a loop, and it seemed like the most important question in the
world.

But in real life, Style oft trumps Optimization. Is a JSON file more readable for
data than having data in code? Yes. But loading the JSON file in your code will
be slower.

Amended: "Style and readability are often more important than optimization."

* but that's not to say that you should check whether an element is in an 100000
  element array as the check of a while loop, which one of my project partners
  has done, slowing our parser down from 2 seconds to 2 minutes.

# 3. Abstraction is simple. Cars and garages.
TODO

Abstraction is everything I learned in my data structures class. You have a Car
type, and a Garage type. But what if there was more?

Let's try modelling something simpler than say, Facbeook. Stripe account system.

User
login info
Account
charge info/legal info

 But now multiple people want to have access to an account. Say, the support
 team.

Users who have access, but no Account directly tied.

Now internally we've started to shard data by Account ID.

Okay, but now you want your users to have access to multiple accounts

many to many between users and accounts (UserAccountAccess)

Okay, but now an account should be able to have different projects. (michelle
stickers v. michelle donations)

user has many account, account has many users, account has many projects

But now I only want my friend to access one of the projects:




# 2. I'm going to get fired because I'm not as productive as my co-workers.

A lot of really smart new grads that I've talked to have told me that they feel
like they're going to get fired for the year at their jobs.

In most cases you're not. Don't stay until 9p every night because you feel like
you need to catch up. Don't work weekends. It's most important to not burn out and be
really sad. That's the worst thing you can do for yourself.

The people who are more productive than you just know the codebase better. And
it all comes with time and a clear mind. You're working in someone else's code.

And some people argue that they felt more productive as an intern. You're
supposed to, because you're given a smaller, more isolated unit of work. You're
not obligated to refactor or clean up or generally do more janitorial work
that's involved in building inside existing code.

In fact, get used to it now. Try contributing to open source.

Amended: "I'm not as productive as my co-workers, but I'll get there soon with a
reasonable amount of work."


# 1. Projects can be finished.

Hackers@Berkeley always wanted to do a "Finishathon" of sorts, because we
realized that we were never relaly following up on and finishing our hackathon
projects. We genuinely thought this was a good idea.

Mixest. I still pay $5 a month for a droplet for it. I still occasionally have
to perform upgrades and fix breakagess from changes in the last.fm api. Even
though it's old and poorly designed, it's not finished.

Then I started my own open source project. I thoguht that after release, it'd be
done. But when you have users and people contributing, it's never finished. And
it's an amazing feeling.

So I amend my belief to: "Unpopular projects can be finished. You don't want
your project to be finishable."


# 0. The most important thing I learned in school is how to code.

Today, I don't remember more than a quarter of what I learned in school. Linear
algebra? OpenGL?

The most important thing I learned in school was how to learn. I learned how to
Google. I learned how to ask the right questions and read the manual when it's
appropriate. Most importantly I learned to be
responsible for what I believed in [slide](). And I learned that even with a degree,
there's so much more that I've yet to learn.



## Conclusion

You have to assume responsibility for what you believe in. Some people get
lucky, but luck favors the prepared mind. Always be alert.

