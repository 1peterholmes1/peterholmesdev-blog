---
title: 'Optional? More like obligatory'
description: ''
pubDate: '8/17/2023'
---
Wow, when I heard that Swift was an "opinionated" language, I thought that wouldn't be too different from the boilerplate that I'm used to from Java. Or that it could be similar to how finicky pointers and memory management is in C++ and C respectively. But wow, I've been trying to debug a Supabase database response for a long time now and when I finally found a [GitHub Issue](https://github.com/supabase-community/supabase-swift/issues/95#issuecomment-1635780910) that mentioned a similar issue that I was facing, I realized I was nowhere near solving it myself. 

I guess I should have expected being surprised by how opinionated Swift was, especially coming from JavaScript (literally the most un-opinionated language there is). 

To that end, I actually tested a Supabase endpoint using the Python library to make sure that _something_ was being returned. 

What ended up solving the issue I was facing, was actually casting the response to a class that I made that inherited `Encodable` and `Decodable`. And also marking that response as optional. In other words, simply putting a question mark ("?" for those still confused) after the type cast of the response, in other words:
```Swift
if let response: [CodableClassThatIMade]? = try await client.database....
```
To be fair, I was also expecting that using print statements (or `console.log` as I'm used to) will display pretty much any object passed to them. In Swift, or at least XCode, that doesn't seem to be the case, more akin to \[object Object]. Once I was able to print that the count of the returning array was greater than 0, I'm confident that I figured out the issue I was having. 

I feel like `guard let` and `if let` and some of the optional stuff is ultimately just going to be part of the Swift language that I never truly end up internalizing. Similar to how I currently understand `async await` in JS (after about 3 months of using it). I get it at the base level, and enough to use it. But I honestly don't know how much of my time it's worth to get deep into the weeds on this. 