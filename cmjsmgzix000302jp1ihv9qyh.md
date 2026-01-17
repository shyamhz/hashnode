---
title: "Do you really understand Version Control?"
datePublished: Tue Dec 30 2025 13:27:51 GMT+0000 (Coordinated Universal Time)
cuid: cmjsmgzix000302jp1ihv9qyh
slug: version-control-system
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1767101045265/86342dd9-33a3-4ad6-a945-9f27dd2e23bb.png
tags: version-control, git, source-control, version-control-systems, source-code-management, chaiaurcode, chaicohort, chai-code, webdevcohort2026

---

If you are a programmer you may already have heard about version controlling and thought "OK, so that is something I just need to learn because every experienced developers use it" and also all the tech instructors too not just teach it but also highly recommend controlling project source code through tracking and versioning.

But have you ever stopped and thought why? Why do we even use **Version Control System** (**VCS**) and **why it was created in the first place**? Exactly **how** version controlling helps us or why from a small side project to big corporate products **all use some kind of version controlling tools**? Yes Git is just one of many Version Controlling tools.

Before jumping into how VCS work we need to understand what problems programmers faced when version controlling was not a thing yet. We must be able to relate to the programmers who had to invent an entire new concept and what pain points they were trying to eliminate to really grasp why it’s really need.

# Why Version Control?

Imagine you are creating a personal side project , where you have all the features planned out and you know what you are building and you are adding one nice feature after another as you please. After few weeks your project has grown decently big and significantly more complex.

Then suddenly you find that somewhere in the whole development process till now you have introduced **a major bug** in the codebase at some point and all the recently added features **depend on it**. Now you need to fix the bug without any idea **when and where** the bug was introduced and how to pinpoint it’s source.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1767090624300/8285f48e-1493-4ae8-884f-2a0c945b4db4.png align="center")

Now you wish only if you could get to that exact point where the bug was made **before** so many dependent features were added. But it is now impossible to get back to that exact point and it is too hard to pinpoint the problem without losing significant time and sanity. Feel the frustration?

Exactly this was one of the **major reasons** developers needed a solid way to track different version of their code from the very beginning to completing the project, so they could revert back and forth to any tracked version as they wished. To focus on building the product rather than bug hunting for hours or days or sometime even weeks.

The diagrams below visualizes exactly how a VCS solves that problem and helps programmer make changes that get tracked and can be reversed as needed creating a smooth software development experience without frustration and regret.

1. ## Start tracking version from the beginning
    

![Diagram 1](https://cdn.hashnode.com/res/hashnode/image/upload/v1767082887797/1ceb823f-7d37-4dcf-b678-38cf6442ac97.png align="center")

2. ### Revert Changes and fix the bug
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1767091043837/80e70826-a726-4aa0-93aa-d8f66fffefb7.png align="center")

3. ### Continue with the corrected code
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1767091156224/936a6231-6feb-4934-a32e-675f065de991.png align="center")

VCS helps us revert or rollback changes and get to the exact point where the bug was introduced and fix it and continue development with the corrected version of the code.

But version controlling is just one of the problems that pushed the development of Version Control Systems.

# The collaboration hell

Now imagine you are working in a group project with your friends.. how you would share your whole project to your friends and how will they share their work with you? A simple and straightforward way can be using using zip file in a pendrive or over the internet. To keep the example simple we will go with the pendrive option.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1767084479767/c8f67b23-e0a5-4132-8fe3-8a799e068819.png align="center")

So your friends take the project from pendrive, make changes, add new commits and give you the pendrive back with latest changes inside the drive and there you have your new feature, sounds simple enough or is it?

Think what if the pendrive goes around between your friends before returning to you and your friends make changes to the project and you add some features to your local version of the project too at the same time. Then this will create a conflict.. whose changes are to be taken as the final one and which one to reject? or what if someone overwrote someone else’s changes while working?

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1767091787685/a84a7889-31ae-4da9-96a0-3b875e2cc41e.png align="center")

We solved the tracking and versioning problem to make bug fixing or rollbacks seamless but now we have collaboration and code merging conflicts and in the real world software development flow of collaboration can make or break the whole development process.

# Single source of Truth

Now think if there was one singe source of truth, one dedicated maintained version of the project that would be the only version that is taken as reference or simply as the latest and only correct version of the codebase and where all new changes are merged.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1767089194510/8028415f-4584-4dcb-99cf-86cc060e83d3.png align="center")

As you can see in the above diagram before making any changes to the local codebase the latest remote version is always fetched and the local version is replaced with the remote latest version. This way everyone **always** has ***all the latest changes*** and have ***identical*** codebases. And remote tracking is essential part of a complete Version Control System.

Typically a remote VCS server is used as a centralized tracking system that tracks new changes just like the local tracking. The local VCS and the remote VCS always use the same version controlling tool to make it possible to sync local and remote tracking in a compatible and uniform manner.

For example [Github](https://github.com/), [Gitlab](https://about.gitlab.com/), [Gitea](https://about.gitea.com/) all use [Git](https://git-scm.com/) internally. They support, and are built around hosting, projects that specifically use only Git as version controlling tool.

# Summary

So let’s summarize exactly what problems Version Controlling Systems solve.

1. **Unavoidable complexity:** The very primary issue VCS solve is losing changes and intermediate states of our work by storing snapshots of older versions of our projects and enabling us to roll back or reverse our mistake or fix them. Without this tracking, pinpointing a bug in large codebase with over hundreds or thousands of files would be like searching for a needle in a haystack. Think about Linux kernel development as an example.
    
2. **Lost information:** As we learnt in the **collaboration hell** section that having no single point of reference is like being lost in the sea without any sense of direction, remote VCS servers act as a lighthouse and always point to the latest valid snapshot of the project we are building.
    
3. **Collaboration history :** Before VCS or Version Control System was a thing deciding who is responsible for a particular piece of code written in a codebase was almost impossible. Without proper identification maintaining that code or asking the right contributor to make modification to that code was not possible.
    
4. **Merge Conflicts**: Not only having a single remotely tracked version of our codebase helps preserving intended changes into the codebase but also it serves as a rollback point where we can get back and resolve all conflicts between changes made by different contributors.
    

# Conclusion

From this you may have gained a basic understanding of why we actually need version controlling in our projects and why it was necessary to invent version controlling at all in the first place. Today no serious projects or real world products are developed without using some kind of source tracking or version controlling.

There is no one single universal tool that is used to maintain source code but the most popular one is Git. And that is why there are more than one remote VCS servers built around Git specifically.

Hopefully now you understand why Version Control System is an extremely crucial part of modern software development and will be able to explain to others simply as well.