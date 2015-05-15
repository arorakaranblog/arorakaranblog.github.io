---
layout: post
title: Migrate your repositories from SVN to GIT, it's time !!
date: 2012-11-06 10:59:04.000000000 +05:30
categories:
- Random
tags:
- git
- svn
status: publish
type: post
published: true
meta:
  _edit_last: '51117020'
  _publicize_pending: '1'
---
<ul>
  <li>Install <code>git-svn</code> on linux</li>
  <li>git-svn clone &lt;SVN repo link&gt; my-new-project</li>
</ul>
<p>Let's move the tags to be proper git tags</p>
<ul>
  <li>
    <code>cp -Rf .git/refs/remotes/tags/* .git/refs/tags/ </code>
  </li>
  <li><code>rm -Rf .git/refs/remotes/tags </code></li>
</ul>
<p>Move the references under refs/remotes:</p>
<ul>
  <li><span style="font-family:Consolas, Monaco, monospace;font-size:12px;line-height:18px;"><code>cp -Rf .git/refs/remotes/* .git/refs/heads/ </code></span></li>
  <li><span style="font-family:Consolas, Monaco, monospace;font-size:12px;line-height:18px;"><code>rm -Rf .git/refs/remotes </code></span></li>
</ul>
<p>Add git server as remote</p>
<ul>
  <li>
    <code>git remote add origin git@my-git-server:my-git-repo.git</code>
  </li>
</ul>
<p>Push it to github:</p>
<ul>
  <li><span style="font-family:Consolas, Monaco, monospace;font-size:12px;line-height:18px;"><code> git push origin --all </code></span></li>
</ul>
