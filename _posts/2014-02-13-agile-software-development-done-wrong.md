---
layout: post
title: "Agile software development done wrong"
description:
category: blog
tags: [agile, scrum, software engineering]
comments: false
image:
  background: witewall_3.png
share: true
---

Agile software development revolves around iterating in short timeframes with **flexibility** in mind.

From my experience, I've found that so-called practioners of Agile do not have a true understanding of the principles behind and hence why its benefits are not cast in the right light. 
Perhaps the most common of all Agile methodologies is Scrum (Scrum should be thought of as a subset of Agile, not an equivalent), and which is also the one I'm most familiar with so in this post I'll focus on my experience on common pitfalls seen in the Scrum methodology rather than claim expertise over Agile in general.

---

**Common pitfall 1**: _Agile teams can be born in a month_

Introducing Agile methodologies to a team takes time.
Announcing that the team is going to use Agile methodologies does not translate into instant success within a month.
Typically some team members have not necessarily had knowledge of Agile or have little experience with Agile, and hence time is required for them to acclimatise to this new working methodology.

In the software engineering world, employees often switch teams within the workplace or move to other workplaces altogether.
This presents a challenge to the effectiveness of Agile methodologies when new team members are being introduced every so often. 
Sprint planning can be difficult at first when the team's velocity will vary more with newer team members.  

Perhaps the worst offender of this pitfall is the way Agile is taught in universities.
The well-meaning curriculum heads have recently introduced more Agile concepts into the computer science and engineering degrees, but have failed to consider the effective delivery of such concepts.
A senior academic who has never used Agile in real life, claims to have expertise in Agile and teaches Agile in a hand-waving fashion is a recipe for disaster.
This academic insists that Agile teams can be born in the space of six weeks and claims that teams not doing daily in-person standups is not doing Agile properly.
If one pauses to think and realises that university students are not working on this one subject full-time, in the same location, with expertise knowledge of all the software and technologies used, then perhaps daily in-person standup meetings are far from practical.

Agile teams take time to foster.

---

**Common pitfall 2**: _Using Agile tools means we're Agile_

Using issue tracking software like Atlassian's JIRA or Pivotal Tracker does not mean one is working in an Agile manner. 
In true Agile fashion, one really should cherry-pick the tools and methodologies that suit the team and the project at hand.
It is not about conforming to so-called 'standard practices' in a blind manner, but rather to think deeply about what principles can guide software development and consciously experimenting to suit their needs.

Many teams tend to pick Scrum because 'everyone is using it'.
That is a bad mentality, rather one should think of _why_ everyone is using it.
Recently I have seen some teams opt to try Kanban (another Agile methodology) or even a hybrid between Scrum and Kanban called Scrumban.
Kanban seems to work for teams that work on a ticket-based workflow that has tight deadlines, as it ensures there are no blockages in the pipeline.
On the other hand, Scrum seems to work for teams that work on a feature-based workflow that has particular business/functional requirements, as it is focused on deliverables and quick feedback loop.

Pick tools that suit your needs.

---

**Common pitfall 3**: _Stand up meetings are short so I don't need to prepare_

This is particularly true for teams that have recently transitioned to Scrum and think that the daily morning standup is short so they don't have to bother preparing for what they have to say. 
This is not true.
The purpose of the standup meeting is for team members to provide a brief summary of what they worked on yesterday, what problems they encountered, and what they will be working on today.
This should ideally be kept less than 2 minutes, so that as a team of 5-8 should only take around 10-15 minutes at most.
However, more often than not I have seen people interjecting with comments, which sparks a 5 minute long side conversation that should really be taken offline and discussed after the standup.
Standup meeting time is precious, so before the meeting write down a short list of things you want to say, stick to that list, and respect the time of others by leaving longer conversations after the standup

Less is more.

---

**Common pitfall 4**: _Test-driven development works for all projects and teams_

There are a lot of people who live by the principles of Test-driven development (TDD), however a true Agile practioners realises that this is an **option**, not a **doctrine**.
I personally quite like the idea of TDD, as it really forces you to think about how you break down your solution into manageable chunks, and most importantly build testability into your codebase right from the start (instead of an after-thought).
However the caveat to this approach is the maintenance overhead of keeping the tests up-to-date with the latest features of the code.
Done well, this can definitely save heartbreak on large, complex projects.
Done poorly with fragile or irrelevant test cases, and it soon becomes a more of a burden than the codebase it is trying to test.

It is unfortunately that the university context rarely permits TDD to be a student's first choice, since the apparent benefits do not seem to align with tight deadlines and is not taught properly as a discipline. It is also typical for lecturers to justify the brilliance of TDD to students, yet not practise what they preach.

TDD is not for everyone.

---


