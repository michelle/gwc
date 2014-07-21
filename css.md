What is abstraction?
- things that separate implementation from details.
What is a CSS selector?



# CSS as abstract art.
[mondrian blank]()


You guys had a class in CSS and are now learning mobile, right?

A little bit about me, first:
## Intro to me.

Hi, I’m Michelle.

I’m an engineer on the product team here at Stripe.

[stripe slide]()


## Neopets

But I wasn’t always an engineer. Now, how many of you have heard of Neopets?
[neopets.com]()

For those who haven’t, it was this website that was super popular when I was in fourth grade. You would have these virtual pets, and you could play games and accumulate Neopoints to buy them pretty paint jobs and level them up and read them books and stuff. And you could also collect avatars and trophies and make cool online friends. And I was pretty into Neopets. all the way up until 9th grade.
[montage of things you can do on neopets e.g. feeding, paintbrushes, books, avatars, trophies, forums.]()

Of course, feeding my pets and having them virtually love me was not enough. I wanted something to show for all my hard work. I wanted trophies. I wanted to look cool to other users.


At one point I was so motivated to win a userlookup of the week award (and i eventually did). Of course, this all involved knowledge of CSS, so you could make pretty stylesheets.
[userlookup of the week]()


I had no idea what CSS is, so I learned one cool trick:

[view source button on windows]()
View source!

I would copy people’s cSS and change the colors and numbers until I had what I want. I didn’t know or care what it was I was writing, and at that time I really didn’t even know what the hell to Google, what position: absolute or position: relative mean (how many of you know?) what the difference between a padding and a margin and an invisible border was. When somethign wouldn’t work, I’d try to move the CSS rules around until it did. Or just give up after a few hours on getting a particular image in the right place because I genuinely thought neoepts was being mean and buggy.

[shitty css]()

And that was fine, because I copy and pasted things and it worked and I got my shiny trophy.

[userlookup of the week]()

If we just consider abstraction as a separation of the implementation details (actually writing and understanding CSS selectors and rules) from the abstract concept (seeing pretty things on my screen), then my source code copy and pasting can still be considered abstraction, however crude and unsatisfying.

[view source, c & p]()
[table flip]()

Here’s an example. What would this return?

The answer is that I didn’t even bother thinking this one through, since CSS shouldn’t be like this!

CSS should be as pretty and maintainable and style guided as every other programming language.


Flexible, readable, maintainable.

There’s a lot of power we’re given in CSS, and it’s oft abused.

## College

The summer before my sophomore year of college, long after I’d put my Neopets days behind me, I started getting into CS. Probably somewhat because I subconsciously remembered my preteen love for making pretty pictures appear on my screen magically and to win trophies. Except this time the trophy was for real. At Berkeley, hackathons were super popular, and folks who could build cool apps were the cooooolest. So I wanted to make something too.

This time I stopped and tried to understand the CSS I was writing. There was no abstraction here. I literally wrote out every single rule. Well, except when I needed to learn how to make a triangle with CSS. I googled that and copied and pasted it.
[cool kids]()
[google triangles]()

And it worked out pretty well, really.
[final product]()

It was a small few-hundred line victory, and I didn’t consider CSS seriously again for another 2 years. 


Right before I graduated, I interned at a company called Quizlet.

[quizlet]()

Now, quizlet builds online learning tools for folks who want to learn. Like flash cards, memory games, etcetc. And so of course they’re a pretty major web application with lots and lots of code.

One of my interview questions involved writing a sorting fn

But the important thing is, I didn’t really take it into my heart, and continued hacking away at CSS.

If any of you are interested, I’d be happy to talk about that problem after the talk.


[!important]()


## Pause here for a sec.

I got the job, somehow, and this became my first foray into actual real life production CSS. How many of you have ever heard of a CSS preprocessor?


TODO: explain preprocessor.

At Quizlet we used a CSS preprocessor called Stylus. It’s this magical layer of abstraction that allows you to write CSS intuitively. You can have things inherit, have variables, etc, etc.

And so basically you can think about css as little as possible. Just write CSS as you would write code. Reuse variables, etc.

Power, fix a bug by adding one line.

## But?

But of course, this means that when things weren’t explicitly planned out (as folks didn’t really see css as real programming), 

And of course, we’d end up hacking things in. We want this ne button to be red in this one view once? then just !important it!

And the multiple levels of nesting made things simpler to write, but of course we’d end up with stuff like:
.some-page {
  .inner {
    .popup {
      &.specific-popup {
        button {
          &.red {
            /** This red button is unusable anywhere else. */
            color: red !important;
          }

          &:hover {

          }
        }
      }

      span {
        /** And every time we wrap anything in a popup span, styles are magically applied.
      }
    }
  }
}

And you end up with selectors like:
.some-page .inner .popup.specific-popup button.red:hover

When you really could’ve just marked that button down with .red-button or something similar. 

[red-button]()

When someone else needs a red button now, they will sometimes refactor it into something nicer, but as CSS isn’t real coding, other times they’ll default to abstraction method #1: copy and paste.

[selector soup]()

When you then need to style some-other-page, you end up copying and pasting most of the innards of some-page. We used this page-based approach to writing CSS because it was easy to find exactly which CSS file to look into when fixing bugs and adding small things. (I’m on the welcome page? just open welcome.scss!) This makes sense from a convenience perspective, but what you really end up with is really messy CSS.

And we ended up using this style of writing CSS here at Stripe as well.

It’s interesting because you’d never go into a large production Javascript or Ruby codebase and add small hacks without feeling at least a little bad. But the way we treat CSS as an afterthought allows us to do that exact thing with CSS.

Not even a small problem.
facebook had 706 CSS files, they declared the Facebook blue color 261 times
261 declarations of facebook blue.



## Hope

Things can be nicer. CSS can be written as not an afterthought. 

So I want to share with you how we’re currently rebuilding our CSS at Stripe.

[show dashboard]()

We’re writing CSS first, and breaking our new dashboard into smaller UI components that we can style consistently.

We’re starting out by ensuring that good markup is written, classes are consistently named.

Tests, etc.

If you’re curious, I can also talk with you more in depth about the tooling that’s available to help with these sorts of things.

Either way, if you’re starting a new project that requires CSS (and many do, these days), do consider putting thought into how it’s structured.


