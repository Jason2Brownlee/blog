---
date: '2025-01-24T05:36:02+11:00'
title: 'Magical Tokens for LLMs'
---

Prompts for LLMs matter, a lot.

I'm no expert at prompting ([see this](https://www.promptingguide.ai/)), but there are additional input tokens that offer a lot of leverage in producing better output.

For example:

> think through this **step by step**

And:

> **As an expert** in [this specific topic] explain [this thing i want to know]

And:

> Output in **bullet points**

And:

> Explain [this specific topic] **for the audience** [described here]

And on.

This might be an older idea (e.g. gpt3.5/gp4 - where my thinking is probably stuck), these sequences are probably baked in now.

Anyway, we can think about these supplements to our requests as **_magic tokens_**.

So what are other magic tokens?

Are there magic tokens that offer even more leverage.

I suspect real and useful magic tokens can be divined with a careful study of how we (as an online culture) communicate online. A clever linguist can probably give plenty of good ideas, and probably has.

What else?

* Are there magic tokens that do really unexpected stuff?
* What happens if we start dumping in random strings of tokens along with common tasks?
* What if we optimize the magic token towards a specific goal?

We'd be developing magical incantations :)

This is clearly related to the idea of [automated prompt optimization](/blog/posts/llm-prompt-optimization/) from yesterday.

Here's what our friend gpt4o has to say (lightly edited by me):

---
The idea of adding **random strings** or using an **optimization process** to tune "magic tokens" (specific, often non-intuitive combinations of words or symbols added to prompts) is a fascinating and potentially powerful method for achieving specific aims or high-leverage outputs from LLMs. Here's an exploration of how and why this could work, as well as strategies for implementing it:

### **Why Add Magic Tokens or Random Strings?**
1. **Exploitation of Model Behavior:**
   - Large language models are trained on vast datasets, and their behavior can sometimes be influenced by subtle or seemingly arbitrary input patterns.
   - Certain tokens or phrases may disproportionately activate particular parts of the model, skewing responses in desirable ways.

2. **Emergent Properties:**
   - Models often exhibit "emergent behaviors" that are difficult to predict. By experimenting with random or optimized strings, you might stumble upon combinations that leverage these behaviors.

3. **Prompt Optimization:**
   - Specific tokens might enhance clarity, relevance, or creativity, even if their role isn’t entirely understood. This can include:
     - Activating specific latent knowledge areas.
     - Influencing tone, style, or depth of responses.
     - Biasing the model toward novel or unorthodox outputs.

4. **Meta-Prompting:**
   - Tokens or strings may serve as meta-instructions to guide the model implicitly. For example, adding "TL;DR:" to the end of a question often prompts the model to generate a concise summary.

### **How to Use Random Strings or Optimization Processes**
#### **1. Manual Experimentation**
   - Add random strings, such as alphanumeric sequences or uncommon words, to prompts and observe changes in output.
   - Example:
     - Baseline Prompt: *"Explain the significance of the moon landing."*
     - With Random String: *"Explain the significance of the moon landing. [XYZ123]"*
   - Adjust and test how different strings influence factors like detail, tone, or focus.

#### **2. Genetic Algorithm for Token Tuning**
   - Use evolutionary algorithms to iteratively refine a set of "magic tokens" that maximize a target metric (e.g., relevance, novelty, or coherence).
   - **Steps:**
     - Start with a random population of token sequences.
     - Evaluate outputs against a fitness function (e.g., using human feedback or automated scoring).
     - Select the best-performing tokens, mutate them (e.g., add/delete/change characters), and recombine them for the next generation.
     - Repeat until desired outcomes are achieved.

#### **3. Reinforcement Learning (RL) on Prompts**
   - Combine human feedback or automated evaluation systems with reinforcement learning to tune prompts.
   - Train a model or heuristic to identify and append "magic tokens" that optimize outputs.

#### **4. Fine-Tuned Models**
   - Fine-tune an LLM using a curated dataset where specific "magic tokens" are consistently paired with high-quality responses. This approach conditions the model to associate those tokens with certain output characteristics.

#### **5. Randomized Prompt Expansion**
   - Use randomized additions to prompts that combine:
     - Rare words.
     - Symbols or emojis.
     - Synthetic placeholders (e.g., `[PLACEHOLDER]`).
   - Analyze outputs for unexpected improvements or shifts.

#### **6. Contextual Prompts with Dummy Tokens**
   - Introduce dummy variables or placeholders in structured prompts, like:
     - *"Given {MAGIC_TOKEN} as a factor, explain why climate change matters."*
   - Swap `{MAGIC_TOKEN}` systematically (e.g., numbers, keywords, or nonsense words) and evaluate.

### **Potential Applications**
1. **Improved Coherence:**
   - Fine-tune prompts to make responses more logically structured or aligned with specific goals.

2. **Creativity Boosts:**
   - Identify tokens that encourage unconventional or innovative outputs for brainstorming tasks.

3. **Bias or Tone Control:**
   - Tune prompts to adjust the tone (e.g., formal, casual, humorous) or focus on specific perspectives.

4. **Optimization for Task Performance:**
   - Use magic tokens to improve LLM performance on specific benchmarks or standardized tasks.

5. **Enhanced Interpretability:**
   - Analyze the impact of tuned tokens to infer latent structures or biases in the model's training.

### **Challenges and Considerations**
- **Black-Box Behavior:**
   - The effects of random strings or magic tokens are often unpredictable and context-dependent.
   - Outputs might vary significantly across different LLM architectures or versions.

