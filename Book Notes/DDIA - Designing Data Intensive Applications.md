# Chapter 1 Ideas
## Abstraction of Data Systems
- Most application tend to perform this common operations storing data(db), storing expensive results and using it again (cache), searching data (searching)
- Each application is different and that's why there are various data systems with different characteristics exists.
- We should be able to reason the right tool for the Job
## Why call these Data Systems or What is Data Systems?
1. Tools nowadays has variety of different use cases that we cannot fit into traditional use cases
2. Applications have very specific needs a single tool cannot satisfy the needs, so an application will wire general purpose components, and create a specific purpose composite data system
# The three concerns of a system
1. How do ensure application runs correct even when things go wrong? - Reliabilty
2. How do respond to increase in scale of load? - Scalabity
3. How to provide consisten