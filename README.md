> [!NOTE]
> [This repository contains **execution logs** and results from **SV-COMP** benchmarks that were run on ***Symbolic PathFinder*** (SPF) during ***Google Summer of Code 2025*** under ***The JPF Team***. The project focused on adding ***Runtime Exception Support*** to SPF, which resulted in significant improvements in ***SV-COMP benchmark*** scores.]

<br>

Please see the report => [Support_For_RuntimeException_In_SPF_GSoC_2025.md](/Support_For_RuntimeException_In_SPF_GSoC_2025.md)


## 📁 Repository Structure

```bash
logs/
├── SPF-1.0/
└── SPF-2.0/
19_False_Verdict_Verification_Tasks_RuntimeExceptionSet.md
Support_For_RuntimeException_In_SPF_GSoC_2025.md         
README.md                                                  
```

<br>

## ⚙️ Setup and Installation

### Prerequisites

1. Java 8 (OpenJDK)
2. Git and Github
3. Gradle (Version: 6.9 or above)
4. Python (Version: 3.10.12)

### Development Environment

1. IntelliJ IDEA Ultimate (For making PRs, commits, adding the correct code)
2. IntelliJ IDEA Community (For Testing)
3. OS: Ubuntu 22.04.5 (Jammy)
4. IntelliJ PyCharm (For the benchmark definitions from sosy-labs)

### How to setup spf repository locally and run benchmarks

```bash
# Clone the repo
git clone -b runtime-exception --recurse-submodules git@github.com:SymbolicPathFinder/jpf-symbc.git SPF

# Move the folder
cd SPF

# Build jpf-core
gradle jpf-core:buildJars

# Build jpf-symbc
gradle jpf-symbc:buildJars
```

Rest can be found [here](https://github.com/SymbolicPathFinder/jpf-symbc/tree/runtime-exception)