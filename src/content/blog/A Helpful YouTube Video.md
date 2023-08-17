---
title: 'A Helpful Youtube Video'
description: ''
pubDate: '8/16/2023'
---
I found a [YouTube video](https://youtu.be/QJHmhLGv-_0) that's been really helpful. It covers some of the basics of using XCode to set up an iOS app with a Firebase backend. For my particular implementation, I'll be using Supabase because I want to try it out. But nonetheless, a very helpful start to understanding the structure of an iOS app. 

This time, Swift is confusing me by having multiple curly brace sets after a single UI View is called. 

```Swift
Button {
	//action
} label: {
	//Contents of the button label
}
```

I don't think I've really seen syntax like this. I guess it takes curly brace blocks as parameters and the first one is whatever the default parameter is of the View (action in this case). Then the second curly brace block acts as another argument to the labeled parameter `label:` which in this case I guess takes a curly brace block as an argument.

### I got the basic authentication working

Then all the `if let ... {} else {}` stuff broke me. I'm trying to store extra user data within the metadata field in the `users` table in Supabase, I don't think Swift likes that the value of the JSON stuff can kind of be anything. I could make a separate table to store user metadata. Actually, I'll probably have to anyway. Eh, I'll do it tomorrow, it's already 12:30 am.