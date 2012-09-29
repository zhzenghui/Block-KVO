Block KVO
=========

Overview
--------

**Key-Value observing made easier with blocks.**

This set of classes use the Objective-C KVO mechanism and allows you to use blocks as observation handlers.
Block KVO can be used and mixed with classic KVO without any problems.

You can check also “redesigned” version on separate branch. It is not properly tested, but it takes different approach and simplifies things even more.

Requirements
-------------
  - **iOS 4 and greater**
  - using source files: **ARC enabled**
  - using library: **`-ObjC` and `-all_load` as _Other Linker Flags_ in Build Settings**


Example
-------

  1. In `init`, `viewDidLoad` or similar method:
  
```objc
[self observe:@"view.backgroundColor"
    withBlock:^(UIColor *oldColor, UIColor *newColor) {
        NSLog(@"Background color of view changed from '%@' to '%@'.", oldColor, newColor);
}];
```

  2. In `dealloc` method:

```objc
[self removeAllBlockObservers];
````

Other methods in [`NSObject+MTKBlockObserving.h`](/blob/master/BlockObserving/NSObject%2BMTKBlockObserving.h) are for more advanced use, for example for observing collections/relationships or removing single block observers.

---------

**TODO:** Add documentation comments.
