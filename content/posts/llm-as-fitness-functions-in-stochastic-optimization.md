---
date: '2025-01-22'
title: 'LLMs as Fitness Functions in Stochastic Optimization'
---

The hard part of stochastic optimization is the evaluation function.

You get whatever you're optimizing-for or toward and it's always a trade-off, even if you can't see it at first.

This got me thinking, there must be tons of problems that we cannot optimize easily because we don't have good (cheap) fitness functions where we could use an LLM to step in.

I know I've read papers on something like this in the openendedness literature.

Maybe this was it:

* [Quality-Diversity through AI Feedback](https://arxiv.org/abs/2310.13032), 2023. ([more here](https://qdaif.github.io/))

> ... we introduce Quality-Diversity through AI Feedback (QDAIF), wherein an evolutionary algorithm applies LMs to both generate variation and evaluate the quality and diversity of candidate text.

Nice, so an LLM (or LM) for both fitness evaluation of "quality" and as a mutation operator.

If there's one paper, I'm sure there are many more on this intersection. Good.

Let's see what our friend gpt4o has to say about the impactful opportunities of using LLMs as fitness functions:

(edited for interestingness by me)

---

Here are some interesting and impactful problems that could be explored using stochastic optimization algorithms with an LLM fitness function:

### Textual Problems
- **Creative Writing Optimization**:
  - Generating poetry, stories, or screenplays optimized for style, emotion, or target audience engagement.
  - Crafting marketing slogans or product descriptions for maximum appeal and clarity.

- **Question Generation**:
  - Designing educational questions tailored to specific difficulty levels or topics.
  - Optimizing interview questions for specific roles or competencies.

- **Text Simplification**:
  - Rewriting technical documents or legal text for better accessibility to laypersons.
  - Translating complex scientific articles into more engaging summaries.

- **Dialogue Systems**:
  - Creating chatbot responses that maximize user satisfaction or minimize confusion.
  - Tuning AI-generated therapy or counseling conversations for emotional resonance and effectiveness.

- **Content Summarization**:
  - Generating concise, highly-informative summaries optimized for specific audiences.
  - Producing multi-level summaries for layered understanding (e.g., abstract → paragraph → detailed).

### Image/Text Problems
- **Ad Copy and Visual Pairing**:
  - Designing combinations of text and images for advertisements to maximize click-through rates or brand alignment.
  - Optimizing infographics for readability and informational clarity.

- **Artistic Creation**:
  - Generating visual designs (e.g., logos, illustrations) optimized for artistic style or adherence to a theme based on textual prompts.
  - Creating memes optimized for humor, virality, or cultural relevance.

- **Visual Storytelling**:
  - Pairing images with captions to tell compelling stories or convey emotions effectively.
  - Creating engaging storyboards for animations or videos.

### Interactive Problems
- **Game Design**:
  - Balancing game mechanics for maximum engagement or fairness using LLMs as proxies for player feedback.
  - Designing puzzles or levels optimized for difficulty and enjoyment.

- **Personalized Education**:
  - Tuning learning materials (text, quizzes, exercises) to individual learners' levels and interests.
  - Crafting personalized feedback or coaching strategies.

- **Product Reviews and Recommendations**:
  - Designing review prompts that maximize the quality and informativeness of user feedback.
  - Optimizing recommendation systems to predict human-like preferences more accurately.

### Multimodal Challenges
- **Brand Identity Optimization**:
  - Designing logos, taglines, and narratives that align with a company’s core values and target demographics.

- **Campaign Design**:
  - Creating political or social awareness campaigns that maximize emotional resonance and call-to-action responses.

- **Cross-Cultural Content Creation**:
  - Adapting content (text or images) for cultural sensitivities while retaining meaning and appeal.

### Real-World Applications
- **Urban Planning**:
  - Optimizing public communication documents (e.g., urban development proposals) for clarity and buy-in from stakeholders.

- **Healthcare Communication**:
  - Generating patient communication materials optimized for understanding and reassurance.

- **Policy Drafting**:
  - Refining legal or policy documents for clarity, brevity, and alignment with societal values.


These problems leverage the natural language understanding, creative capacity, and human-like evaluative abilities of LLMs to serve as sophisticated fitness functions, potentially reducing reliance on expensive or subjective human evaluations.

---


Fine. Boring.

I can see that the majority assume a generative model as creating candidate solutions and an LLM interpreting/evaluating candidate solutions.

I like the iterative/recursive nature of the approach. It might lead somewhere interesting for some problems.

I like the opportunity to use an ensemble of "experts" in evaluation and go for a pareto front/multi-objective optimization across experts. More interesting.

What about where we only use LLMs for candidate solution eval?

Again, from our LLM friend:

---
Here are **10 impactful problems** where LLMs are used purely as evaluators (fitness functions) for candidate solutions, while the candidates themselves are generated by other means:

### 1. **Product Design Feedback**
- Evaluate candidate product designs (e.g., written specifications or descriptions) based on user-centric criteria such as clarity, market appeal, or alignment with customer needs.

### 2. **Curriculum Optimization**
- Assess different configurations of educational content or lesson plans for engagement, clarity, and progression suitability for specific age groups or audiences.

### 3. **User Experience (UX) Text Evaluation**
- Rank or score candidate user interface texts (e.g., tooltips, error messages, help guides) for clarity, friendliness, and effectiveness in guiding the user.

### 4. **Legal Contract Simplification**
- Evaluate multiple simplified versions of legal or technical contracts for readability and retention of critical legal nuances.

### 5. **Brand Voice Alignment**
- Score candidate marketing copy or communication drafts for alignment with a brand’s tone, values, and voice.

### 6. **Moral and Ethical AI Decisions**
- Assess various AI decision-making models (e.g., in ethical dilemmas) for their alignment with pre-defined human ethics or moral guidelines.

### 7. **Science Communication**
- Evaluate candidate layperson summaries of complex scientific articles for balance between simplicity and accuracy.

### 8. **Customer Support Responses**
- Rank candidate responses to customer queries for helpfulness, empathy, and adherence to organizational standards.

### 9. **Job Application Filtering**
- Evaluate resumes, cover letters, or portfolios based on how well they align with a predefined job description or competency model.

### 10. **Policy Proposal Evaluation**
- Assess candidate policy drafts for their persuasiveness, logical coherence, and alignment with societal or stakeholder priorities.

In each case, LLMs act purely as evaluators, making it easier to select the most promising solutions among many generated via alternative methods such as human input, rule-based systems, or other AI tools.

---


Huh.

I don't like any of these for stochastic optimization.

They do spark ideas though. In-house services that sanity check copy/products before they go out to make sure they fit with organizational objectives.

Agent's as evals on human output.

Okay, good stuff.

