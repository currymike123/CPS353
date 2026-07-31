# Course Details

Note:  This is a template repo for purposes of making it easy to find amongst the many student repos. Don't actually use it as a template, though.

## Specific Modules

Each module has slides (pdf and pptx), how many days it typically takes to cover, the corresponding assignment, and in-class exercises plus solutions. Feel free to mix up the order/swap modules in and out - the goal with this layout is to make it easy to update/adapt the course. The 'exams' module has some old exams that I give out as practice exams.

## Github Classroom

Site: classroom.github.com

This is a thin wrapper around github that makes distributing starter code really easy (soooooo much better than Brightspace). The workflow is roughly:

For each semester, create a "new classroom" within the CPS353 organization (ex: "SoftwareEng-Spring-2026"). You can add your course roster to the classroom (it's easy to update as you go if you have any late add students), which will let each student associate their name with their github username.

Within the classroom, any time you want to send out starter code, create a "new assignment" - for this course, I typically give them the project starter code (they'll use that all semester and submit their work that way) plus the in-class exercises to work on in class (which they don't actually turn in). For the assignment, give it a name and a template repo (the search for this is a little cluttered, but exact name matching will work). That will create a shortened url that you can send to the students via Brightspace or slides. Once a student clicks the link, it will fork the template repo for them, grant them write access to their copy, and then give them a link to the repo on regular github. From there, 'Open with Github Desktop' will clone the code locally so they can actually get it into an IDE.

As an added bonus for the project, this gives you admin access to their repo for grading purposes.

## Grading, Aligning Incentives

tldr: 20% checkpoints, 20% final project, 30% midterm, 30% final

Since out-of-class work isn't proctored, a large chunk of a student's actual grade is from exams. I've had good luck with an in-class midterm/final, and then an "optional makeup" during finals week (effectively, this is 3 exams with the lowest dropped) - having to take another exam during finals week dramatically reduced the number of "medical emergencies" that students experienced for the midterm and final (and the students who did actually have an emergency could focus on that instead of juggling scheduling logistics, so win/win).

For the project, I've usually split it 50/50 between checkpoints and final version (essentially, first draft and final draft) - the checkpoints are largely graded on completion, with a requirement to fix feedback before moving forward. Students **hate** this, and want to barrel ahead without looking at feedback, which results in a pretty sub-par project where they don't learn much. Projects where students do respond to feedback end up in a much better state, and based on exam scores, those students also learn a lot more. What I've found effective is to make Brightspace enforce this as follows:

- No fixed deadlines (each piece builds on the previous, so they have to do the work one way or another, and it's nice if they get credit for it). **Possible improvement:** 5-10% penalty per day late
- Each checkpoint has a "recommended completion date" displayed as the due date in Brightspace, but accepts submissions at any time
- Checkpoint 1 is visible to everyone
- Checkpoint 2 has a "release condition" of "submits to folder: Checkpoint 1"
- Checkpoint 3 (and subsequent) have 2 release conditions: "submits to folder: Checkpoint 2" (or Checkpoint 3 for Checkpoint 4, etc) AND "Receives greater than 0% on Checkpoint 1" (or generally checkpoint n - 2)

Any submission that doesn't meet the requirements (passing automated tests, making an attempt to respond to feedback) gets a 0 or left ungraded with a note to complete the requirements and then resubmit, so that I can give feedback without unlocking further checkpoints.

Note that these are **release conditions**, not **visibility conditions** - Brightspace in its infinite wisdom implements these as one-way gates. This structure seems to reach a good balance between "must address feedback/meet basic requirements before moving ahead" and "too much process that gets in the way"; a student can start working on part n+1 as soon as they finish part n, but since they aren't supposed to turn in part n+1 until they address feedback from part n, they can't unlock part n+2 until such feedback exists.

I explicitly point out to students that the turnaround time on feedback (I promise them 4 days) should be treated as an external dependency for the project, that part of their grade is effective project management through requirements with soft deadlines, and that poor project management will negatively impact their grade. I imagine this is their first time running across soft deadlines in an academic context, so I spend a while walking them through how to do that (a few days behind schedule is nbd, a week or more behind schedule is a Very Big Deal), and try to provide some structure with the recommended completion dates and a few not-obviously-pointed-out catch up weeks during the semester. If you're looking for where to add content, this is something that is not currently being effectively absorbed by students.

## Sample Schedule

I post this to Brightspace since the Calendar view there is ... suboptimal (these are Fall 25 dates, but it's the same pacing as the previous few semesters):

```
If you end up needing a few extra days for a checkpoint, you can use this info to plan
how you'll get back on schedule (remember to account for the 4 day external dependency
of 'feedback' between each checkpoint):

Checkpoint 1 RCD (recommended completion date): 9/8
Checkpoint 2 RCD: 9/15
Checkpoint 3 RCD: 9/22
Checkpoint 4 RCD: 9/29
Checkpoint 5 RCD: 10/6
FYI: Leave time for midterm exam studying, midterm is 10/16
Checkpoint 6 RCD: 10/27
Checkpoint 7 RCD: 11/3
Checkpoint 8 RCD: 11/10
FYI: Leave time for final exam studying, final is 11/20
Final Project (checkpoints + capstone) RCD: 12/8

Final Project Hard Deadline: 12/15
```
