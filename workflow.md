# Our Workflow

The tech department at barre3 uses an issue tracking called [Sprint.ly](http://sprint.ly/) to manage our workflow and provide transparency around our priorities and progress. Task lists fall short in workflows where work passes through multiple states. Sprint.ly's [Kanban](http://en.wikipedia.org/wiki/Kanban)-style dashboard makes it clear which state issues or "work items" are in and when they might be soon. The "barre3online" product in Sprint.ly tracks issues for both the current website (barre3-wp) as well as the new website (barre3-rails). 

## Work Items

All requests to fix or change something on the barre3 website or app must be tracked as a work item in Sprint.ly. If you're someone who directly requests a lot of changes or fixes (i.e. you're QA or a product stakeholder), you should be trained in how Sprint.ly works so you can create work items yourself. If you're a member of the tech team and receive a request for a fix or change and this person doesn't know how Sprint.ly works, you create a work item for their request. There are four different kinds of work items in Sprint.ly: 

1. **Story -** A story is often a new feature or additional functionality. Stories in Sprint.ly are green. In general it is something that is perceived to be adding value to our product - either for customers or for our business. A good rule of thumb is that anything that requires more than one step to complete or requires more than one person to complete, then it's a good candidate to be a story. Stories can have subtasks containing other work items. 
2. **Task -** A discrete unit of work that a single person needs to complete. An example of a task could be "Add 'Every Mother counts to the 'How did you hear about us' dropdown". Tasks in Sprint.ly are dark gray. 
3. **Defect -** A defect is a bug. An example might be "Campaign monitor mailing list is not updating for Austin Studio". Defects in Sprint.ly are red.
4. **Test -** A test of some sort. Tests in Sprint.ly are blue. For the time being, we're just going to use test work items in stories to define test cases. That said, all work items must be tested in order to be considered "done". 

## Creating a work item

Once you've chosen the appropriate kind of work item to create, the first step is to add a name the work item. If it's a story, you'll have to use the "As a (blank), I want (blank), so that (blank)" format to clearly define the value the story is providing. If it's not a story, fill out the "What is it?" fields with a brief (1 sentence max), but distinguishable description for the work. 

The next step is to enter a description of the work item. Before we can even consider starting to work on a work item, we need to have a clear definition of what the work is and what it means for that work to be done. The description must make this clear that someone who has no background on the issue can easily understand what's required. Here's exactly what's required to describe each kind of work item: 

1. **Story -** Some high level, unpolished wireframes to show the general flow of this feature. 
2. **Task -** Provide everything someone needs to address this task, including links to relevant pages in the app, copy, images, etc. 
3. **Defect -** Include everything you know about the bug, including who and how many people are effected, screenshots, links, steps, etc. The person reading this bug should know how to replicate the issue and have clear instructions of how to resolve the issue. 
4. **Test -** TBD

If you're the one creating a work item, the onus is on you to fill out a complete description. If you don't have enough information to fill out a complete description, you need to fetch it from somewhere or someone. 

## Lifecyle of a work item

There are five stages of a work item, each represented by a "Kanban" column in Sprint.ly. We've also added two internal "Pre" statuses:

1. **Someday -** All work items start out here and should be properly defined upon entry. The someday pile is groomed regularly to better define items or throw them out. 
2. **Backlog -** Includes a prioritized list of items we think can be realistically completed in the next couple weeks. When a resource is looking for new work, they'll take the top of what's available in the backlog. If an item isn't defined well enough per the criteria above, it will be rejected back to "Someday". 
3. **Current -** Means someone is currently working on the item. Since people can't really work on more than one thing at a time, there shouldn't be that many items in this column at a given time. 
4. **Pre-Complete** (for dev items only) Before a dev work item is considered “Complete”, it must be code reviewed. To code review a feature, check in your work on a feature or issue branch with the Spint.ly issue in the name (see [Gitflow Workflow](https://github.com/barre3/barre3-rails/wiki/Code-Standards#gitflow-workflow)), then open a pull request to merge your branch into the “staging” branch. Once you open the pull request, making sure it can be automatically merged and that it passes unit and integration tests, add the “pre-complete” tag to the work item and leave it in the done column. Once the work is code reviewed (likely by Peter), it will be merged into the staging branch which in turn automatically deploys to staging. It will be the reviewer’s responsibility to update the work item to “Complete” following deployment to staging. 
5. **Complete -** Means the item has passed code review, has unit and integration tests (not applicable for barre3-wp), passes those tests and has been deployed to staging. In the case of a bug, this means we're ready to send it to QA. In the case of a story, that means we're ready to demo to the team, then send it to QA. 
6. **Pre-Accepted** - (for dev items only) This means the item has passed validation either from QA and/or the stakeholders. However, before a dev work item is considered “Accepted”, it must be deployed to production. When QA validates a dev issue, add the “pre-complete” tag. Whomever conducts the deploy is responsible for accepting items in Complete tagged "pre-accepted". 
7. **Accepted -** The work item has been deployed to prodution and we can forget about it. 


## Meetings

This process is supported by the following meetings, in order of smallest and least formal to largest and most formal: 

1. **Standup -** These 10-minute meetings are held every morning at 9:50am. All members of the technology department are required to join. Everyone else is optional. During the meetings, each member of the team explains what they're working on, points to it in the Sprint.ly dashboard so we all know exactly what they're talking about, and explains anything that might prevent them from completeing their work (i.e. they are "blocked"). As a result, the Sprint.ly dashboard should accurately represent the state of work and everyone should understand what they should be working on. 
2. **Triage -** These small meetings are held about every other week between Peter and at least one stakeholder (Anne or Chris most likely). During these meetings, we review the Someday and Backlog lists to see which items are still important and which ones require more definition. As a result, we should have confidence that these lists define the content and priority of our work. 
3. **Story Definition -** These meetings are held to better define a story by whiteboarding or reviewing wireframes and/or creating Cucumber test cases. A representative from dev, design, qa and product is always present (usually Peter, Tiffany, Chris and Sarah). They're generally impromptu and last an hour or more. 
4. **Sprint Planning -** Depending on the length of sprints, the meeting is held weekly or bi-weekly with at least one stakeholder (Anne or Chris most likely). We're going to aim to have these Monday mornings. Should ideally be half an hour and no more than one hour. As a result, the team and stakeholders should have a clear idea of what's expected of them for the next week or two. 
4. **Strategy and Roadmap Meeting -** These are big, long meetings with steakholders where we discuss the feature roadmap, discuss potential features, review high level wireframes of stories before they enter development and demo working code of stories that are in the "Complete" and not "Accepted" stage. 
