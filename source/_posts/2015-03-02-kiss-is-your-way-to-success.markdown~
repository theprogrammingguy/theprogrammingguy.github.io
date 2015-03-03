---
layout: post
title: "KISS is your way to success"
date: 2015-03-02 20:31:24 +0200
comments: true
categories: 
---

Want to write clean efficient code just like I do? Let me give you a KISS!

Don't be shy, come closer! I won't bite you.

The *KISS* stands for *"Keep It Simple, Stupid!"*

What it basically means is that while making your code flexible and extensible don't forget to make it simple.  

I'd been thinking for a while about how to find the perfect complexity of my code to make it useful not only for concrete practical purpose, but also to cover all its possible usages in case of reusing it later. So a was searching the point when code becomes *complete*. When there is nothing to add internally.

What I found was that there is an *unlimited amount* of ways to make your code more flexible by providing additional complexity. But that is not what you want to do. The thing is to make it useful enough you don't need to add anything, but also whittle it down so much you cannot cut it any more.
 
Eventually, simplicity is a good thing. It's a key property which all pieces of large systems must have to allows it to be maintainable.

You should always keep the KISS principle in your mind to become a successive programmer.

That was a programming trivia for today.

#### Solution of the day

Given a string containing letter, digit, and other characters, write a function to check palindrome for only letter and digit. The implementation need to be in-place, no extra memory is allowed to create another string or array. 

For example:  

* "ABA" is palindrome 
* "A!#A" is palindrome 
* "A man, a plan, a canal, Panama!" is palindrome

My solution is:

``` java
public static boolean isPalindrome(String s) {
    int i = 0;
    int j = s.length() - 1;
    while (i < j) {
        while (i < s.length() && !counted(s.charAt(i))) {
            i++;
        }
        while (j >= 0 && !counted(s.charAt(j))) {
            j--;
        }
        if (i >= s.length() || j < 0) {
            return false;
        }
        if (!areSame(s.charAt(i), s.charAt(j))) {
            return false;
        }
        i++;
        j--;
    }
    return true;
}

private static boolean counted(char ch) {
    char nc = normalize(ch);
    return nc >= 'a' && nc <= 'z' || nc >= '0' && nc <= '9';
}

private static boolean areSame(char ch1, char ch2) {
    return normalize(ch1) == normalize(ch2);
}

private static char normalize(char ch) {
    return Character.toLowerCase(ch);
}
```

#### Inspiration share

Today's winner in *inspiration share* nomination is ***Friends*** sitcom. Check it out!

That's all, folks! See you tomorrow! And remember: what is love? Programming is our true love!
