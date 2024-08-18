# Chapter 1 Ideas
## Abstraction of Data Systems
- Most application tend to perform this common operations storing data(db), storing expensive results and using it again (cache), searching data (searching)
- Each application is different and that's why there are various data systems with different characteristics exists.
- We should be able to reason the right tool for the Job
### Why call these Data Systems or What is Data Systems?
1. Tools nowadays has variety of different use cases that we cannot fit into traditional use cases
2. Applications have very specific needs a single tool cannot satisfy the needs, so an application will wire general purpose components, and create a specific purpose composite data system
### The three concerns of a (any) system
1. How do ensure application runs correct even when things go wrong? - **Reliabilty**
2. How do respond to increase in scale of load? - **Scalability**
3. How to provide consistent performance when components degrades - **Maintainability**
## Reliability
- "Continuing to work, even when things go wrong(faults)"
- design **fault tolerant** mechanism that create **failures**

> [!NOTE] Reliability is important
- Imagine you're building a photo gallery appplication, where parent uses to save their kid's photos, and your system is not failure.
- Your'e responsible for your users!

### Hardware Faults
- Hardware faults happens all the times, such as disk failures, Ram faulty, power issues
- It can be handled with redundancy(When one component dies, another takes places, such as RAID) but not compeletely.
- Single machine failures are fairly low with redundancy implemented, with a downtime
- For Multimachine redundant system, the downtime can be averted for **high availablilty**
### Software Faults
- Systematic errors within the system itself, may cause cascading across nodes.
- Software faults are often corelated
- These kind of errors may hide until certain circumstances comes 
- A fault in one component may affect another, ie cascade
- Can be helped with comprehensive testing, monitoring behaviours

The author talks about bugs that are related to underlying software implementaion that the developers take granted for, such as leap years and seconds, and the application assusmes too, not applicaiton errors 
### Human Errors
- 'Humans are unreliable' 
- Design systesms in such a way that reduces oppurtunities for errors
    - Well designed abstrations
    - Isolate places where mistakes can cause failures
    - Provide fully featured sandbox environments for exploration and testing purposes
    - Do extensive exception handling
    - Test all levels unit tests, integration tests, and manual testing
    - **refer the book duh**


