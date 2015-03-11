---
layout: post
title: "The law of the universe"
date: 2015-03-03 22:49:51 +0200
comments: true
---

Welcome back!

Remember the *Second Law of Thermodynamics?*

> The state of entropy of the entire universe, as a closed isolated system, will always increase over time.

<!-- more -->

*Entropy* is a measure of disorder. Imagine perfectly written code. All lines appears in their places. The arrangement is perfect. The entropy is incredibly low.

Now let's talk about program written by monkey. Well, code-monkey, if you wish. The program works somehow, but the code is such a mess it's a miracle it even compiles. You would never agree to add changes to this code. It will explode!

As you can tell, that was an example of a code with high entropy.

So how should we understand the law? What it means is each time you add new features to your project, the source code becomes more messed up *unless* you make an ***extra effort*** to [keep it simple][KISS].

It's true! That's why we need to review our code on a regular basis, find better approaches to do what we've done, refactor, improve it.

After all, if the entire universe obeys the law, why your code shouldn't?

Are you confused about me telling you to reduce the entropy of your code while the law says it's impossible? It would be impossible if your code was a *closed isolated system*. Here is the thing -- when you put an effort into cleaning your code, the entropy of the universe increases more than entropy of your code decreases.

If you want to learn more about laws of the universe, I suggest you to read ***A Brief History of Time*** by *Stephen Hawking* -- the **inspiration share** of today.

That was a programming trivia for today.

#### Solution of the day

You are given an unsorted sequence of integers 'a'. Find the longest subsequence 'b' such that elements of this subsequence are strictly increasing numbers. Elements in the subsequence 'b' must appear in the same relative order as in the sequence 'a'. You may assume that 'a' can fit to the memory.

Example:

* input: a = [-1 2 100 100 101 3 4 5 -7]
* output: b = [-1 2 3 4 5]

``` java
public static int[] longestIncreasingSubsequence(int[] a) {
    int[] dp = new int[a.length];
    int[] h = new int[a.length];
    int max = 0;
    for (int i = 0; i < a.length; i++) {
        dp[i] = 1;
        h[i] = -1;
        for (int j = 0; j < i; j++) {
            if (a[i] > a[j] && dp[j] + 1 > dp[i]) {
                dp[i] = dp[j] + 1;
                h[i] = j;
                if (dp[i] > dp[max]) {
                    max = i;
                }
            }
        }
    }
    int[] b = new int[dp[max]];
    while (max >= 0) {
        b[dp[max] - 1] = a[max];
        max = h[max];
    }
    return b;
}
```

Time complexity is O(N ^ 2).

Wait a minute. Are you saying there is a faster solution? Let's see...

``` java
public static int[] longestIncreasingSubsequence(int[] a) {
    int[] dp = new int[a.length];
    int[] h = new int[a.length];
    int[] c = new int[a.length];
    Arrays.fill(c, -1);
    int max = 0;
    for (int i = 0; i < a.length; i++) {
        dp[i] = 1;
        int l = 0;
        int r = i - 1;
        while (l <= r) {
            int m = (l + r) / 2;
            if (c[m] >= 0 && a[c[m]] < a[i]) {
                l = m + 1;
            } else {
                r = m - 1;
            }
        }
        int k = (r >= 0) ? c[r] : -1;
        h[i] = k;
        if (k >= 0) {
            dp[i] = dp[k] + 1;
            if (c[dp[k]] < 0 || a[i] < a[c[dp[k]]]) {
                c[dp[k]] = i;
            }
            if (dp[i] > dp[max]) {
                max = i;
            }
        } else if (c[0] < 0 || a[i] < a[c[0]]) {
            c[0] = i;
        }
    }
    int[] b = new int[dp[max]];
    while (max >= 0) {
        b[dp[max] - 1] = a[max];
        max = h[max];
    }
    return b;
}
```

How about that? Time complexity is now O(N log N). However, it's too hard to understand now.

That’s all, folks! See you tomorrow! And remember: what is love? Programming is our true love!

[KISS]: /blog/2015/03/02/kiss-is-your-way-to-success/ 
