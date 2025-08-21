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
<br>
<h2 align="center">Support Runtime Exceptions in SPF</h2>

<h3>Introduction</h3>

**Java Pathfinder (JPF)** is a Java bytecode analysis tool mostly used for **[model checking](https://github.com/javapathfinder/jpf-core/wiki/Testing-vs.-Model-Checking)** written in Java. It does not execute a program like a normal JVM, it systematically explores all possible execution paths to check for errors, deadlocks, and unhandled exceptions. JPF was started as a model checker around 1999 and was developed at the NASA Ames Research Center. 

JPF also has extensions like **[Symbolic Pathfinder (SPF)](https://github.com/SymbolicPathFinder/jpf-symbc/)**, which combines symbolic execution with model checking and constraint solving for automated test case generation and error detection in Java bytecode. In SPF, programs are executed on symbolic, rather than concrete inputs.

<br>
<h3>Project Goal</h3>

In this project support for throwing **runtime exceptions** like `NullPointerException` and `StringIndexOutOfBoundsException` were added, for some string functions like **contains()**, **startsWith()**, **endsWith()**, **equals()**, **isEmpty()**, **subString()** and **charAt()** also the score of SPF on sv-benchmarks ([sv-comp](https://sv-comp.sosy-lab.org/)) was not good, the score also got improved because of the support that was done in this project.

<br>
<h3>Contributions</h3>

All the code I have contributed can be found at [this url](https://github.com/SymbolicPathFinder/jpf-symbc/compare/runtime-exception...saifk16:jpf-symbc:handler).

With those changes, methods like **contains()**, **startsWith()**, **endsWith**, **equals()**, **isEmpty()**, **subString()** and **charAt()** are supported to raise a `Runtime Exception`.
<br>

*NullPointerException* - **contains()**, **startsWith()**, **endsWith**, **equals()**, **isEmpty()**

```java
String str = Verifier.nondetString();
assert(str.contains("HELLO"));
```

In the above example we can clearly see that **str** is symbolic and **HELLO** is concrete, and a symbolic value can be anything it can be a **null**, it can be empty, it can be **HELLO** as well. 

Earlier we only had two choices:

- First choice where the **str** can contain **HELLO**
- Second choice where the **str** can not contain **HELLO** 

But there should can be a third choice as well because the **str** can be equal to **null** as well, as it is symbolic, so we need to add another choice for this case in the [SymbolicStringHandler](https://github.com/SymbolicPathFinder/jpf-symbc/compare/runtime-exception...saifk16:jpf-symbc:handler#diff-6feea6c550b38c071b2b438affe6dd6b0be73f795de404d4410b6354820375ecR931) in the method ***handleBooleanStringInstructions*** which is handling **contains()**, **startsWith()**, **endsWith**, **equals()**. **isEmpty** is not included in this method it is handled in the method [handleIsEmpty](https://github.com/SymbolicPathFinder/jpf-symbc/compare/runtime-exception...saifk16:jpf-symbc:handler#diff-6feea6c550b38c071b2b438affe6dd6b0be73f795de404d4410b6354820375ecR1371).
<br>

*StringIndexOutOfBoundsException* - **subString()**, **charAt()** 

```java
String str = Verifier.nondetString();
assert(str.subString(beginIndex));
```

> [!NOTE]
> Although we have added support for the `NullPointerException` but the `Verifier.nondetString()` will never return null. 

See the [issue 1438](https://gitlab.com/sosy-lab/benchmarking/sv-benchmarks/-/issues/1438) and this file [Verifier.java](https://gitlab.com/sosy-lab/benchmarking/sv-benchmarks/-/blob/5393b24a8864900ae00b6b159b7d9405b04fc62a/java/common/org/sosy_lab/sv_benchmarks/Verifier.java#L52-59)

After this a flag `nullPointer.Exception` was added in SPF so the choice 0, i.e., for the null check will be skipped for now, but this support or code change will help the users of **SPF**, as a **symbolic string** can be **null** as well.








