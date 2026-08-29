# Retrospective: FlyRank Internship

## To the person I was in Week 1

When I started this internship, I thought I understood backend engineering. I could build APIs, work with databases, and deploy basic applications. But I didn't yet understand what it meant to build software for the open internet, where you can't trust the input, you can't control the traffic, and you can't predict what will break next. That's what changed.

I also didn't understand what AI fluency meant beyond using a chatbot. I learned it's about knowing when to use AI, how to evaluate its output, and how to integrate it into real workflows, not just asking it to generate answers.

## What I set out to do

I set out to complete the Backend Track and build two capstones: an embeddable widget platform for lead capture, and an AI image understanding engine. I also completed the General AI Fluency track, building a personal portfolio with an AI agent and establishing reusable AI workflows.

## What actually changed

### The Widget Platform taught me about the open internet

In the widget capstone, I built a multi-tenant system where customers create embeddable widgets and install them with one `<script>` tag. The hard part wasn't building the form; it was handling CORS, rate limiting, spam protection, and geo enrichment with fallback chains.

**What I learned:**
- CORS debugging is a rite of passage. I spent an afternoon figuring it out, and now I check preflight headers by instinct.
- Rate limiting isn't optional; it's the boundary between your system and abuse.
- Fallback chains are how you survive production. When one geo provider failed, another took over.

### The Image Matching Engine taught me about AI reliability

In the image matching capstone, I built a system that uses Gemini Flash to tag images, generates embeddings, and matches images to blog posts with a mismatch guard.

**What I learned:**
- Structured output isn't optional. Without Zod validation, I would have blindly trusted whatever the model returned.
- Quota limits are real constraints. I hit Gemini's 20 requests/day quota, and it taught me batch discipline.
- The mismatch guard is the whole point. Knowing when to reject a match is more valuable than finding one.

### The AI Fluency capstone taught me about AI as a career partner

I built a portfolio with an AI chat agent, developed reusable AI workflows, and established a consistent personal brand.

**What I learned:**
- AI is most useful as a thinking partner, not a replacement for thinking.
- Good prompts provide context, constraints, and expected behavior, not just a question.
- AI agents should be intentionally constrained to their purpose.

## The moment I realized I'd changed

I caught myself doing something differently about halfway through the image matching capstone. I hit a bug: the JSON parsing was failing because Gemini was returning markdown fences around the JSON. My "old self" would have hacked a quick fix and moved on. Instead, I wrote a proper cleanup function, added error handling, and committed it with a clear message. The "old self" didn't think about cleanup functions; that's the shift.

## What I'd build next

If I had more time, I'd extend the widget platform with webhook delivery and a real-time dashboard. For the image engine, I'd add multiple model comparisons and automatic alt text generation. For the portfolio, I'd add conversation persistence and rate limiting to the chat agent.

## The three most transferable things I learned

### 1. Resilience isn't a feature; it's the product
A production system degrades gracefully: fallbacks, retries, and safe side effects. I built safe side effects in the widget platform and fallback chains in both capstones. That pattern applies everywhere.

### 2. Validate everything at the boundary
Never trust the client. Never trust the AI model. Never trust the database. In the widget platform, it was CORS and rate limiting. In the image engine, it was Zod schemas. In the portfolio agent, it was constraining the AI's scope. Same principle.

### 3. AI fluency is about judgment, not just usage
Knowing when to use AI, how to prompt it, how to evaluate its output, and how to integrate it responsibly matters more than knowing how to chat with it. I learned this across both tracks.

## What I'd tell my Week 1 self

"You're going to spend more time debugging CORS and rate limits than building features. And that's okay; that's the actual job. Also, start with 3 images, not 50. The quota will teach you patience. And don't just use AI; learn to work with it."

---

This internship gave me something I didn't have before: the confidence to build for the open internet and the judgment to use AI as a career partner. I don't just write endpoints anymore. I think about what happens when things go wrong. And I don't just ask AI for answers; I know how to prompt, evaluate, and integrate it responsibly.
