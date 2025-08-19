![Google Summer of Code](GSoC_Logo.png)
---
<h1 align="center"> FINAL REPORT (GSoC 2025) </h1>

<div align="center">
  <img src="jpf.png" width="150">
</div>

<h2 align="center">THE JPF TEAM</h2>

- **Organization** - [The JPF Team](https://github.com/javapathfinder/jpf-core/wiki)
- **Organization Admins** - [Soha Hussein](https://github.com/sohah), [Yannic Nohller](https://github.com/yannicnoller)
- **Mentor** - [Soha Hussein](https://github.com/sohah)
- **Project** - [Support Runtime Exceptions in SPF](https://github.com/javapathfinder/jpf-core/wiki/GSoC-2025-Project-Ideas#runtime-exception-in-spf)
- **Contributor** - [Saif Ali Khan](https://github.com/saifk16/)

<br>
The following report summarizes the work done during Google Summer of Code 2025 with the results, improved sv-comp scores, and future work. This also serves as the final project report with all the contributions made, current state of the project, and the challenges faced.

<br>
<h2 align="center">Support Runtime Exceptions in SPF</h2>

<h3>Introduction</h3>

**Java Pathfinder (JPF)** is a Java bytecode analysis tool mostly used for **[model checking](https://github.com/javapathfinder/jpf-core/wiki/Testing-vs.-Model-Checking)** written in Java. It does not execute a program like a normal JVM, it systematically explores all possible execution paths to check for errors, deadlocks, and unhandled exceptions. JPF was started as a model checker around 1999 and was developed at the NASA Ames Research Center. 

JPF also has extensions like **Symbolic Pathfinder (SPF)**, which combines symbolic execution with model checking and constraint solving for automated test case generation and error detection in Java bytecode. In SPF, programs are executed on symbolic, rather than concrete inputs.





