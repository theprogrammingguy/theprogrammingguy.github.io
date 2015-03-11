---
layout: post
title: "Do it wrong!"
date: 2015-03-04 22:47:02 +0200
comments: true
categories: 
---

Hi there!

I've got a confession to make. I'm not a native English speaker. 

It may be obvious by the way I write. There might be a lot of mistakes in my writing, which I overlooked, although I'm really pedantic when it comes to revising my work before publishing.

<!-- more -->

Some mistakes are there because I just didn't notice them. Others are because I don't have enough knowledge or practice and couldn't spot them even if I was pointed on the sentences in which they occurs.

Frankly speaking, I'm not afraid of mistakes. And you shouldn't be too. They are an unavoidable aspect of learning process.

I've found recently that while doing my daily routine I have epiphany moments when I suddenly realise I've made a mistake in my English. These moments are usually happen when I see or hear the correct version of what I tried to say. Sometimes they happen without a reason.

Here is my point. If I hadn't done those mistakes, I wouldn't have had these moments of realization.

Obviously, you cannot choose between making or not making a mistake. However, you can choose between doing something wrong or not doing it at all.

My answer is **do it wrong!**

Of course, you don't want to put your money or reputation on that. Just make sure you won't suffer in case of a failure.

If you think your speaking skills are not good enough for public speaking, practice on your friend, cat, dog, favorite toy or even in front of your webcam.

If you want to create a good game, but don't feel confident in your skills, create a bad one! Create ten bad games! Create a worstest game ever! It will be an incredibly useful experience.

Remember, at some moments of your learning process it's more helpful to *start doing* than to *keep studying*.

That was a programming trivia for today.

#### Solution of the day

Write a program that answers YES/NO search queries containing \* placeholders.

Example: if the data you have is (hazem, ahmed, moustafa, fizo), then you should answer as follows for:

* ahmed: YES
* m\*\*stafa: YES
* fizoo: NO
* fizd: NO
* \*\*\*\*\*: YES
* \*\*\*\*: YES 
* \*\*: NO

Your program should be able to answer each search query in O(1)

``` java
public class PlaceholderSearchSet {
    private final Set<String> set = new HashSet<>();

    public void append(String word) {
        appendRecursively(word, 0);
    }

    private void appendRecursively(String word, int offset) {
        if (offset == word.length()) {
            set.add(word);
        } else {
            appendRecursively(word, offset + 1);
            appendRecursively(
                    replaceWithPlaceholder(word, offset), 
                    offset + 1);
        }
    }

    private String replaceWithPlaceholder(String word, int i) {
        return word.substring(0, i) + '*' + word.substring(i + 1);
    }

    public boolean contains(String word) {
        return set.contains(word);
    }
}
```

Today's **inspiration share** is ***On Writing*** book by *Stephen King*.

That’s all, folks! See you tomorrow! And remember: what is love? Programming is our true love!
