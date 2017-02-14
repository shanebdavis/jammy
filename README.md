# jammy
If git is an assembly language, then jammy is git's high-level language.

* git: incompetent, stupid, annoying, or childish person (wikipedia)[https://en.wikipedia.org/wiki/British_slang#W]
* jammy: 1. Lucky. 2. Pleasant or desirable. [wikipedia](https://en.wikipedia.org/wiki/British_slang#J)
* jammy git: Lucky fellow .. usually as a result of some surprising and undeserved luck [urbandictionary](http://www.urbandictionary.com/define.php?term=jammy%20git)

# Goals

* never use the git command-line tool again
* opinionated: have an opinion about how the git-workflow should be done, streamline that workflow
  * I averaged 8.5 checkins per day last year. People should be doing explicit checkins 5-10x per day - at least once an hour.
  * branching - there is a pattern to good branch-usage. If we follow it, we can branch much more and do it safely and not get lost in branch-spaghetti.

# Status - a Stub!

I have lots of ideas how to move beyond git. Git is a wonderful tool. It gets the basics right, but it's too manual. It's an assembly language. We need a better way to leverage this amazing tool. Some thoughts:

* streamlined feature branches
  * `jammy start feature my-feature-x`
  * jammy runs in the background and automatically merges in updates from the upstream branch if safe (optional)
  * `jammy done` - merges into upstream branch (if tests pass, possibly)
* detangle the spagetti of checkins and branchs
  * No tool visualizes this right. It gets very confusing.
  * Mostly, we need a way of logically grouping checkins and collapsing the details so we can get a better view of the big picture.
* auto checkins
  * Locally, I want every change I make to be checked in. I want to be able to roll-back to last-hour.
  * When I do `jammy commit` I want the auto-checkins collapsed.
* all tags and branches synced all the time with remote
  * It makes no sense to me that git pull and git push don't sync the ENTIRE repro by defeault.
  * Perhaps ocasionally you want local branch to just be an experiement that you don't want synced, fine - that branch should be tagged as such and therefor won't be pushed. But most branches should be pushed. There should be a warning for any branch that isn't pushed.
  * When I say "jammy push" I want to know my local repro is 100% pushed to the cloud. If my local computer blows up, I'm safe.
* semantic versioning
  * Are there advantages to integrating semantic versioning into jammy?
* EASY editing of checkin messasges. Checkin messages are CRITICAL and "git rebase" is a PITA when all you want to do is fix a type-o in your message. This is unacceptable.
  * We need to be able to fix checkin messages even on the remote repro.
  * Instead of rewriting history for the remote repro, one idea is to maintain a ".jammy_view" file in the root of the project which contains any edits for checkins, and when you view your history with a jammy-aware tool, it shows the updated checkin messages.
* retrospective branching / virtual branches
  * the ability to arbitrarily edit the branch history - even on the remote repro
  * maybe the last N checkins SHOULD have been on a new branch. Make it easy to do this.
  * This probably requires more stuff in .jammy-view, since you can't alter the branch history on the remote server.
* Colapssable, hierarchical log.
  * If we are checking in more, we need a way to zoom out and see the big picture, ignoring the minuta of all the checkins.

# Feedback

Please contact me if you have ideas on what should be in a high-level-language for controlling git: [shanebdavis](https://github.com/shanebdavis)