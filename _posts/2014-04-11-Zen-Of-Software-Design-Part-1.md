---
layout: default
title: Zen of Software Design - Part 1
---

I call it Zen of Software Design.. instead of [Zen of Python](http://legacy.python.org/dev/peps/pep-0020/) which is presented at the bottom of this blog for reference and below is my interpretations and thoughts on it

Lines 1 to 9 of [Zen of Python](http://legacy.python.org/dev/peps/pep-0020/) is covered in this blog, Lines 10 to 19 will be covered in Part 2.

<br/>
<b><i>Interpretation</i></b>

The way to read "better than" statements in above poem, is to understand that one does not always win over other and both have their place under sun. But the poem advocates one over another when all things are equal and there is a choice to be made. i.e. leaning or favoring one over another.

<br/>
<b><i>Beautiful is better than ugly</i></b>


While it is easy to understand that beautiful is better than ugly, it is very subjective to know what is beautiful and what is ugly. If you look at source code as an art, like a painting, bad code/design will stink ([code-smell](http://en.wikipedia.org/wiki/Code_smell)) and makes you feel uncomfortable instinctively. I don't think there is standard rules by which you can differentiate beautiful from ugly design similar to good/bad paintings. I guess it comes from looking at different codebase and experience.

<br/>
<b><i>Explicit is better than implicit.</i></b>

It should be obvious to figure-out what's happening while looking at the code, for someone not familiar with the codebase. Usually implicit is looks like magic which happens without any clue how it is working. There are two kind of implicits we face in day-to-day work.

*	Well known implicits :- Things which are well documented and have become standard way of doing things. These implicits usually go across project team boundaries. Example : SpringMVC annotations, Rails conventions
*	Project implicits :- Things which project teams builds within the project which is not something a new developer would be acquainted with in other projects. 

<br>
I have seen developers going overboard with Annotations or conventions in projects, where it is difficult to figure-out how things work. A rule of thumb I use to figure out if we have gone overboard is by asking myself the question "Can I explain, to a new developer joining team, all the implicit things happening in the project within 1 hour session ?".

<br/>
<b><i>Simple is better than complex.</i></b>

Again this seems very obvious but still elusive. No one wants to create a complex system but creating simple design/software is a complex job. 

Few things which help me be on track of simplicity while looking at the code

*	How many execution flows/paths exists ?.

	if there are few execution paths than its easy to keep them in mind and figure out a specific scenario falls in which one of the paths.
*	How easy is it to figure-out a given scenario falls under which execution path ?. 

	It should be easy to figure that out, if the application is well designed and simple to remember.
*	How many exceptions to the conventional flows exist ?. 
	
	In every application there are few exceptional scenarios which don't fall under normal execution paths and need exceptional flows for them. These should be minimal and explicitly identified.
*	How easy it is to explain high level design to a new developer ?. 
	
	I found this rule of thumb to be very helpful. It becomes obvious when you explain (or imagining to explain) how application works to a new developer. If you can explain it without flinching several times when the developer says "ah in scenario x app will do this" and you go hmmm its mostly correct but there are some other issues etc.

<br/>
<b><i>Complex is better than complicated.</i></b>

Design can be complex because domain is complex but sometime domain is simple but software is designed or implemented in complicated way. Design should be as-complex or as-simple as the requirement needs, not more and not less. 

The questions I ask to figure out if design is complicated is

*	What part of requirement is causing the design to be complex?
*	Is the technology choice introducing additional complexity?
*	Is there any negotiable requirement which can be removed to make it more simpler?
*	Are we designing the system for future proofing which might not be required?

<br/>
<b><i>Flat is better than nested.</i></b>

When we look at code there are few obvious cases where this is true. For example it is better to have several flat functions than having one long nested function. For example :- Using Strategy Design Pattern or Command Design pattern to separate code into independent units. Where it is not very obvious and still useful to think is

*	How many layers are we introducing in software architecture ?
*	How many jumps do we need to make to get to the final value (may be cached value or database lookup) ?
*	Is the path of execution intermingled and can not be modified independently?

<br/>
<b><i>Sparse is better than dense.</i></b>
<b><i>Readability counts.</i></b>

Few times I have questioned myself if single responsibility principle, unit testing, dependency injection and design patterns are good. The reason for this doubt is that after following single responsibility principle, unit testing with dependency injection and following design pattern, a small codebase grows to considerable code size.  I call this new increased codebase sparse compared with earlier code which was dense. 

The advantages of sparse code base compared to dense code is

*	It is easier to understand and modify. 
*	It is easier to extend to add more scenarios.
*	It is easier to isolate an issue and fix it.

<br/>
<b><i>Special cases aren't special enough to break the rules.</i></b>
<b><i>Although practicality beats purity.</i></b>

Good software Architecture/Design usually settle with a set of rules like

*	Execution flows/paths 
*	Logical Architecture Layers and how each layer communicated with another layer.
*	Inter-process communication protocols


Every now-and-then a new requirement which breaks design rules under which application has operating comes in. Usual tendency is to treat this as special case which works differently to existing architecture. 

While it might be the right approach in few cases, we should 

*	strive to see if this special case can be modelled as one of the existing flows
*	check if existing rules can be extended to incorporate the new requirement as first class design decision instead of treating it as special case which breaks the rules.
*	check if we have been adding a lot of special cases and do a course correction if required.

On the other hand if they truly are special cases and trying to extend or modeling it has one of the existing flows make design complicated, we should not hesitate to incorporate the new requirement as special case as a pragmatic/practical architect or developer should do.

Lines 10 to 19 will be covered in Part 2 of this blog


	$ python

	>>> import this
	The Zen of Python, by Tim Peters

 	1 Beautiful is better than ugly.
 	2 Explicit is better than implicit.
 	3 Simple is better than complex.
 	4 Complex is better than complicated.
 	5 Flat is better than nested.
 	6 Sparse is better than dense.
 	7 Readability counts.
 	8 Special cases aren't special enough to break the rules.
 	9 Although practicality beats purity.
	10 Errors should never pass silently.
	11 Unless explicitly silenced.
	12 In the face of ambiguity, refuse the temptation to guess.
	13 There should be one-- and preferably only one --obvious way to do it.
	14 Although that way may not be obvious at first unless you're Dutch.
	15 Now is better than never.
	16 Although never is often better than *right* now.
	17 If the implementation is hard to explain, it's a bad idea.
	18 If the implementation is easy to explain, it may be a good idea.
	19 Namespaces are one honking great idea -- let's do more of those! 
