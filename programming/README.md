# programming

[\#code](https://dotcli.github.io/memex/#tag-code)

## DRY principle

Don't repeat yourself. When you find yourself doing the same thing twice, there's likely something that can be abstracted away.

## SOLID principles

* S - Single responsibility - Classes should be distinct in functionality.
* O - Open/closed - "software entities … should be open for extension, but closed for modification"
* L - Liskov substitution - "objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program"
* I - Interface segregation - "many client-specific interfaces are better than one general-purpose interface"
* D - Dependency inversion - use interface to decouple dependency from high level module to low level module

The full name of this acronym aren't that intuitive. It's more important to understand each principle individually than remembering the acronym.

## Architecture

**Start with the data.** Think about what is needed to represent your content. The same data is transformed into various forms for different parts of the application to consume. Related idea found here: [The Hikikomori's Guide to Javascript](https://robotlolita.me/2013/04/27/the-hikikomoris-guide-to-javascript.html)

**Anthropomorphize your code.** Give them distinctions in functionality. Think about what a class needs to know in order to perform its function.

Example:

When writing a Kinect installation that attaches strands to the kinect skeleton, I would think about what the strand needs to know every frame in order to update their locations. In that case it is what two joints they are between, and how far they are between the joints.

## Commenting etiquette

The first thing to consider when commenting is if a comment is justified. Does the function's / variable's names already explain what it does? What value does the comment add for the future reader? Often, a comment is needed when the code involves complex math that isn't obvious at first glance.

Keep comments in separate lines from the code. usually above the code it's describing. Keep the line length short. If the sentence starts using "and" or ",", break it to another line.

Use flags for quick note and guides for future revisit, but don't overuse them, there are usually better production management tools.

Flags: `TODO, NOTE, HACK, XXX, DEBUG`

