---
title: 'Getting the app to launch away from XCode'
description: 'Addressing issues that were preventing the app from launching when disconnected from XCode'
pubDate: '8/25/23'
---
I need to figure out a way to keep my API key and url "safe" in my source code. I was having an issue where when I would run the app on my phone without XCode, it wouldn't launch because I had saved the key and url in a plist file that I guess wasn't being built as part of the app bundle, so hardcoding it fixed it. I want to find a better solution though, even though hard coding an anonymous API key that can barely access anything (because of Row Level Security on the database) probably isn't the end of the world, it just doesn't _feel_ right.