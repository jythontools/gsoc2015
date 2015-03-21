# Jython Google Summer of Code 2015 Ideas

These ideas need further fleshing out, but here is a starting list:

# Work on JyNI

Further extend support in [JyNI](http://jyni.org/) (Jython Native
Interface) for more of Python's C extension API, including
verification of interesting libraries. One ultimate goal is supporting
NumPy on Jython, but good progress to this will be more than enough
for the summer. You will need to figure out the best balance of what
needs to be improved in Jython, vs what can be contributed to JyNI
itself.

# Performance optimization

Determine quick and achievable wins for a summer of coding on
Jython. You should be data-based - run micro and macro benchmarks with
profiling tools, determine hotspots, find bottlenecks and
eliminate. Repeat, on a weekly or biweekly cycle. Your focus should be
on the Jython runtime and bytecode engines like
`org.python.modules.sre`, but not on a better Java bytecode compiler
for Jython, since that's too much work. You can also look at startup
time optimization, as well as removing overhead, such as trimming down
jar size.

# Python bytecode compiler

Jython has an implementation of a Python bytecode virtual machine in
`org.python.core.PyBytecode`. Complement this by writing a Python
bytecode compiler. Start by taking the AST and visitor approach as
seen in `org.python.compiler.CodeCompiler` for Java bytecode, and
write a corresponding compiler for Python bytecode. Do this
incrementally, with a TDD approach. Among other things, you should be
able to fix this bug: http://bugs.jython.org/issue527524
