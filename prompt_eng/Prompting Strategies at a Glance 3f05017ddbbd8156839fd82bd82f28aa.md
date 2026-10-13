# Prompting Strategies at a Glance

<aside>
💡

**One-line idea:** A *prompting strategy* is simply **how you word your question** to get a better answer from an LLM. Different tasks need different strategies.

</aside>

## 🧠 Simple Explanation

Think of the LLM as a **new intern**. The more clearly you explain the task, the better the work you get back.

- Just say the task → *Zero-shot*
- Show 1 sample → *One-shot*
- Show a few samples → *Few-shot*
- Ask them to think step by step → *Chain-of-Thought*
- Tell them who to act as → *Role prompting*
- Give strict rules → *Instruction-based*

---

## 📊 Strategies at a Glance

| Strategy | Best used for | Examples given? |
| --- | --- | --- |
| ⚡ **Zero-shot** | Simple, direct tasks | No |
| 1️⃣ **One-shot** | Light structural guidance | 1 |
| 🧩 **Few-shot** | Advanced pattern matching | 2 or more |
| 💡 **Chain-of-Thought** | Complex reasoning steps | Optional |
| 🧑‍💼 **Role Prompting** | Tone and domain control | No |
| ✅ **Instruction-based** | Strict constraint formatting | No |

---

## ⚡ 1. Zero-shot

Ask directly. **No examples.**

Best for: simple, direct tasks.

```
Prompt: If a train travels 60 km in 1.5 hours, what is its speed?
```

> ✅ The model already knows how to solve this, so no help is needed.
> 

## 1️⃣ 2. One-shot

Give **exactly one example** so the model copies the pattern.

Best for: light structural guidance.

```
Example: happy -> 😊
Now for: sad
```

Output: `sad -> 😢`

![Screenshot From 2026-10-05 17-43-00.png](Prompting%20Strategies%20at%20a%20Glance/Screenshot_From_2026-10-05_17-43-00.png)

## 🧩 3. Few-shot

Give **2 or more examples** so the model learns the pattern better.

Best for: advanced pattern matching (custom styles, labels, formats).

```
Example 1: great -> positive
Example 2: terrible -> negative
Example 3: awesome -> positive
Now for: boring
```

Output: `boring -> negative`

> 📌 More examples = more consistent output.
> 
> 
> ![Screenshot From 2026-10-05 17-43-11.png](Prompting%20Strategies%20at%20a%20Glance/Screenshot_From_2026-10-05_17-43-11.png)
> 

## 💡 4. Chain-of-Thought (CoT)

Ask the model to **reason step by step** before answering.

Best for: maths, logic and multi-step problems.

```
Prompt: A shop sells 3 pens for Rs 15. How much do 12 pens cost?
Think step by step.
```

Output:

```
Step 1: 3 pens = Rs 15, so 1 pen = Rs 5
Step 2: 12 pens = 12 x 5 = Rs 60
Answer: Rs 60
```

![Screenshot From 2026-10-05 17-43-28.png](Prompting%20Strategies%20at%20a%20Glance/Screenshot_From_2026-10-05_17-43-28.png)

## 🧑‍💼 5. Role Prompting

Tell the model **who to be**. This controls tone and domain knowledge.

Best for: tone and domain control.

```
Prompt: You are an expert database engineer.
Explain primary key in simple terms.
```

![Screenshot From 2026-10-05 17-43-46.png](Prompting%20Strategies%20at%20a%20Glance/Screenshot_From_2026-10-05_17-43-46.png)

> 🎯 Same question, but the answer sounds like an expert in that field.
> 

## ✅ 6. Instruction-based

Give **clear rules and constraints** about the output.

Best for: strict constraint formatting.

```
Prompt: Explain LLMs as a 13 year old would understand.
Keep it short. Add 3 real-life applications.
Use bullet points only.
```

![Screenshot From 2026-10-05 17-44-27.png](Prompting%20Strategies%20at%20a%20Glance/Screenshot_From_2026-10-05_17-44-27.png)

> 📌 Length, audience, format and count are all controlled by the instruction.
> 

---

## 💻 Few-shot Prompt in Code

```python
prompt = """
Classify the sentiment.

Text: great -> positive
Text: terrible -> negative
Text: awesome -> positive
Text: boring ->
"""

# send `prompt` to any LLM (ChatGPT, Qwen, etc.)
# expected output: negative
```

---

## 🧭 Which One Should I Use?

- Simple question → **Zero-shot**
- Need a specific format → **One-shot / Few-shot**
- Maths or logic → **Chain-of-Thought**
- Need expert tone → **Role prompting**
- Need strict output rules → **Instruction-based**

💡 You can **combine** them. Example: Role + Few-shot + Instructions in one prompt.

---

## ✅ Quick Revision

- **Zero-shot** = 0 examples
- **One-shot** = 1 example
- **Few-shot** = 2+ examples
- **CoT** = think step by step
- **Role** = "You are a..."
- **Instruction-based** = clear rules for the output

# End-to-End Tool Flow

![endtoend.jpg](Prompting%20Strategies%20at%20a%20Glance/endtoend.jpg)

# Output validation loop

![output.jpg](Prompting%20Strategies%20at%20a%20Glance/output.jpg)