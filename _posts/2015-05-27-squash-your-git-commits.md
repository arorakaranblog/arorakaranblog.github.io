---
layout: post
title: Squash! your git commits.
date: 2015-05-27 14:00:01.000000000 +05:30
categories:
- Github
tags: [code,git,github,squash,commits]
status: publish
type: post
published: true
comments: true
share: true
---
I want to add a feature to a git repository.
Have already created a few commits in my local branch named `Feature-branch`
In order to push this branch to my remote repository as a single commit follow these simple steps:
  
1. Pull latest code from remote master branch:   `git pull --rebase origin master`
    <p><img src="{{ site.url }}/images/{{ "squash1.png" }}" /></a></p>
2. Switch branch:    `git checkout Feature-branch`
    <p><img src="{{ site.url }}/images/{{ "squash2.png" }}" /></a></p>
3. Squash your commits to one:   `git rebase -i master`
    <p><img src="{{ site.url }}/images/{{ "squash3.png" }}" /></a></p>  
* Running this command gives you a list of commits in your text editor that looks something like this:
    <p><img src="{{ site.url }}/images/{{ "squash4.png" }}" /></a></p>
* Replace pick with squash to convert the corresponding commits to one single commit:
    <p><img src="{{ site.url }}/images/{{ "squash5.png" }}" /></a></p>
* After you save and exit the editor, Git applies all changes and then puts you back into the editor to merge all the commit messages:
    <p><img src="{{ site.url }}/images/{{ "squash6.png" }}" /></a></p>
* Change the commit message and save and close the editor to create one single commit:
    <p><img src="{{ site.url }}/images/{{ "squash7.png" }}" /></a></p>
* Commits are squashed to one:
    <p><img src="{{ site.url }}/images/{{ "squash8.png" }}" /></a></p>
4. Force push your feature branch: `git push origin Feature-branch -f`
    <p><img src="{{ site.url }}/images/{{ "squash8.png" }}" /></a></p>
    
<p>There! your feature is pushed to a new branch as a single commit :)</p> 