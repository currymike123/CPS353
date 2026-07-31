# Software Engineering Checkpoint 2: Draft the APIs

This week, we'll be starting work on the code for the semester-long project. To kick things off, you'll be building the APIs for the various components.

## Background Info:

The overall system will consist of:

1. A **user**, who will provide information about a job. Specifically, they'll provide an **input** source, and **output** source, and **delimiter** characters for results  
   1. Note: exactly **how** the user will provide this is up to you, and you don't have to decide just yet; for now, you'll be designing the API that they will use, but whether that API gets accessed via REST commands, JSON, protocol buffers, javascript, the command line, or other is something we'll go into more detail on in a later assignment  
2. A **compute engine** that will take in a **stream** of integers, and output an integer and its result. What that result is will be partly up to you\! As part of this assignment, you'll be deciding what your compute engine will compute.

For example, if you decided to compute the factors of a given input, then for an input of "6,12", with result **delimeters** of ';' between input/result pairs and ':' between a given input and its result, the output would be "6:1,2,3,6;12:1,2,3,4,6,12". Note: For any additional output formatting (such as the commas between factors), you can choose to make that user-configurable in the API or not.

For this checkpoint, you'll be designing APIs between several components:

1. Between the user and the compute engine (this will be a **network** boundary)  
2. Between the data storage system and the compute engine (for input and output sources) \- this will be a **process** boundary  
3. Within the compute engine, between the component that handles reading and writing the job, and a component that does the actual computation (a **conceptual** boundary).

**Note:** There are lots of different ways to design a generic computation engine. For this assignment, you **must** use the APIs and components as described above (later assignments are going to rely on this specific architecture).

## Part 1: Decide on a computation

Pick a computation for the system to run, and document it (in regular English, no need to code it yet) in the **README.md.** Include a sample input and output (ex: ‘The system will find all the factors of the input number, for example, an input of ‘6’ would have an output of 1,2,3,6’)

You can pick anything you want, with two restrictions:

1. The input to the computation must be a **single positive integer** (any integer greater than zero and less than Integer.MAX\_VALUE is valid)  
2. The computation must be somewhat **CPU intensive**. For example, adding together several numbers is not CPU intensive, factoring large numbers is.

Some examples:

- Finding all the factors of the input  
- Calculate the Collatz sequence for an input ([https://en.wikipedia.org/wiki/Collatz\_conjecture](https://en.wikipedia.org/wiki/Collatz_conjecture))  
- Find the largest prime smaller than the input  
- Convert an input into English words ("1" \-\> "one", "21" \-\> "twenty-one")


The first hundred problems on Project Euler ([https://projecteuler.net/](https://projecteuler.net/)) are also good for brainstorming (that's where the English words example came from). Caution: The later problems are also great for brainstorming, but are non-trivial to solve, so don't accidentally go down a rabbit hole.

The computation doesn't need to be **programmatically** challenging, but it does need to make the computer spin its wheels a bit \- in later assignments, we'll be doing performance tuning, which is both more interesting and easier when there's substantial work happening. A good sign that a computation is CPU intensive is if it involves many loops, ideally with at least one nested loop.

Try to come up with something unique, but if you're stuck, you can use one of the examples listed above. If you have an idea but aren't sure if it would be a good fit, feel free to run it by me.

## Part 2: System Design Diagram

Draw up an overall **system diagram** of how the various components interact (this will be helpful in drafting your **prototypes**). Include this image in your README.md:

1. Commit the image to your repo  
   2. Add a link to the image in your README, so that it displays inline (hint: Github Markdown is a well-documented format online, you may need to look up how to add images to it)


	Make sure you have **all 3 APIs**, and that they are between the components described above.

## Part 3: Build the APIs (Planning note: this is the largest piece of the checkpoint)

**Confusion Note:** Most likely, you’ve never written code this way before. If it feels confusing and silly because it’s **overly complex** (ie, this feels like a crazy Rube Goldberg contraption), that’s ok \- over the course of the semester, you’ll get to see how useful this approach is. If it feels confusing and silly because nothing makes sense (more like a postmodern performance art piece), **that’s a problem** \- usually, that means you haven’t quite figured out how APIs and prototypes are supposed to interact. Reviewing the examples from lecture can be helpful.

**Functional Requirements:**

Note: you'll be using some custom annotations for this assignment.  See the 'Project Annotations' document in Brightspace (under 'Readings') for more details about what these are and how to use them.

For each API, you'll want the main **interface** and a **prototype** class, along with any required **return/request interfaces**. You do not need to implement any non-protoytpe classes just yet.

1. An API between the **user** and the **compute engine**. The user will specify a source for the input, delimiter characters for the output, and a destination for the output.   
   1. Make sure to make the source/destination **general** \- the source could be a local file, a networked database, or something more custom. The only guarantee you have is that **the data storage system will know how to access it**  
   2. Allow the user to opt to use some reasonable **default** delimiters if they don't wish to specify their own  
   3. Add the @NetworkAPI annotation to the interface representing the API, and @NetworkAPIPrototype to the prototype method in the prototype class for this API

2. An API between the **data storage system** and the **compute engine**. The data storage system is responsible for reading from and writing to user-specified input and output sources.  
   1. Similarly to 1c, add @ProcessAPI and @ProcessAPIPrototype to the interface for the API and the prototype method  
   2. Eventually, this API will handle a **stream** of integers \- we haven't covered streaming yet, though, so for now you can use a list or array; make sure to wrap those specifics in a general interface\! This is going to be an API that will **change over time**

   

3. An API between two separate **components** within the compute engine. One component will handle initialization, reading, and writing for the job, and a second component will do the actual computation.  
   1. As a first step, determine which component is the **user** for this API, and make sure your design and prototype reflect that  
   2. Similarly to 1c, add @ConceptualAPI and @ConceptualAPIPrototype to the interface and prototype method for this API

**Process Requirements (Complete these as you go through the functional requirements)**

1. The three APIs should have at least 3 **separate commits** in total (at least 1 per API, but possibly more\!).   
2. Choose **one commit per buddy**, and request a code review of that code **before merging** **to main**. This commit should be substantial enough that getting someone else to review it would be helpful, and should follow the guidelines for how to structure code for review.  
3. Your buddy will also send you code to review, make sure to do a thorough review  
4. Iterate with your buddy on the reviewed code until the review is approved, and then merge the result to main  
5. Make sure all the commits on the main branch have a descriptive **commit message** \- avoid things like 'Added files via upload' or 'Merged branch'. You'll want the commit history for the main branch to be useful to get a sense of what changed when.

## Checkpoint 2 Submission:

1. Make sure you've addressed any feedback from checkpoint 1  
2. Commit the Checkpoint2TestSuite to your repo in a feature branch with a pull request  
3. Merge that pull request into your repository. In order to do so, all the tests will need to pass. If the tests **are not passing**, that usually indicates a problem with your code. **Do not edit the checkpoint tests without prior approval from Katherine.**   
4. On Brightspace, for Checkpoint 2, submit **three things** (all in one text submission):   
   1. a link to the latest commit on your main branch for this checkpoint  
   2. a link to the pull request that you had your buddy review (this will be merged, so look under 'closed' PRs for the link) \- if you have multiple buddies, include all the relevant PRs  
   3. a link to the pull request that you reviewed for your buddy \- if you have multiple buddies, include all the relevant PRs

