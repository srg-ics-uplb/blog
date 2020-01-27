Fuzzing: Hack, Art, and Science
###############################

:date: 2020-1-27
:category: Paper Review
:author: Joseph Anthony C. Hermocilla

A program usually accepts input, performs operations on the input, and produces output.  Incorrect processing of input can lead to security vulnerabilities, such as buffer overflow. Depending on the input, the program may not perform the desired operation. An attacker can craft a specialized input that exploits the vulnerability to take control of the machine running the vulnerable software. 

This paper [GODEFROID2020_] gives an overview of fuzzing as a way to detect security vulnerabilities. Other approaches mentioned in the paper include the use of static program analyzers and manual code inspection. Fuzzing tests the behavior of a program against all, or a subset, of possible inputs to identify security vulnerabilities. It is an automated testing technique since there is a large set of possible inputs to a program. 

The paper discussed three fuzzing techniques. The first technique is called Blackbox Fuzzing. This technique uses well-formed inputs, mutates them, then use the mutated input to test the software. 

The second technique is Grammar-Based Fuzzing. This technique is useful if the input follows some form of structured formats such as JSON or XML. In this approach, the tester provides a grammar specifying the format. The fuzzer then generates input based on the provided grammar.

The last technique is called Whitebox Fuzzing. This technique is more advanced since it uses dynamic symbolic execution. It gathers constraints on inputs as it executes a program from conditional branches. The constraints are negated and solved using a constraint solver. The solutions are then mapped to new inputs to pass through other execution paths in a program. SAGE is an example tool for Whitebox Fuzzing described in the paper.

The conclusion is that the fuzzing technique to use depends on the type of program being tested. Programs that use binary input formats are best tested with Blackbox Fuzzing or Whitebox Fuzzing. Programs with more structured formats will benefit from Grammar-Based fuzzing. 

.. [GODEFROID2020] Patrice Godefroid. 2020. Fuzzing: hack, art, and science. Commun. ACM 63, 2 (January 2020), 70–76. DOI:https://doi.org/10.1145/3363824
