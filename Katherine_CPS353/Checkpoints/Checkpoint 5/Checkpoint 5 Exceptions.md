# Software Engineering Checkpoint 5  
## Add Error Checking to the Compute Engine

This week we'll be making the project resistant to errors.

## Process Requirements

1. Make sure to have **at least 3** commits on **3 different feature branches**
     
2. Choose **one commit per buddy**, and request a code review of that code **before merging to main**. This commit should be substantial enough that getting someone else to review it would be helpful, and should follow the guidelines for how to structure code for review.  
     
3. Your buddy will also send you code to review, make sure to do a thorough review  
     
4. Iterate with your buddy on the reviewed code until the review is approved, and then merge the result to main  
     
5. Make sure all the merge commits on the main branch have a descriptive **commit message** \- avoid things like 'Added files via upload' or 'Merged branch'. You'll want the commit history for the main branch to be useful to get a sense of what changed when. 
   

## Functional Requirements

1. For each of the 3 implemented components (coordinator, computation, and data storage), add validation for the parameters passed to any public methods

	  
	Validation can be as complex or as simple as you'd like \- anything from checking that inputs are not null to validating that file names refer to real, loadable files would count. 

If a parameter does not require validation (ie, all possible values it could take on are valid), add a comment to the method explaining that

2. Add exception handling to prevent uncaught exceptions from reaching any process or network boundaries \- this exception handling should take care of both **expected** exceptions (explicitly declared checked exceptions) and **unexpected** exceptions (runtime exceptions that aren't deliberately thrown by your code), and it should translate them into a response that clients of the API can identify as an error situation (either with an explicit **error return status** or a **sentinel value**).  
     
3. Add at least one unit test that checks that the validation logic works correctly (you can pick which component you'd like to check, although feel free to add tests for all of them\!).  
     
4. Add at least one integration test that checks your exception handling logic from (2) \- specifically, you want to verify that if an exception is thrown in one component, it correctly gets caught and transformed into something that is not an exception as a return value.  
     
5. Download the Checkpoint5TestSuite from Brightspace and add it to your project.   
   

## Checkpoint Submission

1. Make sure everything (including the checkpoint tests from Brightspace from step 5\) is **merged** to the main branch.

2. Make sure you've addressed any feedback from checkpoint 4

3. On Brightspace, for Checkpoint 5, submit **three things** (all in one text submission):   
   - a link to the latest commit on your main branch for this checkpoint  
     - a link to the pull request that you had your buddy review (this will be merged, so look under 'closed' PRs for the link) \- if you have multiple buddies, include all the relevant PRs  
     - a link to the pull request that you reviewed for your buddy \- if you have multiple buddies, include all the relevant PRs
