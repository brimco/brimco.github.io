---
layout: post
title: Swipe Actions
tags: [SwiftUI, lists]
---

# Swipe Actions

Use swipe actions on lists to add buttons to either side.

```javascript
@State private var selection = 0

List {
    Text("Hello")
    .swipeActions(edge: .trailing) {
        Button(action: delete) {
            Image(systemName: "trash")
        }
        .tint(.red)
    }
}
```

Swipe actions are only available in iOS 15+, so you may need to check if available:

```javascript
List {
    if #available(iOS 15.0, *) {
        Text("Hello")
        .swipeActions(edge: .trailing) {
            Button(action: delete) {
                Image(systemName: "trash")
            }
            .tint(.red)
        }
    } else {
        Text("Hello")
    }
}
```
