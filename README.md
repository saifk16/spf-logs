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

Also use this `run config` it will help in running the tests/examples in SPF, just add it inside the 
`.idea/runConfigurations` folder and restart your ide or reload your project.

```xml
<component name="ProjectRunConfigurationManager">
    <configuration default="false" name="svcomp" type="JarApplication">
        <option name="JAR_PATH" value="$PROJECT_DIR$/jpf-core/build/RunJPF.jar" />
        <option name="VM_PARAMETERS" value="-Djava.library.path=&quot;$PROJECT_DIR$/jpf-symbc/lib/&quot; -ea -Xmx14g -Xss1g" />
        <option name="PROGRAM_PARAMETERS" value="$PROJECT_DIR$/jpf-symbc/src/examples/svcomp/config.jpf" />
        <option name="WORKING_DIRECTORY" value="$PROJECT_DIR$" />
        <option name="ALTERNATIVE_JRE_PATH_ENABLED" value="true" />
        <option name="ALTERNATIVE_JRE_PATH" value="1.8" />
        <envs>
            <env name="TARGET_CLASSPATH_WALA" value="./jpf-symbc/build/examples/" />
            <env name="LD_LIBRARY_PATH" value="./jpf-symbc/lib/" />
        </envs>
        <method v="2" />
    </configuration>
</component>
```

<br>

Follow the instructions on these files to setup the benchmark definitions:

1. [Competition Scripts](https://gitlab.com/sosy-lab/benchmarking/competition-scripts/#instructions-for-execution-and-reproduction)
2. [bench-defs](https://gitlab.com/sosy-lab/sv-comp/bench-defs)
3. [Benchexec - Install.md](https://github.com/sosy-lab/benchexec/blob/main/doc/INSTALL.md)

<br>

> [!WARNING]
> Please setup carefully and look out for issues related to cgroups

<br>

So there are two modes in the benchmarks can be executed upon tools like SPF

1. RuntimeException

```bash
# command to run runtime exception set over spf
scripts/execute_runs/execute-runcollection.sh     benchexec/bin/benchexec     archives/2025/spf.zip     benchmark-defs/spf.xml     witness.graphml     results-verified/     -t RuntimeException-Java         --timelimit 900 --memorylimit 3GB --limitCores 1 --numOfThreads 8     --read-only-dir / --overlay-dir /home/ --overlay-dir ./
```

<br>

2. ReachSafety

```bash
# command to run reach safety set over spf (Assertions)
scripts/execute_runs/execute-runcollection.sh     benchexec/bin/benchexec     archives/2025/spf.zip     benchmark-defs/spf.xml     witness.graphml     results-verified/     -t ReachSafety-Java         --timelimit 900 --memorylimit 3GB --limitCores 1 --numOfThreads 8     --read-only-dir / --overlay-dir /home/ --overlay-dir ./
```

Please remember to add a zip file of SPF in the `archives/2025/` folder. You can create a zip using this command:

```bash
zip -r spf.zip SPF/
```

