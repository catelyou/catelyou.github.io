---
layout: post
title:      "OO Counting Sentences Lab: Crowd Sourcing Solutions"
date:       2019-08-03 19:05:08 +0000
permalink:  oo_counting_sentences_lab_crowd_sourcing_solutions
---

I'm quickly learning that your success as a developer relies not only on your skills and knowledge, but also on your ability to Google your way out of a problem. I'm no stranger to getting stuck on a lab but the OO Counting Sentences Lab was a perfect example of how I crowd sourced possible techniques in order to get a solution.

As a refresher, the purpose of the OO Counting Strings Lab is to write a code that will count the number of sentences in a given string. First, in my notebook, I defined a sentence by a string of words that ended in "!", ".", or "?" understanding that sentences could end in any combination as complex sentences. For example, "..." or "!!" or "??"

Then, as I've learned going through this program, I opened the last several lessons in tabs to use as resources including a topic that I stumble through frequently: RegEx. I knew that I had to count patterns and I also knew that RegEx could be a baseline for solving this problem.


So, based on the lab breakdown, I knew I had to use .split and .count as a part of my count_sentences method. Combining this knowledge with RegEx, I wrote:

```
def count_sentences
   self.split(/[.|?|!]/).count
end
```

However, the above code does not return complex sentences. How can I account for those numbers? Ugh. Stuck.

After some Googling, I came across a blog post that addressed the same issue: How do we count complex sentences? The blog mentioned .squeeze could do the trick. The squeeze method eliminates duplicate characters by replacing the duplicates with a single character(!! > !). The author outlined their code as 

```
def count_sentences 
   string = self.squeeze(”.”) 
	 string = string.squeeze(”!”) 
	 string.split(/[$.|?|!]/).count 
end
```

While passing, the above code does not account for all sentence punctuations. To accommodate for this, I rewrote the above code to:

```
def count_sentences
    self.squeeze.split(/[.|?|!]/).count
end
```

The above eliminates the duplicate characters while counting all the punctuations - getting my code to pass!

While this code got me through this lesson, I have to recognize the limitations it presents overall. The squeeze method does not account for complex sentences that end in combinations of different punctuations. For example, my test would not pass if one of the complex senteces ended in "?!".