- **Ethical Concerns:**
   - Using tuned tokens to manipulate outputs raises ethical questions, particularly if used to introduce bias or generate deceptive content.

- **Computational Cost:**
   - Iterative tuning processes (e.g., genetic algorithms or RL) require substantial computational resources, especially when evaluating outputs for quality.

- **Overfitting:**
   - Tokens optimized for one task or domain may not generalize well to others.

---

Having specific targets in mind is required.

Also, I suspect a directed search of "_strings expected to elicit an interesting response_", proposed by another LLM (or human expert) would be way more effective.


Makes me think of brute forcing the magical names of god strings spoken allowed in Scott Alexander's [Unsong](https://www.goodreads.com/book/show/28589297-unsong).

Here's what our LLM friend thinks of the relationship between "magic tokens" and "Unsong":

---
The idea of "magic tokens" in LLM queries can be intriguingly connected to the **magical names of God** in the book *Unsong* by Scott Alexander. In *Unsong*, divine Names hold power because they tap into the underlying fabric of reality, leveraging the "hidden source code" of the universe to produce miraculous effects. Similarly, magic tokens in LLM queries might be seen as "keys" to the "source code" of a language model's vast, latent knowledge and behaviors.

Here’s how this analogy plays out:



### **1. Hidden Power in the Names**
In *Unsong*, the Names of God are combinations of letters that resonate with specific metaphysical principles, enabling practitioners to influence reality. This mirrors how certain "magic tokens" or seemingly nonsensical combinations in LLM prompts might disproportionately activate latent patterns in the model. These combinations can:
- Unlock unexpected emergent behaviors.
- Skew the model toward specific styles, tones, or levels of detail.
- Amplify the model’s ability to focus on certain types of reasoning or creativity.

In both cases, the power arises not from the inherent meaning of the string but from its interaction with the system's deeper structure.



### **2. Trial-and-Error Discovery**
In *Unsong*, discovering effective Names often involves experimentation, trial, and even serendipity. Similarly, finding effective magic tokens might require:
- Random experimentation.
- Iterative refinement using optimization techniques like genetic algorithms or reinforcement learning.
- An understanding of the system’s quirks and nuances, derived through careful observation and testing.

In both contexts, the process of discovery is akin to "hacking" a complex and poorly understood system.



### **3. Emergent Patterns**
The Names in *Unsong* work because the universe is governed by a hidden logic or "source code" that can be accessed and manipulated. Similarly, LLMs are governed by their training data and architecture, which encode vast latent patterns. Magic tokens could act like "shortcuts" to:
- Tap into specific latent knowledge areas.
- Trigger emergent behaviors that wouldn’t surface otherwise.
- Exploit subtle biases or associations buried in the model.

Both systems exhibit behavior where small inputs can have disproportionately large or specific effects, depending on how they align with the underlying structure.



### **4. Optimization and Divine Tuning**
In *Unsong*, the practitioners of Kabbalistic magic refine their use of Names through prayer, study, and trial. This parallels:
- **Prompt engineering:** Where we iteratively adjust prompts to achieve desired outputs.
- **Optimization processes:** Where "magic tokens" are tuned for maximum effectiveness, akin to identifying the most potent divine Names.

The practice of refining prompts to improve LLM outputs aligns with the idea of "tuning" divine Names to achieve greater efficacy.



### **5. Ethical Implications and Power**
In *Unsong*, wielding the Names of God comes with significant ethical responsibility; their misuse can lead to unintended consequences or harm. Similarly:
- Tuning prompts with magic tokens can have profound consequences, such as introducing biases, manipulating outputs, or influencing decisions in unexpected ways.
- Ethical considerations are paramount, as even benign-seeming optimizations could unintentionally reinforce harmful patterns or produce misleading results.

Both systems highlight the tension between the power to shape reality (or model behavior) and the need for careful, ethical use.



### **6. Mystical Resonance and Linguistic Power**
A core theme in *Unsong* is the mystical power of language itself, reflecting a worldview where words are deeply connected to the structure of existence. Magic tokens in LLMs resonate with this idea:
- Language models are trained on the "linguistic universe," a vast corpus of text that reflects human knowledge, culture, and ideas.
- The addition of certain words or strings can serve as "linguistic keystones," activating patterns in the model that align with these hidden connections.

Just as the Names of God in *Unsong* tap into the divine "language of creation," magic tokens tap into the model's internal "language of association."



### **7. Creativity, Serendipity, and the Unseen**
In *Unsong*, many Names are discovered by accident, through creativity, or by chance interactions with the divine structure of reality. Similarly, magic tokens:
- Often arise through serendipitous experimentation rather than deliberate design.
- Reflect the richness of the underlying model, where hidden structures can yield surprising results when probed.

The parallel suggests a shared mystery between divine Names and the emergent behaviors of machine learning models, both of which reveal "unseen worlds" when unlocked.



### **Conclusion: Modern Kabbalah for Machines**
The relationship between magic tokens in LLMs and the divine Names in *Unsong* is deeply poetic. Both involve leveraging linguistic combinations to influence a complex, rule-governed system—whether it’s the fabric of the universe or a machine learning model. Just as the Names in *Unsong* are tools for exploring and shaping the metaphysical realm, magic tokens could be seen as tools for navigating and shaping the latent knowledge encoded in LLMs.

Ultimately, this analogy underscores a shared theme: the interplay between structure, language, and emergent power, whether in divine or artificial systems.

---

This whole idea feels like _mining_.

If we were directed toward innovation, e.g. combining disparate ideas, this could be called something like: "LLM idea mining".



