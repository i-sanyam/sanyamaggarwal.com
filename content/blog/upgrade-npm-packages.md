---
date: '2021-10-07'
title: How to upgrade to npm packages with breaking changes?
tags: [nodejs, npm, best practices, javascript]
author: Sanyam Aggarwal
link: https://sanyamaggarwal.medium.com/how-to-upgrade-to-npm-packages-with-breaking-changes-8bde1ed45685
post_type: medium
description: A whole lot of features rolled out in ES6 and this caused a lot of npm packages to release newer versions with breaking changes

---

This was my first blog about tech.

I had to upgrade the [mongodb npm package](https://www.npmjs.com/package/mongodb) in our code base from version 2.2 to 3.6. Between these releases ES6 had released and [async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function), [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await) were introduced. Newer packages of the versions were released with the cleaner async methods instead of using [callback functions](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function). The 2.2 version used callbacks and the 3.6 version had an async API. To make matters worse, the package was used haywire everywhere in the code base which required that I change every file where this package was required.

I learnt my lesson the hard way and introduce you to the best practices I follow when working with [npm packages](https://www.npmjs.com/), because Breaking Changes will arrive unannounced on a Red Carpet.

