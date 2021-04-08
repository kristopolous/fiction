# Principles of Framework Design

Whether you're a contracting firm that wants to lock your client list in by using a technology stack that nobody else knows or you're an 
independent developer who wants to increase the word count of your resume to negotiate a higher pay there's nothing quite like 
creating your own framework.

The following text is a set of guiding principles for framework writing. A framework-framework. The text outlines how to structure your
project using scholarly literature on cults and organizational anti-pattern studies that ensure job security regardless of someone's competency.

By the time you're done with this guide you'll be able to not only let useless nonsense flow from your fingertips 
but also be able to convince others that it's industry best practice. 

For users of frameworks the text helps by outlining the social dynamics and purpose for the decisions made in the popular frameworks. You'll be
able to understand and approach frameworks better in the future by applying the principles which lead to their popularity.

## What is a framework anyway?

There's some debate over what a framework versus a library is.

So let's start with a definitions.

A framework 
  
  * breaks core assumptions about a language or system
  * limits what a user is permitted to do
  * increases complexities by adding new abstractions
  * has non-specific specifications by using unclear and imprecise language

Let's take these one by one.

### Breaks core assumptions 
Unlike a library which seeks to work within existing ecosystems, frameworks intend to create new ones.

In order to wall the framework garden things have to be approached
in fundamentally different ways.

### Increases complexities by adding new abstractions
Leaky abstractions

You're not documenting a technology, you're marketing a product.


### has non-specific specifications by using unclear and imprecise language

### Success story: Chef
When the founder of chef in 2008 decided to create a framework for sysadmin tasks how would he have known it would lead to a $70 million/year company and an acquisition 12 years later.

The key to the success was to introduce entirely new abstractions without being specific about their implementations. By making documentation essentially always written as marketing material chef successfully obscured how to use their software

This was essential for the early adoption of the software. For instance take the overview documentation from 2012 where you would find statements such as this:

> The Chef Server acts as a hub that is available to every node in the Chef organization. This ensures that the right cookbooks (and recipes) are available, that the right policies are being applied, that the node object used during the previous Chef run is available to the current Chef run, and that all of the nodes that will be maintained by Chef are registered and known to the Chef Server.

