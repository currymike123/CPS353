# Software Engineering Checkpoint 8  
## Performance Tuning

## Process Requirements

1. Make sure to have **at least 3** commits on **3 different feature branches**
     
2. Choose **one commit per buddy**, and request a code review of that code **before merging to main**. This commit should be substantial enough that getting someone else to review it would be helpful, and should follow the guidelines for how to structure code for review.  
     
3. Your buddy will also send you code to review, make sure to do a thorough review  
     
4. Iterate with your buddy on the reviewed code until the review is approved, and then merge the result to main  
     
5. Make sure all the merge commits on the main branch have a descriptive **commit message** \- avoid things like 'Added files via upload' or 'Merged branch'. You'll want the commit history for the main branch to be useful to get a sense of what changed when.   
   

## Functional Requirements

1. Using any or all of the techniques we've covered, find at least one CPU-based performance bottleneck in your compute or coordinator components. **Do not just look at the code and guess** \- measure the code in some way that identifies the bottleneck  
     
2. Fix/improve the bottleneck(s) from (1) to improve performance by at least 10% \- create a second implementation of your interfaces for the faster version. Include a **comment** at the top of the faster implementation with the details of what you did for step (1) to identify the bottleneck.  
     
3. Create a benchmark test for your compute engine and coordinator components (this will be an integration test). What Data Store you want to use for the benchmark is up to you (either a real, file based one, or a test-only version).   
   1. Have the benchmark test use both the original and the faster versions of your code  
   2. Have the benchmark test pass if the new, faster version is at least 10% faster than the original version  
        
4. Document the results of the test in either the README or an additional text document in the repo  
   1. Include before and after benchmark numbers from your benchmark test  
   2. Include a link to the benchmark test in your repo  
   3. Document what the issue and fix were at a high level (the level of detail you might put in a commit description). Feel free to include links to the specific PR for the fix alongside the description  
      

## Checkpoint Submission

1. Make sure everything is **merged** to the main branch. Note that there are no provided tests for this checkpoint \- you'll need to make sure your testing is sufficient\!

2. Make sure you've addressed any feedback from checkpoint 7

3. On Brightspace, for Checkpoint 8, submit **three things** (all in one text submission):   
   - a link to the latest commit on your main branch for this checkpoint  
     - a link to the pull request that you had your buddy review (this will be merged, so look under 'closed' PRs for the link) \- if you have multiple buddies, include all the relevant PRs  
     - a link to the pull request that you reviewed for your buddy \- if you have multiple buddies, include all the relevant PRs
