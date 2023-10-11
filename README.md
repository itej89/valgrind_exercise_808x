# Valgrind Exercise

## Standard install via command-line
```bash
# Configure the project and generate a native build system:
  # Must re-run this command whenever any CMakeLists.txt file has been changed.
  cmake -S ./ -B build/
# Compile and build the project:
  # rebuild only files that are modified since the last build
  cmake --build build/
  # or rebuild everything from scracth
  cmake --build build/ --clean-first
  # to see verbose output, do:
  cmake --build build/ --verbose
# Run program:
  ./build/app/shell-app
# Clean
  cmake --build build/ --target clean
# Clean and start over:
  rm -rf build/
```


##  Valgind's results
* Valgrind results can be found in "valgrind_results" directory of this repository



##  Valgind's behaviour when using with static library
```
1. What happens when the executable is linked statically?  Does Valgrind still detect those same bugs?

Ans: When exwecutable linked statically Valgrind does not detect memory leaks. Also Valgrind shows additional errors from glibc which will be supressed when linked statically.


2. Why or why not.

Ans: Reason for Valgrind unable to detect memory leaks is that when linked statically valgrind can not load its own libraries using 'LD_PRELOAD' causing it to lose the ability to detect memory leaks.



References: 
https://www.linkedin.com/pulse/how-use-valgrind-detect-memory-errorsan-overview-sanjay-kumar/

https://stackoverflow.com/questions/7506134/valgrind-errors-when-linked-with-static-why
```
