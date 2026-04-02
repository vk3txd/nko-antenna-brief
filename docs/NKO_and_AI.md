# NKO antenn and the use of AI

I don't know of any other HF antenna aimed at the Amateur Radio community that has been so heavily influenced by AI.

This is the story of how it came about, and what human and AI interaction brought.

---

## In The Beginning

In September 2025 I used AI for the first time. ChatGPT. I'd never used AI previously and was both interested yet sceptical that it could aid me much.

So I asked it to analyse the New Carolina Windom. It waxed lyrical about the virtues of the vertical coax radiating and how this benefited. I got quite excited!

It all went downhill from there when I asked it about how much current was on the vertical coax, how it was generated (where it came from) and what benefit it actually brought. AI got all "hand wavy" and wishy washy.

We argued, me and the rusty box of chips, and it became clear that the New Carolina Windom while being an innovation and a good idea, was perhaps not as good as it could be.

AI made the comment, "to make the vertical radiator effective it needs to have substantial current on it" which is really quite simple yet at the same time led me to ask myself, "how can I get more current on the vertical coax?"

I then suggested an UnUn. Simple as that. The UnUn shares a terminal with an antenna arm - you can't get a stronger current flow on the coax shield than a direct connection - and the NKO was born.

Note. AI did not do the innovation and in nearly 6 months of use, I have found this to be the case. It is not, or rarely, innovative.

---

## How AI Benefited Me

AI can search the internet, collect and collate information, and then present results vastly quicker than any human. This alone makes it very valuable as a research tool.

This is a huge help in analysing a situation, searching forums for user experiences and problems, and considering options. It can then use this in an analysis which is a huge help.

It can present information from this research in helpful ways also. For example, I fed in audio clips and had it use DSP to analyse speech frequencies to determine if NKO does indeed change the way an antenna 'hears' signals (it does). I could have done it myself, but it would have been a research project in its own right.

AI can use first principles in an analysis and produce a result that is remarkable. I can instruct it to change parameters, then it will re-evaluate. The down side is that it can use the wrong formula, use incorrect values and make vastly wrong assumptions. For example it has used the full wavelength value for a half wave antenna, used the wrong weight of ferrite in an efficiency calculation.

This all comes at a cost, and the cost is being overly reliant and accepting quite often clearly wrong information.

Most importantly I found that AI presents information it generates so well, so plausibly, that even the most profoundly wrong information still looks good!

The benefit behind this is that it builds a reluctance to accept AI informaiton without some kind of verification, and in doing that I learn more.

AI has helped me learn.

---

## AI Shortcomings

In the early days, AI asked questions, or it's analysis led me to question it. One day I happily remember successfully challenging Grok-AI 4 times in an hour and calling out flawed results.

As a simple test; ask the AI of your choice how using a 4:1 UnUn with an OCF antenna arms will perform. Almost universally it will complain about common mode current and raise issues and strongly suggest a 4:1 current balun is best. Then ask it about how a balun deals with imbalanced impedances of the OCF arms and query its assumptions. Challenge its 'beliefs' and criticise assumptions. Then give it a link to this GitHub repo - and it all changes. Then 'sycophancy' kicks in and it praises the concept.

This made me highly sceptical of AI. At the same time it made me keenly aware that results can be skewed by human input.

An example. AI was analysing ground interaction with the vertical radiating coax and treating it as a vertical monopole. All good and sounds sensible. So I suggested that the highest current is at the apex, high in the air where the coax shield connects to the antenna arm. This radiating section is more like an upside down monopole. AI then changed its analysis significantly. It had not taken into account the struture of the antenna properly. Yet we had 4 months or more of history on exactly this.

This is a significant failing. It was myopic in its analysys despite being hugely involved in the project for months.

I queried AI on this specifically. It said;
- AI tends to prefer known models using existing scenarios and do analysis using them, instead of a new innovation. It _assumed_ using a ground mounted vertical antenna.
- It likes to generalize rather than use something specific (like an innovation)
- It needs to be forced to use specific cases. A human _must not_ assume the AI is using the correct assumptions.

Reinforcing; query the assumptions that AI uses. In my example "It reaches for a standard antenna archetype before analysing the actual current distribution." AI said that.

AI also tends to make statements that look really clever and analytical, yet they are a complete fabrication. For example it suggested a 3dB improvement with a change of soil type. I showed this analysis to a 2nd AI which called this out strongly.

## Lessons Learned

There are a number;
- Knowing the answer first is ideal, or at least having some ideas about the shape of an answer helps. This way AI results divert from that can raise more questions
- Be careful that AI actually uses the correct parameters / equations / structures / factors that are in play
- Ask what assumptions have been used
- Use AI to get corroboration - cross check
- Be critical.






