---
layout: post
title: Fetched Results
tags: [SwiftUI, core data]
---

Use `@FetchRequest` to get objects from your Core Data and store as a `FetchedResults` variable.

For example, get all objects of the entity `Category` and sort them by `order`, and store as the variable `categories`:

```javascript
@FetchRequest(
    entity: Category.entity(),
    sortDescriptors: [NSSortDescriptor(key: "order", ascending: true)]
)
var categories: FetchedResults<Category>
```

# `sortDescriptors`

## Multiple sort Descriptors
Sort descriptors will determine the order of the fetched results. You can have multiple sort descriptors, and they'll be applied in the order you list them.

```javascript
@FetchRequest(
    entity: Category.entity(),
    sortDescriptors: [NSSortDescriptor(key: "name", ascending: true), NSSortDescriptor(key: "order", ascending: true)]
)
var categories: FetchedResults<Category>
```

## Sorting Strings
To compare strings as case-insensitive, you need to specify the `selector`:

```javascript
@FetchRequest(
    entity: Category.entity(),
    sortDescriptors: [NSSortDescriptor(key: "name", ascending: true, selector: #selector(NSString.localizedStandardCompare))]
)
var categories: FetchedResults<Category>
```

# Filtering Results
You can filter which results you want by specifying the `predicate`:

```javascript
@FetchRequest(
    entity: Food.entity(),
    sortDescriptors: [NSSortDescriptor(key: "name", ascending: true, selector: #selector(NSString.localizedStandardCompare))]
    predicate: NSPredicate(format: "onGroceryList == true && checkedOff == true")
)
var checkedOffFoods: FetchedResults<Food>
```