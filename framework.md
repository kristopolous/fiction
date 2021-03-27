# Principles of framework design

Whether you're a contracting firm that wants to lock your client list in by using a technology stack that nobody else knows or you're an 
independent developer who wants to increase the word count of your resume to try and negotiate a higher pay there's nothing quite like 
creating your own framework.

The following text is a set of guiding principles for frameworks. A framework-framework if you will. If you went back and did a double take
on that sentence then good. By the time you're done with this guide you'll be able to not only let useless nonsense flow from your fingertips 
but also be able to convince others that it's industry best practice because nothing pairs better with arrogance than incompetence.

Make easy things hard and hard things nearly impossible

## Slow down development as much as possible
	Introduce 

## Make things as difficult as you can
### The maxim of maximum unreasonability

## Break as many ways to diagnose defects as you can find
### Make sure stack traces are utterly worthless
### Consume all errors and replace them with generic non-specific handlers
### Suppress your languages’ built-in logging capabilities 
### Disable simple diagnostic sanity checks by enforcing onerous linting rules
### Automatically update all dependencies to their latest git commit without warning

## Change core rules and abstractions at least once a month
### Provide zero migrations and no support for previous versions
### Require the users to rewrite their entire codebase to comply to the next version
### Change what is semantically meaningful

## Confuse your users into utter incoherency

The best frameworks reset everyone's knowledge about a topic back to zero. Regardless of how experienced or knowledgeable someone is
with the underlying tools they should have to question everything and effectively be reduced to a totally ignorant confused person.


Here is a helpful sliding scale to see how far you are in your goals of confusing all users:

Mild criticisms
Profanity
Screaming
Threats of violence to you
Crying and isolation
Threats of violence to themselves
Complete Dissapearance

As with any piece of buggy software, ultimate enlightenment happens when you become the primary source of your users psychiatric issues.

### Introduce vague almost equivalent terms that have real-world differences that you never clearly disclose

  Don'ts              Instead
  Install Software    Consume a module

	For instance, stories, actions, models, views, fixtures, hooks, interfaces, providers, 

These worlds are all utterly meaningless and you should use them interchangeably. However, require very specific relationships to exist as to what can do what and what can talk to whom and never disclose, under any circumstance what this is.

#### Endless terminology rabbit holes.

Here's an example:

Let's try to define "provider" in react:

The <Provider> component makes the Redux store available to any nested components that need to access the Redux store.

Alright, what's a "redux sture":

A store holds the whole state tree of your application. The only way to change the state inside it is to dispatch an action on it.

Alright, what does "dispatch an action" mean:

An action is a plain object that represents an intention to change the state.

Alright, what's an "intention"? And on and on. Every single term is an endless tree of of other endless trees with each level becoming more vague indirect and jargon filled.


Here's an example from react. Say I want to have a shared login dialog between different components. In normal javascript I'd have a function, perhaps
called "dologin" that I'd simply call say, like this:

    dologin();

Something this direct is completely unadvisable. This kind of simplicity should be made impossible. React does indeed make such things not possible.

Instead they have multiple circuitous ways to achieve this:

  Instead of calling a function you can "dispatch" an "action". Then you have a "reducer" that "consumes" the action.
  You can have a new semantic tag called ModalRoot
  You can do a presentational component
  And finally you can create something called "portals"


But what you cannot do, for a reason they have cleverly decided never to disclose is permit simply calling the function.  In so doing they
ensure they've reset knowledge to zero and suppressed the languages built in capabilities through a mind-altering practice using elitest language. 
Now all you need is a huge time commitment to understand it.

#### Change it completely 

	Move things around every version for instances pretend you have 


#### Make things inflexible by crippling expression and compatibility 


## Getting users
Now that you have a dadaist interpretation of James Joyce that changes and blows like the wind, it's time to convince people to use it.

### Pretend this is the only thing that serious professionals use
Here's some examples of leads from the various projects

  Angular: The modern web developer's platform
  Laravel: The PHP Framework for Web Artisans
  Django: The Web framework for perfectionists with deadlines 

Effectively the form is the following: 
  
  Name: We're the best and we're only for smart people

By doing this the agency for failure is moved from the project to the user. You plant and nurture their self doubt so when they fail
using your software they blame their own inadequacies and not your precious creation.

### Remember, this is a cult.

"A cult?!", you may say. Yes, indeed. 

Let's go over some of the common indicators of cults and you'll see what I mean:

  1. The leader is the ultimate authority
  2. Dissent is discouraged
  3. Mind-altering practices are used
  4. Members must seek permission before engaging in certain activities
  5. The group is elitest
  6. The ends justify the means
  This means that members may engage in some activities which they would have previously thought reprehensible.
  7. A Huge Time Commitment
  8. A Requirement to Socialize with Fellow Members Only
  9. There Is Nothing Worth Pursuing Except the Group's Goals
  10. Fear and Dread

  3. The group is paranoid about the outside world


### Provide no data whatsoever for specious claims of acceleration

Non-quantifiable claims are extremely useful. Claiming something is easier and faster gives you plenty of room to backpeddle because there's no specific measurable statement made.  

### This is the new way to build

Simply attribute your framework to a reputable company and then claim it was built by "them" - all of them, despite the fact that
nobody there still uses it. This also works with things such as key/value datastores and other, wider, tools such as source control
and file systems.

The attribution instantly gives your project merit in many people's eyse without any further consideration neccessary.

