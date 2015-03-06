---
layout: post
title: "Unavoidable mistakes"
date: 2015-03-05 21:39:54 +0200
comments: true
categories: 
---

Hello!

[Earlier][1] I mentioned two types of mistakes.

Some of them you do because of simple lack of knowledge. I [suggested][1] you not to worry about them.

Today I want to talk about second type of mistakes. You don't understand you've done them and they somehow stay invisible to you for a certain period of time.

Have you ever made such mistakes? You cannot figure out why your code doesn't work. It seems to be correct, but you keep getting an error. You try debugging it, but it appears to be the perfect time for debugger to start fooling around, so it refuses to see your breakpoints.

That drives you crazy. You spend plenty of time just to find you've done a really stupid mistake.

Does it sound familiar to you? Frankly, I made such mistake today.

These mistakes have an important property, which makes them different from the first type.

**They are unavoidable!**

It may or may not be obvious until you make it plain, but it's impossible to write code without bugs! Even carefully reviewing your changes won't help you much.

Are you still not convinced? Let me prove my point. Write a solution for the problem you can find further in this post. There is a single limitation: write it at once in a text editor without syntax highlighting and don't run it until you are sure you've finished. If your program works correctly without making changes, that will be something really impressive!

However, it's not about writing a bug-free code. It is about accepting the fact most of our newly written code contains mistakes and dealing with it. It's something that proves the necessity of unit testing and need of reviewing pieces of another's writing.

That was a programming trivia for today.

[1]: /blog/2015/03/04/do-it-wrong/

#### Solution of the day

Inplace reverse a sentence containing english words and spaces between them.

Example:

* input "I wish you a merry Christmas"
* output "Christmas merry a you wish I"

Constrains: O(1) additional memory

``` java
public static void inplaceReverse(char[] s) {
    reverse(s, 0, s.length);
    int lower = 0;
    for (int upper = 0; upper < s.length; upper++) {
        if (s[upper] == ' ') {
            reverse(s, lower, upper);
            lower = upper + 1;
        }
    }
    reverse(s, lower, s.length);
}

private static void reverse(char[] s, int lower, int upper) {
    int i = lower;
    int j = upper - 1;
    while (i < j) {
        char ch = s[i];
        s[i] = s[j];
        s[j] = ch;
        i++;
        j--;
    }
}
```

My **inspiration share** of today is ongoing ***Better Call Saul*** TV series. Check it out!

That’s all, folks! See you tomorrow! And remember: what is love? Programming is our true love!
