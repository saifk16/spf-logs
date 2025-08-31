This repository contains **execution logs** and results from **SV-COMP** benchmarks that were run on ***Symbolic PathFinder*** (SPF) during ***Google Summer of Code 2025*** under ***The JPF Team***. The project focused on adding ***Runtime Exception Support*** to SPF, which resulted in significant improvements in ***SV-COMP benchmark*** scores. See the [report](/Support_For_RuntimeException_In_SPF_GSoC_2025.md)


# 📁 Repository Structure

```bash
logs/
├── SPF-1.0/                          # Baseline results (sv-comp branch)
│   ├── reachsafety/                   # ReachSafety benchmark logs
│   └── runtime/                       # Runtime Exception benchmark logs
└── SPF-2.0/
    └── Date-26Aug/                    # Results with runtime exception support
        ├── reachsafety/               # ReachSafety benchmark logs
        └── runtime-exception/         # Runtime Exception benchmark logs
            └── spf.2025-08-26_03-20-08.results.SV-COMP25_runtime-exception.RuntimeException-Java.html

19_False_Verdict_Verification_Tasks_RuntimeExceptionSet.md  # Analysis of 19 key test cases
Support_For_RuntimeException_In_SPF_GSoC_2025.md          # Complete project report
README.md                                                  # This file
```