---
title: A Misadventure at the AAA
tags:
  - Display Names
  - Best Practices
  - Software Testing
date: 2015-08-03 11:21:00
layout: layouts/post.njk
---

Today's bug in dealing with names and name changes was satisfying because it involved a display name field, in this case, the name on a membership card, so it flagged a case to look out for. 

For the past two months my wife Cynthia had been trying to update the name on my AAA membership card, she added me to her account back before my transition. Twice before she called member services, informed them of my name change, and a week later the new card would arrive in the mail with my old name on it.

This morning Cynthia said we were going to the AAA office to escalate. And Cynthia was ready to get in people's business about this. This is another reason why Cynthia is awesome.

Once we got in, the clerk looked up Cynthia's account and confirmed that my name was correct on. However, the field in which you set the name you want to have printed on your membership card still had my old name. She fixed the card name field, ordered a new card for me, and printed out a temporary membership card. We thanked her, giddy with the knowledge of a new thing to test for.

What I imagine was happening was when Cynthia added me to the account, a clerk filled in my old name into the first- and last-name fields, and the system copied the values into the name-on-card field. When Cynthia called member services to change my name, the edit to the first name didn't trigger an update to the name-on-card field, and the system generated a new card with the old name.

A test to verify correct behavior would look like:

<big><center>*If a field's value can be programmatically generated from other field values **or** overridden by user input, then whenever a field that the generated value  depends on changes, the value of the dependent field should update and the user asked to confirm the new generated value.*</center></big>

[Comment on this post at Dreamwidth](http://emceeaich.dreamwidth.org/177039.html).
