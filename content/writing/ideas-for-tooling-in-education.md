+++ 
title = 'Ideas for Tooling in Education'
date = 2025-06-28
draft = true
+++ 

# Ideas for Tooling in Education

I've found that some of the most useful writing on AI is that of the kind that goes "Here's how I
use AI/LLMs/ChatGPT as an X" where X is usually a programmer or a researcher of some kind. Simon
Willison, for example, has a series called [How I use LLMs and ChatGPT](https://simonwillison.net/series/using-llms/)
that gives you a decent picture of where AI is actually useful, instead of having to take someone's
word for it.

Most of my AI use revolves around learning. Ever since these models started getting better at
reasoning and finding references, I've noticed that I tend to keep a tab open with a chatbot in it
as I'm ingesting new information. New tools for education seem to always be either overly-hyped by
early adopters or underappreciated by sceptics. I think that's a testament to how hard learning is:
most new technology is usually effective at getting learners excited/motivated to learn more about
something, but traditional tools -- like just reading a book, for example -- are still the most
effective ways to internalize new information.

## Why Learning is Hard

One of the reasons why teaching -- and presenting information in general -- is hard is that you're
often presenting information to different kinds of people with different backgrounds, different
amounts of context, and with varying levels of intelligence and comprehension. As an educator,
you're often explaining at a pace that is too slow for some, and too fast for others. At other
times, you're presenting information that is too deep for those who only want a shallow
understanding of the topic, or too brief for those who want to know the details.

This issue of pace is certainly more common in lectures and video materials than in text (i.e.,
textbooks, lecture notes, papers). Text allows the reader to consume the information at their own
pace. So, someone who has plenty of context regarding the material at hand might just skim through
the text. Whereas, someone who hasn't been familiarized with the terminology yet, or hasn't gone
through the necessary prerequisites to understand the material at hand, can read through the text
more slowly, possibly rereading multiple times.

The problem with traditional text formats regarding the former case is that the learner still has to
spend energy and time skimming through the text -- even if very little to no information is being
retrieved. In the process, the learner could miss important information that they would have wanted
to pay attention to otherwise. Skimming could also make the reader feel disengaged or bored.

The problem with the latter case (i.e., slowing down the pace or rereading when something is too
challenging) is that it doesn't always work. The alternatives in this case often are: (1) reading
something that's adjacent to what we're trying to learn, (2) reading a textbook on the same topic
that's less technical or easier to approach for our current level of understanding, (3) working
through exercises, or (4) changing the learning medium (e.g., going from text to video). After going
through some of these options, one could go back to tackling the topic at hand more prepared than
before.

LLMs offer something that's pretty tangible when it comes to solving this issue of pace and
verbosity in learning. The ability to go through some text, find something you don't quite
understand, and then have the LLM explain that for you is not only useful in the sense that you get
more information, but it also means that you now have a knob to control how much time and energy you
want to invest in one topic. You control the depth, verbosity, language, examples, and tone used to
explain a topic.

## Knobs for verbosity and depth

Future tools that aim to utilize AI for learning should try to offer high granularity when it comes
to controlling these knobs. With just these two variables -- verbosity and depth -- you get to
generate four kinds of text:

* **Low verbosity, low depth.** A quick and non-detailed explanation of something. Useful for those
  who don't want to invest a lot of time on the topic and don't care about the details.
* **Low verbosity, high depth.** A concise explanation of something. Useful for those that already have
  plenty of context about the topic at hand and prefer to get a compact explanation. Examples of
  this type of text would include research papers, mathematical proofs, definitions that rely on
  specific notation or symbolic language, and algorithms explain through pseudocode.
* **High verbosity, low depth.** A wordy explanation of something that's not packed with insightful
  information. Useful for those who want a gentle introduction to a topic, or for those who just
  enjoy reading. Examples could include self-help books, the [For Dummies](https://en.wikipedia.org/wiki/For_Dummies) 
  reference books, and introductory articles.  
* **High verbosity, high depth.** Lengthy explanation of something that's complex. Textbooks could
  be a good example of this category.

LLMs with high context windows have already gotten better at ingesting large amount of information
and summarizing it into fewer paragraphs [0]. Similarly, extracting more information from
tightly-packed sentences works pretty well too. You do this by picking a sentence that's too dense
-- or assumes prior knowledge which you don't have -- and then feeding it to an LLM to slowly build
up understanding, validating your understanding incrementally by asking questions and having the LLM
prompt you for answers.

## Personalized learning

Controlling verbosity and depth is already a form of personalized learning because you get to choose
the material which is attuned towards your intended time-investment and effort. But, LLMs can still
do better at personalizing the learning experience by allowing you to generate material that's
suited to your current level of understanding, learning style, and background.

You can decide if, instead of using fictional or over-simplified "textbook examples," you want to
read about actual real-world applications of the thing you're reading -- or you can do the opposite:
you may decide that you don't want to get bogged down into the implementation details of something
and ask for a simplified example, instead. 

You could use your current knowledge and prompt the LLM to find differences between the information
you currently have and the one you want to obtain. (This is why books like "Java for C++
programmers" exist, for example.) This makes it easier to form new connections, increasing the
likelihood that you remember the information at hand.

You can test your current understanding by posing a question which would showcase whether your
mental model is accurate. There's no societal pressure about being wrong. If your current
understanding is incorrect, you get to test it before building on top of a flawed mental model.

You should also be able to control the kinds of sources the LLM should ingest information from.
Filtering sources that you don't find to be trustworthy.

You can go from not understanding a sentence to gathering information incrementally by alternating
between the levels of depth to adapt to the level of effort that you're willing to put in to
internalize that information. 

This closely resembles having a personal tutor. You get many of the
benefits of having a real tutor (see [Bloom's 2 sigma problem](https://en.wikipedia.org/wiki/Bloom's_2_sigma_problem)), 
but this one has more energy and patience and won't judge you like a normal tutor would. The
downside being that LLMs cannot replicate the captivating energy of a really good tutor, nor can
they replicate a personality that has a consistent philosophy with strong opinions on certain
matters. They're often very dull so they're probably better off being used as tools for enhancing
learning rather than replacing conventional methods.

If you are interested to learn more about how we can use AI to improve education,
check out Andy Matuschak's [How might we learn?](https://andymatuschak.org/hmwl) presentation.
The process of learning something new is often too messy to fit into a well-organized flow. The
reason why Andy's work in this problem is compelling to me is that he's been able to pinpoint some
of the most common pain points in the learning process -- like the conflict between implicit and
guided learning, memory retention, social connection -- and has offered tractable solutions. 

There's a plethora of ["Cursor for X"](https://www.ycombinator.com/companies?query=cursor%20for) type of applications popping up everyday. Yet, I haven't seen
anything that compelling that integrates the current LLM capabilities with "the learning
experience." I think any solution offered in this area should also try to promote itself as a
another tool in the student's toolbox, rather than as a new experience that's going to revolutionize
or, even worse, replace traditional learning.

---

[0] What I'm talking about here is still normative: I would like for the depth and verbosity knobs
to be reliable, but that's not always the case. Some models are particularly verbose and instructing
them otherwise sometimes results in missing information, rather than conciseness. Another issue
where these models fail sometimes is when you want something very specific. Sometimes the amount of
effort it takes to get that specific thing often outweighs the effort that you would have otherwise
spent on just looking at a more comprehensive source of information like a book or a paper.

