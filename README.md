# rmqo

What is it?
-----------

Range Minimum Queries Offline (rmqo) is a fast C++11
library implementing an algorithm for answering a small batch of RMQs. 
The time complexity of the implemented algorithm is <i>n + O(q log q)</i> and the
extra space used is <i>O(q)</i>; where <i>n</i> is the size of the input array and <i>q</i> is the queries number. Note that we write <b>n</b> to stress that the number of operations per entry of the 
input array is a very small constant. Specifically, we only scan the input array twice.

Why rmqo?
--------

Answering a small batch of RMQs is a core computational task in many real-world applications. 
With <i>small batch</i>, we mean that the number <i>q</i> of queries is <i>o(n)</i>, for instance <i>q=O(sqrt(n))</i>, 
and we have them all at hand.  It is therefore not relevant to build an <i>O(n)</i>-sized data structure 
or spend <i>O(n)</i> time to build a more succinct one. It is well-known, among practitioners and elsewhere, that these data structures for on-line querying carry high constants in their pre-processing and querying time. We would thus like to answer this batch efficiently in practice. With <i>efficiently in practice</i>, we mean that we (ultimately) want to spend <i>n + O(q)</i> time and <i>O(q)</i> space. 

Requirements
--------

* A 64-bit GNU/Linux (or MAC) operating system.
* A C++11 ready compiler such as `g++` version 4.9 or higher.
* Processor of the system should support fast bit operations available in `SSE4.2`.

Installation
--------

```
git clone https://github.com/solonas13/rmqo.git
cd rmqo
make
make install
```

Usage
--------

Please check the `example-rmq.cc` file in the examples folder.

Examples 
--------

<b>Answering RMQs</b>
```
cd examples
make -f Makefile.rmq.gcc
./example-rmq
```
<b>Answering LCA queries</b>
```
cd examples
make -f Makefile.lca.gcc
./example-lca
```
Benchmark
--------

A simple program that generates a random array of size <i>n</i> and uses the rmqo library to answer a batch of <i>q</i> randomly generated RMQs.
```
cd bench
make -f Makefile.rmq-bench.gcc
./rmq-bench 100000000 10000
```

Citation
--------

```
M. Alzamel, P. Charalampopoulos, C. S. Iliopoulos, and S. P. Pissis: 
How to answer a small batch of RMQs or LCA queries in practice. 
(in preparation)
```

License
-------- 

GNU GPLv3 License; Copyright (C) 2016 Mai Alzamel and Solon P. Pissis
