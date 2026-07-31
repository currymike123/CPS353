# Software Engineering Checkpoint 3  
## Adding Unit Tests and a Testing Framework

This week we'll be adding the Test Driven Development part of implementing the computation system.

## Process Requirements

1. Make sure to have **at least 3** commits on **3 different feature branches**
     
2. Choose **one commit per buddy**, and request a code review of that code **before merging to main**. This commit should be substantial enough that getting someone else to review it would be helpful, and should follow the guidelines for how to structure code for review.  
     
3. Your buddy will also send you code to review, make sure to do a thorough review  
     
4. Iterate with your buddy on the reviewed code until the review is approved, and then merge the result to main  
     
5. Make sure all the merge commits on the main branch have a descriptive **commit message** \- avoid things like 'Added files via upload' or 'Merged branch'. You'll want the commit history for the main branch to be useful to get a sense of what changed when.  
   

## Functional Requirements

1. Familiarize yourself with the “filter” option in build.gradle \- you’ll be adding tests that don’t (yet) pass this week, and you’ll need to **filter them out** from your build.gradle so that github still allows you to merge your pull requests. This is an exception to the 'outside resources are suspicious' policy \- you'll want to look at the documentation for gradle ([https://docs.gradle.org/current/userguide/java\_testing.html\#test\_filtering](https://docs.gradle.org/current/userguide/java_testing.html#test_filtering) is a good starting point), and possibly stackoverflow.  
     
2. Within the 'src' folder, create **empty implementations** for each of your 3 APIs. These implementations shouldn't do anything just yet, but they should have **fields** (you might also know these as 'attributes' or ‘instance variables’) for any APIs that they'll need to call (for example, the component that will talk to the data store will need a DataStoreAPI field; check your **system design diagram** from last week to make sure you don't miss anything). Methods should return **default** or similar values (empty string, null, failure values). Feel free to use the pattern we talked about in class for response values\! At the end of this step, you'll have 3 java classes, one per API, and possibly some implementations for your request/response objects (if you need them to make things compile).  
     
3. Within the 'test' folder, create **smoke tests** for each API. Use **Mockito** to mock out API dependencies and optionally, any method parameters where the type of the parameter is an interface. The prototypes from the previous assignment are a great place to start for creating these. For now, these tests will fail (because the implementations don't actually exist), that's fine\! Put the tests for each API in their own Test\<Name of API\> class.

   

   Not all of the tests may require a mock object. That's ok\! How many mocks you'll need will depend on the interfaces you created for checkpoint 2\. You will definitely need mock objects in at least one of the tests, however.

   As you write these tests, you may discover things you want to tweak with your APIs. Feel free to do so\! APIs are much easier to change before they're implemented rather than after.

   

4. Within the 'test' folder, create the **infrastructure** for an integration test:
   
   a. Create a test-only **in-memory implementation** of your input and output configuration interfaces (Note: if you find that you were overly-specific about the input/output config in your API, now is a good time to generalize it). The input config should contain a **List\<Integer\>**; the output config should contain a writable **List\<String\>** that the DataStore will write to. You'll have two new classes at the end of this. Note: these are test-only implementations. Your APIs should still remain generic enough to support other implementations, such as file-based input/output.
   
   b. Create a test-only **in-memory implementation** of your Data Store API that accepts the input/output from (a). Because this is test-only, you don't need to worry about process boundaries or scale issues; you can "read" the input as the list of integers in the input config, and "write" the output to the list of strings in the output config. Because this will never be exposed to users/outside of test code, you're free to make type assumptions/cast inputs in convenient ways without detailed error checking. You'll end up with one new class after this step.  
        
5. Within the 'test' folder, write an **integration test** for your two compute engine components, using the empty implementations from (2) and the test-only data store from (4). For this test, you will not have any mock objects. Put this test in its own ComputeEngineIntegrationTest class.

- Give the test the **initial input**: \[1,10,25\], with no delimiter specified  
- Add **validation** that what is written to the output is consistent with what your compute engine will (eventually) compute. Note: because you haven't implemented the engine yet, this test will fail. That's ok\!


## Checkpoint Submission

1. Make sure everything is **merged** to the main branch. You should have:  

     In the src folder:  
     - All your APIs from last week  
     - 3 empty implementations of the APIs  
     - (possibly) some empty implementations of request/response types (depending on your architecture)  

     In the test folder:  
     - 3 unit test classes, one per API  
     - An in-memory implementation of the DataStore, input, and output configs  
     - An integration test for the two components of the compute engine, using the in-memory data store

2. Make sure you've addressed any feedback from checkpoint 2  
 
4. Create a feature branch to merge the Checkpoint3TestSuite from Brightspace into your repo (make sure it's in the test/ folder). In order to do so, all the tests will need to pass. If the tests **are not passing**, that usually indicates a problem with your code. **Do not edit the checkpoint tests without prior approval.**   
5. On Brightspace, for Checkpoint 3, submit **three things** (all in one text submission):   
   - a link to the latest commit on your main branch for this checkpoint  
   - a link to the pull request that you had your buddy review (this will be merged, so look under 'closed' PRs for the link) \- if you have multiple buddies, include all the relevant PRs  
   - a link to the pull request that you reviewed for your buddy \- if you have multiple buddies, include all the relevant PRs

