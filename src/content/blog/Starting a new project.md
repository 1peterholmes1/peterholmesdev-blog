---
title: 'Starting a New Project'
description: ''
pubDate: '8/11/2023'
---

I decided that I want to learn iOS app development. 
So, last night I opened XCode for the first time (intentionally). I want to go from my current understanding of frontend development to iOS development to build my app for native iOS using Supabase as a backend. 
I also decided that I want to post blog entries on my website to keep myself honest about keeping up development. I don't really think anyone will find or read these. I'm mostly posting them for myself, to be able to track my progress. And hopefully if I solve some issue I've been having, I can either help other people, or even just help myself once I've no doubt forgotten how to do something. 

## My first step was trying to understand the Swift language. 

My background is mostly in C/C++ and Java from school, Python from personal projects, and most recently JS/TS from full stack web (mostly with various frontend framework flavors like JSX/TSX or Vue/Svelte/Astro).

Swift was a bit of familiar, with a whole lot of new. As people have said, Swift is a very opinionated language. The first step was getting used to the syntax and things like parameter labels. At first, I thought parameter labels were kind of redundant and requiring every parameter to be passed after its `name: ` felt super repetitive. But it grew on me a little bit. It definitely makes more sense for functions with a ton of optional parameters. I started to think about it like passing an object to a function in JS, but without the curly braces.

```
JS: const res = someFunc({param1: 1, param2: "abc"})
Swift: let res = someFunc(param1: 1, param2: "abc")
```

Another thing that took me a bit to work through was my muscle memory of declaring every variable with `let` or `const` instead of `var`. I'll eventually work through that.
I do like the type declarations as someone coming from Typescript, but I could imagine someone coming from a pure C/C++ or Java background being confused for a bit.

#### As it stands now, about 4 hours of work after I opened XCode, there are still some things that confuse me:

When I tried to use a ForEach loop in a LazyHStack (per the SwiftUI documentation), apparently I need to include a variable declaration after the opening curly brace in a form of syntax I have never seen before (idk if this is similar to an Objective-C thing, I've never used it)

```
// This is the strangest syntax ↓ that I've seen ... so far
ForEach(1...18, id: \.self) { index in 
	SomeView(param: index)
}
```

This was the syntax that broke me. It made me swallow my pride and start the basic Swift Codecademy course to just have the most basic syntax drilled into my brain.

## Things that I solved that I might want to refer to later

After creating the project, I changed the package name in the project settings, and I don't think it fully signed me into iCloud for some reason.
As a result, when using the default files that come with a standard new iOS project, it worked fine. The preview was updating and I was starting to put together a basic view. However, when I tried to add a file to use a nested view, or even just a TabView with multiple views above, the preview started breaking. All it took was adding a file to the project and it stopped showing the preview and gave an error message with a huge long file path that ended in `....preview-thunk.dylib`. Eventually I found a stackoverflow answer that said it could be an issue with codesigning.
Solution: \[XCode 14.2] In Preferences/Accounts: I removed my iCloud account and re-added it. Then, on the project page (click at the top level App name in the sidebar with the icon similar to the iOS App Store) I changed the Bundle Identifier in the "Signing & Capabilities" tab back to what it was when I went through the initial wizard. To be safe, I unchecked "Automatically manage signing" and rechecked it, then selected my Personal Team in the "Team" Dropdown.
That seemed to fix it.