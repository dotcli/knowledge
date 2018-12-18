# tools
> [\#tool](https://dotcli.github.io/memex/#type-tool)

## Philosophy
> "Our tools make us."

I've yet to develop a concrete philosophy when it comes to choosing or developing software tools. But there are a few guidelines I find helpful to keep in mind.

**Speed.** When a tool becomes part of who we are, their speed is directly tied to our mental performance. If it takes 5 seconds to load, and 4 buttons to save anything, we would feel sluggish, as our flowing thoughts get artificially constrained and slowed down.

**Offline functionality**. Internet speed, and regulation, is often a factor we have limited controls over. Therefore our tools need to be resilient, to work without the internet; else we won't work without the internet.

**Intentionally limiting accessibility**. If I separate the type of tools on my desktop v.s. the ones on mobile phone, then I can make distinguish between my desktop and phone, honing them for different purposes. When I start using them, I would have a singular purpose, and not be distracted. This is especially helpful for work / life balance.

**Plain text storage.** Of all the storage options, plain text is the most human-readable, transportable, and enduring format.

> Related: [Gwern's notes on why his website is built as a static site.](http://www.gwern.net/About#fnref15)

## Task Management

I developed a plain-text system for planning & tracking. It is super readable - being all plain text. Flexible - I can scribble down whatever info or items that don't fit into the "format", because the content _is_ the format.

The system revolves around 3 text files.

`now.md`: Includes everything I'm to do and have done today. Every morning I start with a blank `now.md` file, and every night I end up with a checklist of items I completed and didn't complete, which I'll cut and paste into...

`tracker.md` : A file with a list of dates, and what I did that day, copied from `now.md`. If I missed a day or two of tracking with `now.md`, I would edit `tracker.md` based on my memory.

`upcoming.md` : My planner. It has a list of upcoming dates \(usually 10 ~ 20 from today\), and general description of what I'm going to do on that date. The intention of keeping the upcoming date shorter than 1 month is so I can focus on the near future, though this is flexible. Every date occupies only one line of text, this way I can visually see how busy I will be on a day. When a day goes by, I remove it from the list. If there are events happening on distant dates I don't have in the list yet, I'll put it after the list of dates, as individual notes.

Later on, once there's enough data, I will develop scripts to analyse the tracker, and discover my activity patterns.

