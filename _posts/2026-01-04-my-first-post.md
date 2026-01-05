---
title: "Welcome to My Blog"
categories: [blog, intro]
tags: [python, automation, snippets]
---

Welcome 👋  

I’m starting this blog as a **developer notebook** — a place to write things down so I don’t lose them, and hopefully help other developers along the way.

Most of what you’ll see here will revolve around **Python**, automation, and practical code that actually gets used.

---

## Why Python?

Python is my go-to tool when I need to:
- Automate repetitive tasks
- Build quick scripts
- Glue systems together
- Prototype ideas fast

It’s readable, powerful, and gets out of the way.

So let’s start with a few **small but useful snippets** 👇

---

## 🐍 Snippet 1: Simple script timer

When optimizing or debugging, I often want to know **how long something takes**.

```python
import time

start = time.time()

# code you want to measure
time.sleep(1.2)

end = time.time()
print(f"Execution time: {end - start:.2f}s")
