---
layout: post
title:  The CodePush Issue
categories: [CodePush, Mobile Development, React Native]
---

CodePush, the App Center cloud service by Microsoft, gets tons of praise on the web. And yes, I see the benefits, but I also have some concerns about the extent folks might use it.


Before I start explaining, let me tell you, that I'm by no means an experienced React Native developer. I mainly use Ruby and Rails but for a few months now, I've been working with React Native. And I really, really enjoy it. I also enjoy CodePush because it gives me the ability to test and ship my code in an easy way. Until it doesn't...

In case you are familiar with CodePush, you can skip the next few lines. If not, here are some bundled information. [Microsoft's CodePush documentation](https://learn.microsoft.com/en-us/appcenter/distribution/codepush/) describes it as a cloud service that enables React Native developers to deploy mobile app updates directly to their users’ devices. And the purpose is:

> [...] addressing bugs, adding small features that don’t require you to rebuild a binary, or redistributing it through any public app store.

### Small Features and Bug Fixes

CodePush makes it incredibly easy to ship features and bug fixes. So easy, that you could end up using it for not only small features and bug fixes but for much more. It's convenient. You don't have to go through app stores, which also means you don't have to wait for an approval by Apple or Google. Again, convenient.

There's a downside to it though, or even a few:

You can't use CodePush for every change. For example when native code changed. That could happen when you merged a dependabot PR that updates a library with native code. If that is the case, you have to create a new build and open the app store(s).

But let's assume your native code doesn't change that often, so you use CodePush and everything seems to be fine. You don't check the app stores, because there's no need for it. And when you finally do, you want to close it right away because you see a couple of warning that need to get addressed on top of your feature work.

And the third possible issue: missing knowledge sharing. Because it's so easy (and on first sight convenient) to use CodePush, folks might feel intimidated when they have to go through app stores. But it's not. It's just a bit different. And it takes longer (you have to submit a release, wait for an approval and publish that release).

### Let's make everyone happy

Whenever possible try to make everyone (including yourself) happy. It might be easier than expected. Use CodePush for small features and bug fixes. Teach everyone who changes a single line of code in your mobile application how to create a release that goes through app stores. Create understandable documentation including step by step guides: either as a page or via a script. Create an easy-to-follow Release plan and give everyone access to add feature implementations and bug fixes (this comes in handy when you write the release notes). This isn't possible from one day to the other, but with time, it will improve the stability of your application and happiness of your team.