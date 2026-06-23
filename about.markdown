---
layout: about
title: About
permalink: /about/
lang: en
---

In October 2025, Sky News published a political comment piece. Same news, different day. This one went viral. Why? Because of how modern devices notified readers of the headline.

<figure>
  <picture>
    <img src="/assets/img/screenshot-sm.webp" alt="A screenshot of an iOS notification for a Sky News headline where the word 'analyst' has been cut off to look like 'anal' causing an embarrassing shift in the meaning of the headline" />
  </picture>
  <figcaption><a href="https://news.sky.com/story/zack-polanski-and-nigel-farage-are-polar-opposites-in-politics-but-have-one-thing-in-common-13455371">Sky News Oct 2025</a>, screenshot via Reddit</figcaption>
</figure>

No human wrote this headline. It will have happened as the result of the text being truncated automatically by the device notification system.

What is truncation? It is a method for automatically cutting off content when doesn't fit into a layout container. Say you have a button element that can fit a maximum of 18 characters. If the button content is 25 characters, truncation cuts off the content at 17 characters, and then insets an ellipsis to show what has happened:

<figure>
  <picture>
    <source srcset="/assets/img/example-dark-xl.webp" media="(prefers-color-scheme: dark)" />
    <img src="/assets/img/example-light-xl.webp" alt="" />
  </picture>
  <figcaption>This is a hypothetical example, not an actual screenshot (with apologies to <a href="https://www.aaschool.ac.uk">the AA</a>)</figcaption>
</figure>

In a traditional media setting with strict layout rules (newspapers, television graphics and so on), subeditors would rewrite headlines to fit the available space. They would also do this without changing the intended meaning. (This is called overtyping and doing it quickly is a specialist skill.)

No human subeditor would have truncated the Sky News headline that way, but human subediting doesn't scale to an endless variation of digital devices. Truncation is a blunt force technical solution to deal with the need to display near-infinite content in an endless variety of interfaces.

---

## Safe Truncation Information

This website is a simple resource that lists common English words that risk being truncated into something embarrassing or potentially offensive. The list contains both the regular word and the undesirable truncated fragments with definitions for both (should you need them).

Using this list, it should be relatively straightforward for engineers to automatically parse a content string before and after truncation, identify any risk words, and catch problematic truncations before rendering.

The list is directly available in a [json file here](/en.json). 

It's a simple Jekyll build on Github Pages so it should be pretty stable.

---

## Constructing the list

The Safe Truncation list isn't quite a banned words list, plenty of those already exist. The issue with truncation is not that an offensive word slips through, its that the meaning of the content could be shifted in an embarrassing way.

With an example like [Polemic/Pole](/#Polemic) neither word is offensive in general context, but risks being truncated in unexpected ways:

<div class="comparison">
  <p><span>"Tristan loved nothing more</span> <span>than his professor's long polemics</span> <span>against the dangers of artificial</span> <span>intelligence."</span></p>
  <div>&rarr;</div>
  <p class="bad"><span>"Tristan loved nothing more</span> <span>than his professor's long pole&hellip;"</span></p>
</div>

Arguably as the subject of the content gets more serious, so do the implications of these errors. After all, everyone knows how much time academics spend on deep, penetrating analysis.

To help identifying context shifts using LLMs the list includes definitions for both the regular word and the undesirable truncated fragments.

---

## Languages other than English

I don't understand enough about sentence construction in languages other than English to know how widespread an issue truncation might be. I assume it isn't much of an issue with logographic languages like Chinese, but probably impacts compound-heavy languages such as German and Dutch.

Safe Truncation Information is designed to make adding additional languages simple. If you want to contribute (or if I've missed any English words) please do [get involved on Github](https://github.com/ThinkMake/safe.truncation.info).