So no longer are we writing a script that does `apt install tool` instead all our core assumption are changed. We have new terms to learn such as:

 * Chef server
 * Chef organization
 * Cookbook
 * Hub
 * Node
 * Node object (what it means to be available, maintained, and registered)
 * Recipe
 * Policy (and how it's applied)

So we're no longer configuring systems. Instead we are deep into a world of new abstractions and are fundamentally limited by these abstractions. By miring their users in endless confusion opscode (now Progress) was able to commercialize this opportunity to a successful company. 

## Establishing core principles

All frameworks hinge on a set of core principles or beliefs we'll call a doctrine. Doctrines are unwavering assertions about the world
which are presumed to be natural. The set of doctrines form an ideological foundation, this is the framework.

For instance, Ruby on Rails has a document they call "The Rails Doctrine", which as of this writing is linked to on their homepage. 
In it they have a set of 9 core beliefs which they call "the most important pillars".

In philosophy, the level of adherence to a doctrine is called aesthetics.  Something that is "beautiful" adheres highly to a given doctrine.
The aesthetical becomes the goal and the practitioner is judged based on the conformity to the aesthetics.  People with high conformity are
often described using the term nature or natural.

The group of people preoccupied with the pursuit of this aesthetic who practice the conformity form a tribe. Sometimes tribes can have 
disagreements with each other over the "true nature" or "originalism" of the aesthetic and thus split into factions.

Take ballet for instance. There's core beliefs about geometry expressed in the human body and people seeking the purity of this form, 
a fundamentalist interpretation of the principles forms the aesthetic of the art. Same is true for the musicians in the orchestra pit
which only work as an ensemble if everyone is preoccupied with a conformity to the music to be played.

This nexus of the aesthetics in the conformity to a doctrine, often called fundamentalism and its practice, often called orthodoxy 
can also be found in religion, politics, the arts, and for our topic, software frameworks.

That's why the terminology in one of these systems can be readily found in another. For instance, The Rails Doctrine uses the words 
"movement", "doctrine", "originality", "fundamental", "tribe", "heretical" and "nature" all within the 127 words contained within 
the first 2 paragraphs. The orthodoxy is more important than the problem.

The important thing is the preoccupation with the strive for aesthetic authenticty is the practice. The purpose of ballet is to do
the practice of ballet in some factioned form of originalism, such as the Vaganova method, in the purest and most natural way possible.

Any other concern is secondary. Because everything must conform to the doctrine first and foremost, reality has to be melded and shaped to
fit inside the aesthetics.  That's why religion, the arts and politics are ineffective tools for problem solving.  Everything has to be done backwards. 
Practical solutions are forbidden and instead have to first fully exist and then be massaged and interpreted so as not to be heretical and conform to 
the doctrine.

In order to secure the fundamentalist facade, realities, problems and solutions have to either be positioned in a way so as not to cause cognitive 
dissonance or denied as a reality. The principle of denial existing within an orthodoxy is a strong psychological edifice. It permits one to deny
responsibility and not have to worry about things outside the doctrine by rationalizing or imagining away problems.

This is a core mechanism that permits the narrative structures to be considered simple or objective, it's a fundamental othering.

When reality falls outside the doctrine instead of fixing the assumption more often the orthodoxy is amended.

### Success story: React

ReactJS has a wildly inflexible architecture that aggressively forces their users to conform to an orthodoxy.  As an example let's say we have the following
code

    function C() {
      var A = {
            something: () => console.log("hi")
          }, 
          B = document.createElement('div');

      B.onclick = () => A.something();
    }

This small snippet of code violates "best practices" in react and thus is almost, but not quite impossible to do.

See the problem here is that B and A are directly interacting with each other. If we were to map things in react-land, they would 
show that c has "children" of A and B and here A and B talk to each other "horizontally" which is heretic to the purity of the 
orthodoxy.

The hierarchical nature here is an unwavering assertion about the world. Essentially the claim is as follows:

      C
     / \
    A---B

The A <=> B is what forces us to wear a scarlet letter and live on the edge of the town.

Therefore we no longer solve a problem. Instead, we are imposed upon us an aesthetic puritism do to a natural belief of "props down, events up". 
A popular way to do this basic programming technique that's been readily available in effectively every programming language since the first 
digital computer (Plankalkül had it in 1942) is the usual suspects either add "a new testament" to the orthodoxy, in this case with something
called "redux" or figure out an acrobatic way to comply.  

Let's do the second. So we need to "pass down" things that will "pass up". We have a solution, now we must go backwards, first we will go 
into "classes" to make things more orthodox.

    class A {
      componentDidMount() {
        this.props.connector(this);
      }
      something() {
        console.log('hi');
      }
      render() {
        return;
      }
    };

    class B {
      render() {
        return <div onClick={ this.props.onClick }>
      }
    };

    class C {
      constructor() {
        super(props);

        // here's our connecting function
        this.connector = this.connector.bind(this);
        this.state = {connector: ''};
      }

      connector(obj) {
        this.setState({connector: obj});
      }

      onclick() {
        this.state.connector.something();
      }

      render() {
        return (
          <A connector={ this.connector } />
          <B onClick={ this.onclick } />
        );
      }
    };

So to simplify this flow

    A -> B

We now do

    C -> A -> C -> B -> C -> A

Or as a diagram, we get the following:

       .---◢ ◣----.
     .▶B---▶C--.   \
     |  ◤--'|\  ▼  /
      \____/  '►A-'

See how we do multiple round trips passing things through C in order to maintain the hierarchy? This is how we stay within the orthodoxy

If this looks like Ptolemaic astonomy, that's not a coincidence! In Ptolemaic astronomy the assumption of Earth being
the center of the universe was enforced as the orthodoxy.  As a result you got epicycles upon epicycles because the simpler model was
forbidden.


People were so committed to the more convoluted orthodoxy that anyone who questioned it was literally burned alive for heresy.

Claiming that A -> B was even possible would have been an actual death sentence.

The great success of React is in enforcing a new kind of authoritarianism.  So react enforces the doctrine by explicitly
disallowing heretical code. 

It's effectively an authoritarian and maintains equilibruim, as Adam Przeworski claims "mainly on lies, fear and economic prosperity".

 * There needs to be an economic value to the doctrine perceived in the mind of the prospect.
 * There has to be a fear of losing out or falling behind by not adhering to the orthodoxy
 * The core claims have to be fundamentally, exhaustively and obviously fraudulent.

React does this boldly on the first two sentences of their homepage:

"React makes it painless to create interactive UIs. Design simple views for each state in your application"

The thing that they intrinsically complicate the most is what they claim they do the opposite of. Therein lies the
paradox of the cognitive dissonance as outlined above.

orthodoxy is an extremeley poor tool
to solve any actual problem. 
This is why orthodox religion and politics 

t.. actice, called the that whatever the doctrine is, the framework exists to be in service to the doctrine.  It is not supposed to facilitate
the user in addressing problems, but is instead supposed to be the purest expression possible of the underlying doctrine.

These 

The group of peers concerned with the 
This is true 

Conformity Tribalism Orthodoxy and Fundamenalism



## Slow down development as much as possible

Frameworks work at a subconcious level. They permit the users to be constantly busy as they chaperone codebases which 
would otherwise have long term stability all while staking the claim that it's the fastest and easiest solution.

Because frameworks exist primarily in a product space it's worth looking at their value proposition. Frameworks essentially 
act as a modern facilitator to what Frederick Winslow Talor called "Soldiering" in the text "Scientific Management". 
Essentially this means "the evasion of work or duty", the workers you wish to provide to have a vested interest in their own well-being and do not benefit from working above the defined rate of work when it will not increase their remuneration.

Normally a manager would have every reason to dismiss these programmers. To combat this natural inclination, a proper framework makes sure this is impossible by making them unfirable. 

Given a product:

 * Systems should not continue to function without the programmer and
 * Code has to constantly be rewritten in order to achieve the same ends

Also it permits the users to go on constant employer funded vacations to conferencces and training sessions.

From a professional programmer's point of view, the primary goals of any framework are to provide the users with the following:

 * Job security by ensuring brittle applications
 * Endless tasks by ensuring endless complexity
 * A sense of elitism and entitlement
 * No expectations of deliverables
 * Be vague enough so blame can get shifted if things break

By making every project asymptotically impossible to deliver vaporware, the ideal framework ensures that people
are always doing something while at the same time nothing ever gets done. 

The old is dying and the new cannot be born; in this interregnum they're on salary so they make it last as long as possible.

### Job security through obscurity
In trades where theres no guilds or unions, there's a tendency to create career protection through other forms of tribal qualification systems or arcane knowledge.
Making things intentionally complicated so that only a select few people can comprehend them is a common way to capture and exercise power.

People adopt the patterns because they want to have the perceived protective properties of the obscurities.

Worlds of irrelevant relations and materially meaningless abstractions are essentially how fields such as fortune telling and astrology continue unabated.
The form becomes the function and the elaborations its aesthetic.

### Encouraging Brittle Applications
Centralizing code and shaping control flow is essential in building robust software. So a good framework should put up as many barriers to achieving these ends as possible.

It should be done in *the name of* reusability and in *the name of* robust software while at the same time encouraging its exact opposite.

The most popular way to achieve this is by making obvious things hard or extremely complex to implement.  For example, pretend we have a templating language for
websites.

Many websites share a look and feel on each page. Perhaps we could state them as follows:

    <header>
    <main>
    <footer>

Where header is essentially the "state" of the user and some contextual navigation, the "main" is the current region of interest and "footer" is general controls.

A bad idea here would be to have separate copies of header and footer for every different kind of "main". There's many ways of doing this. Perhaps you could have

    function generateHeader() {
    }

    function generateFooter() {
    }

Then you can do something like


    generateHeader(current_state)
    main stuff
    generateFooter()

Now if this all sounds very reasonable to you you haven't acclimated yourself to framework thinking. A proper framework designer would find fault in the above design.

The nature of the complaint is effectively arbitrary because that's merely our McGuffin. The important thing is to forbid such logical things from being possible.

For instance, you could forbid your template from making function calls or including other templates within it. There's enough academic programming literature to misinterpret and 
justify just about anything. But the end result is that you will force the user to do one of two things:

  * make multiple copies of the code
  * do some enormous acrobatics to achieve the ends

It's worth looking into the second option. Here's some example of what you could do. 

### Restrict the language to make all refactoring efforts futile

In our templating language, we would like to eliminate the ability to write maintainable, 
comprehensible code like this:

    if (x) {
      let w = something(x);
      if (w) {
        let z = something_else(w);
        if (z) {
          if(y < z) {
            onething
          } else if(z > y) {
            another
          } else {
            // error 
          }
        } else {
          // error 
        }
      }
    }

We are going to do it with two simple rules: 

  * no assignments allowed
  * must be a single comprehension

Thus we get this:

    { x ?
        ( (something(x) && something_else(something(x))) ?
          ( (y < (something(x) && something_else(something(x)))) ?
            onething : ( 
              (z > (something(x) && something_else(something(x)))) ?
                another : /* error */ 
              )
          )
          : /* error */
        ) : null 
    }

Now there's a lot of questions that come up here:

  * what if something(x) isn't idempotent? Well you forbid that.
  * what if something(x) is expensive? *shrug*
  * what if returning nothing isn't a failure condition? Ah! Wrapper functions!

Speaking of wrapper functions, let's do that to "refactor". 
Our code now looks like this::

    something_else_else(x) {
      return something(x) && something_else(something(x));
    }

    { x ?
        ( something_else_else(x) ?
          ( (y < something_else_else(x)) ?
            onething : ( 
              (z > something_else_else(x)) ?
                another : /* error */ 
              )
          )
          : /* error */
        ) : null 
    }

We still have a problem, the one we shrugged off:

  * what if something(x) is expensive?

Let's do something about it! A cache! By forcing refactoring to require cache-invalidation and naming, the two hardest parts of programming,
you've forced an increase in the underlying complexity in an effort to decrease it.

Our refactored code is now:

    defined(cache_library) || include cache_library;

    something_else_else(x) {
      let has_value = cache_check(something_else_else, x);
      if(has_value) {
        return cache_get(something_else_else, x);
      } else {
        return cache_set(something_else_else, x, something(x) && something_else(x));
      }
    }

    cache_bust();
    { x ?
        ( something_else_else(x) ?
          ( (y < something_else_else(x)) ?
            onething : ( 
              (z > something_else_else(x)) ?
                another : /* error */ 
              )
          )
          : /* error */
        ) : null 
    }


But if we are dealing with caches on modern infrastructures we probably have to worry about race conditions. So let's make it atomic with
a lock. Fine, that'll do!

Here's our final code:

Without the framework

    if (x) {
      let w = something(x);
      if (w) {
        let z = something_else(w);
        if (z) {
          if(y < z) {
            onething
          } else if(z > y) {
            another
          } else {
            // error 
          }
        } else {
          // error 
        }
      }
    }

With the framework

    defined(cache_library) || include cache_library;

    something_else_else(x) {
      defined(lock_library) || include lock_library;

      if (let lock = acquire_lock(cache_check, something_else_else) && lock) {
        let has_value = cache_check(something_else_else, x),
            to_return;
        if(has_value) {
          to_return = cache_get(something_else_else, x);
        } else {
          to_return = cache_set(something_else_else, x, something(x) && something_else(x));
        }
        release_lock(lock);
        return to_return;
      } else {
        // lock unavailable.
        return something(x) && something_else(something(x));
      }
    }

    cache_bust();
    { x ?
        ( something_else_else(x) ?
          ( (y < something_else_else(x)) ?
            onething : ( 
              (z > something_else_else(x)) ?
                another : /* error */ 
              )
          )
          : /* error */
        ) : null 
    }

In this way, every effort to refactor thus increases the overall amount of code and the call-graph complexity. 
Additionally because we create needless problems with effectively arbitrary restrictions, code has to address
entirely invented problems that come as a direct result of this and have absolutely nothing to do with the task
at hand. Before the framework it was a few simple branching statements. Now we have naming issues, cache invalidation, 
deadlocks, idempotency issues, and dependency injection all because we decided to restrict things in the name of
making things simpler.



## Make things as difficult as you can
### The maxim of maximum unreasonability

Outside of the world of programming there are terms "orthodox" and "fundamentalism". 
Core beliefs
Orthodoxy 
Fundamentalism


Consistent orthodoxy and philosophy 
Make easy things hard and hard things nearly impossible. 

Ideas are impossible to execute

### Success Story: Moment.js
Javascript's Date object takes a little bit of work to understand. Because nobody was promoting how to properly used it this provided a
product/market fit for a significant framework based entirely around dates.

Let's say in normal javascript I wanted to subtract two `Date` objects. Let's do that:

    let difference = Date() - date2;

The problem with the above code is that it's simple and easy to understand. There is no elitism behind it and complexity is completely absent.
Additionally it will most likely work indefinitely and it's pretty clear what is happening.

Here is an example of how moment.js fixes all these problems. The equivalent code in moment.js is as follows:

    let difference = moment.utc(
      moment.duration( 
        moment().diff( date2 ) 
      ).asMilliseconds());

By requiring a dependency chain of 3 nested functions to do the same operation, moment.js achieves all the goals of a framework. There is
no assurance of the stability, long term support, or continued relationship of any of those components. Additionally the code has been
made impenetrable so only an inner-circle of acclimated developers will have any idea what is going on.

Additionally there's a sense of accomplishement by complicating the task to make it feel like it's much more significant than it actually is.

## Break as many ways to diagnose defects as you can find
### Make sure stack traces are utterly worthless

Once you've obscured all the basic sanity rails of any system you have to make sure that finding out the new ones
or how things are implemented is utterly inpenetrable. One of the ways to do this is to make sure your framework
has dozens of layers of indirection in between function calls.

This means that if say, user supplied fnA calls user-supplied fnB, and a stack-trace is called, you'll get
the following:

  < between 20-50 frames from your framework >
  fnA
  < between 20-50 frames from your framework >
  fnB
  < between 20-50 frames from your framework >

The core goal that you wish to achieve is to make the developer utterly infantile and helpless, raising their hands
and just claiming it's all "unknowable impenetrable black magic with no consistency or certainty whatsoever". This is
to both insulate you from the risks of exposing your incompetency in your implementation and inculcate a level of
servitude from your users where they have to rely on you anyway.

#### Success Story: Laravel
ActiveRecord style ORMs are perhaps some of the most exemplary frameworks one can find.

Not only do they intentionally obscure the underlying code that is run on the database, causing innocent looking code to
actually have hidden levels of algorithmic complexity that can make it profoundly slow, but they present an interface
to users in order to interact with their data that requires the ORM to inject itself in perhaps dozens of levels of
redirection.

The result is the developer cannot inspect the code in any meaningful way at all and it is effectively a binary blob
with stripped symbols that they are left poking and prodding at. It permits the framework writer to have all the
social benefits of calling something open source but by making the code effectively low-grade cryptographically secure,
they then harbor none of the responsibilities.

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

 * Mild criticisms
 * Profanity
 * Screaming
 * Threats of violence to you
 * Crying and isolation
 * Threats of violence to themselves
 * Complete Dissapearance

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

Alright, what's an "intention"? And on and on. 

Every single term is an endless tree of of other endless trees with each level becoming more vague indirect and jargon filled.

We're of course dealing with concrete deterministic state computers. So there is a crisp programmatic definition of all of these things. The code is something specific. This method of handwaving is crucial for never actually disclosing or promising what that thing is so that if something goes wrong you always have plausible deniability.


Here's an example from react. Say I want to have a shared login dialog between different components. In normal javascript I'd have a function, perhaps
called "dologin" that I'd simply call say, like this:

    dologin();

Something this direct is completely unadvisable. This kind of simplicity should be made impossible. React does indeed make such things not possible.

Instead they have multiple circuitous ways to achieve this:

 * Instead of calling a function you can "dispatch" an "action". Then you have a "reducer" that "consumes" the action.
 * You can have a new semantic tag called ModalRoot
 * You can do a presentational component
 * And finally you can create something called "portals"


But what you cannot do, for a reason they have cleverly decided never to disclose is permit simply calling the function.  In so doing they
ensure they've reset knowledge to zero and suppressed the languages built in capabilities through a mind-altering practice using elitest language. 
Now all you need is a huge time commitment to understand it.

#### Change it completely 

Move things around every version for instances pretend you have 


### Make things inflexible by crippling expression and compatibility 

"The problem with language X is that it allows you to do anything you want."

#### Success Story: AngularJS

When you have the full capabilities of a general purpose language such as Javascript there is possibility that even with careful
precautions users may still be able to produce usable robust software.

The developers at AngularJS had a wonderful way of addressing this. By removing core language syntax they force things to either
be impossible or far more difficult than they would have otherwise.  

The core decision was what to remove while making some things nearly, but not actually impossible. Make it just enough so that documentation
and marketing can be written for the feature but then once someone starts to use it it becomes effectively (but not actually) impossible to
achieve anything.

The subset of features they removed from the language are as follows:

 * any assignment operator.
 * increment and decrement (++, --) since they are just hidden assignment operators
 * chaining epxressions with ; or ,
 * the new operator since it creates things

Thus in order to achieve these ends a whole new vocabulary has to be developed. Not only does this achieve the job-security goals but it
also ticks off many of the core cult features in order to get user adoption. By derailing the task at hand, the users are now focused on
the arbitrary goals set out by the designers of the language.


## Getting users
Now that you have a dadaist interpretation of James Joyce that changes and blows like the wind, it's time to convince people to use it.

### Pretend this is the only thing that serious professionals use
Here's some examples of leads on the homepage of various success stories we've talked about up to now

 * Angular: The modern web developer's platform
 * Laravel: The PHP Framework for Web Artisans
 * Django: The Web framework for perfectionists with deadlines 

Effectively the form is the following: 
  
 * Name: We're the best and we're only for smart people

By doing this the agency for failure is moved from the project to the user. You plant and nurture their self doubt so when they fail
using your software they blame their own inadequacies and not your framework. 

This structure means that despite the person's failure to succeed with your software they will continue to promote it because their failures
with the tool are presumed to only be through their own personal imperfections.

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

--

Afterwards

Let me drop the silicon valley business guy facade.

All institutions are human institutions and computer related ones are no different. The same 
mechanisms that can drive any other system into madness can happen to computers as well.

Toxic systems can only thrive in environments where they are given the privilege to exist.

It's the very nature of the maturity of our technology, the increase in computing speed
and the amount of money flowing through the industry that provide the necessary conditions
for these systems to arise. Because the path to success does not have tight constraints, there
it becomes a recreational theme park full of levers that aren't necessarily attached to anything.
Instead of brevity and efficiency, richness and elaborate complexity become the primary values. 

In the same way that high profits can make the most wreckless management practices not have 
any consequences and thus seen as enlightened, the current conditions give room for the
festering of the worst tendencies in how popularity is formed through systems such as  
authoritarianism, tribalism, and power exploitation.

The disasters are thus never truly disasters because the success or failure of the product was
ultimately irrelevant.

And finally, to answer the question "well, what would you do instead?"

"Direct solutions to problems with the least amount of concerns to aesthetics possible"

What does that look like? It's intentionally unspecified. The disconcern for aesthetics isn't
an aesthetic. It's an eschewing of the practice and a disregarding of the epistemology. 
It's aggressively non-prescriptive and anti authoritarian.

Instead, be able to recognize the pattern and please, don't believe the hype.
