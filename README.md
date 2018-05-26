General
--------------------

### Basic math

* [Arithmetic series](https://en.wikipedia.org/wiki/Arithmetic_progression) sum: n(a1 + an) / 2 = ϴ(n²)
* [Bayes theorem](https://en.wikipedia.org/wiki/Bayes%27_theorem): P(A|B) = P(B|A) P(A) / P(B)
* [Harmonic series](https://en.wikipedia.org/wiki/Harmonic_series_(mathematics)) sum: 1 + 1/2 + 1/3 + ... + 1/n = ln n + O(1)

* There are n! permutations for n elements: n ways to choose the 1st element, n-1 ways to choose the 2nd element, etc. k-permutation = permutation of subsequence of length k.
* [Binomial coefficient](https://en.wikipedia.org/wiki/Binomial_coefficient) (ways to select unordered items): n! / [k! (n - k)!], for ordered items: n! / (n - k)!

### Graphs

* Bipartite: two disjoint, independent sets
* Complete graph: every pair of vertices is adjacent, no loops
* Strongly connected: every 2 vertices are reachable from each other
* Tree: connected, acyclic, undirected graph

### Complexity

* o, O, ϴ, Ω, ω
* O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2<sup>n</sup>) < O(n!)
* P, NP, NP-complete, NP-hard, [P vs NP](https://en.wikipedia.org/wiki/P_versus_NP_problem)

#### Amortized analysis

[Amortized analysis](https://en.wikipedia.org/wiki/Amortized_analysis) looks at the entire execution sequence, not just the worst-case scenario.

* Aggregate analysis: T(n)/n for a total cost T of n operations
* Accounting method: saving credit from costly operations to speed up other operations
* Potential method: like the accounting method but with a custom function

### Data structures

#### Basic

Average cases are presented. BST is assumed to be balanced, hashing a simple item is assumed to be constant-time.
For the hash table worst-case for all operations is O(n).

Structure  | Access   | Search   | Insert/delete  | Space
---------- | -------- | ---------| -------------- | -------
Array      | O(1)     | O(n)     | O(n)           | O(n)
List       | O(n)     | O(n)     | O(1)           | O(n)
BST        | O(log n) | O(log n) | O(log n)       | O(n)
Hash table | O(1)     | O(1)     | O(1)           | O(n)


##### BST

* [AVL](https://en.wikipedia.org/wiki/AVL_tree) – first self-balancing BST. Height of two child subtrees differs by at most 1. In order to balance after a regular insertion of new node w: travel up to the root to find the first unbalanced node z. Rotate subtree rooted with z: 4 cases based on node z and its child/grandchild: a) y is left, x is left (on the path to w), b) left-right, c) right-left, d) right-right.

* [Red-black](https://en.wikipedia.org/wiki/Red%E2%80%93black_tree) – each node is R or B, the root is B. If node is R, both children are B. Any path from node to any leaf (NIL, B) has the same number of black nodes.

* [Treap](https://en.wikipedia.org/wiki/Treap) – BST with priorities maintained in a heap. Searching is just like BST, insertion: generate random priority, add leaf at a regular position, use rotations in order to restore the max-heap property.

##### Heap

[Heap](https://en.wikipedia.org/wiki/Heap_(data_structure)) – priority queue, max-heap or min-heap. Adding: add at the bottom, continue swapping with parent (sifting up). Deleting: swap root with the last leaf, sift down the new root. Various kinds of heaps exist: Brodal, Fibonacci, etc.

#### String matching

* [Trie](https://en.wikipedia.org/wiki/Trie) – a tree in which the position of a node describes the associated value, search is proportional to the pattern length, that is O(m).

* [Suffix array](https://en.wikipedia.org/wiki/Suffix_array) – stores indexes of sorted suffixes from the input text, search is O(m log n), space is around 5n.

* [Suffix tree](https://en.wikipedia.org/wiki/Suffix_tree) – a trie which stores all suffixes of the input string, search is O(m), space is around 10n.

### Algorithms

* [Brute-force](https://en.wikipedia.org/wiki/Brute-force_search) – exhaustive search, checking all solution candidates.

* [Dynamic programming](https://en.wikipedia.org/wiki/Dynamic_programming) – solving simpler subproblems and storing solutions, e.g., Fibonacci sequence with memoization.

* [Greedy algorithm](https://en.wikipedia.org/wiki/Greedy_algorithm) – makes a locally optimal choice at each step.

* [Las Vegas](https://en.wikipedia.org/wiki/Las_Vegas_algorithm) vs [Monte Carlo](https://en.wikipedia.org/wiki/Monte_Carlo_algorithm) – LV is a randomized algorithm which always produces a correct result or informs about the failure (it gambles with computational resources), MC is a randomized algorithm which might report an incorrect result (it gambles with result accurracy).

#### Sorting

* [Bubble sort](https://en.wikipedia.org/wiki/Bubble_sort) – best O(n), avg O(n²), worst O(n²)
* [Insertion sort](https://en.wikipedia.org/wiki/Insertion_sort) – best O(n), avg O(n²), worst O(n²)
* [Selection sort](https://en.wikipedia.org/wiki/Selection_sort) – best, avg, worst O(n²)
<br />

* [Heapsort](https://en.wikipedia.org/wiki/Heapsort) – best, avg, worst O(n log n)
* [Mergesort](https://en.wikipedia.org/wiki/Merge_sort) – best, avg, worst O(n log n)
* [Radix sort](https://en.wikipedia.org/wiki/Radix_sort) – best, avg, worst O(w n)
* [Quicksort](https://en.wikipedia.org/wiki/Quicksort) – best O(n log n), avg O(n log n), worst O(n²), related: [quickselect](https://en.wikipedia.org/wiki/Quickselect), finds k-th smallest element in O(n) avg time.

#### Machine learning

Supervised, unsupervised, reinforced.
Applications:

* classification (discrete)
* regression (continuous)
* clustering
* density estimation

Techniques:

* [ANN](https://en.wikipedia.org/wiki/Artificial_neural_network)
* [Association rules](https://en.wikipedia.org/wiki/Association_rule_learning) – created mostly based on frequency of appearance, e.g., `{onions, potatoes} => {burger}`.
* Bayesian
* [Decision tree](https://en.wikipedia.org/wiki/Decision_tree_learning) – sets of rules
* [Deep learning](https://en.wikipedia.org/wiki/Deep_learning) – using multiple layers of nonlinear processing units. Levels correspond to different levels of abstraction and form a hierarchy of concepts.
* [SVM](https://en.wikipedia.org/wiki/Support_vector_machine) – separate data by hyperplanes with the largest margin. Kernel functions allow for implicit mapping into higher dimensions in order to ensure data segregation.

#### Graphs

* [A*](https://en.wikipedia.org/wiki/A*_search_algorithm) – maintain a closed and open set (open has start at the begginning). While open is not empty, take current from open with lowest estimate, move it to closed, and expand all negibhors. Finish if current is the goal. Heuristic must be admissible (not overestimating).

* [B*](https://en.wikipedia.org/wiki/B*) –

* [D*](https://en.wikipedia.org/wiki/D*) –

* [Dijkstra](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) – specific case of A* without a heuristic.

* [Coloring](https://en.wikipedia.org/wiki/Graph_coloring) – labeling where no adjacent vertices share a label.

* [TSP](https://en.wikipedia.org/wiki/Travelling_salesman_problem) – find the shortest Hamiltonian cycle (visits each node exactly once and returns to the start).

* [Voronoi diagram](https://en.wikipedia.org/wiki/Voronoi_diagram) – partitioning into regions based on a distance to the closest point.

#### Trees

* [Kruskal](https://en.wikipedia.org/wiki/Kruskal%27s_algorithm) – minimum spanning tree. Divide all nodes into a forest, always take the shortest edge, span only if spanning two distinct trees, otherwise discard.

* [Traversal](https://en.wikipedia.org/wiki/Tree_traversal) – DFS (pre-order, in-order, post-order), BFS (use a priority queue based on depth).

#### String matching

##### Exact

* [Aho-Corasick](https://en.wikipedia.org/wiki/Aho%E2%80%93Corasick_algorithm) – a finite state machine which resembles a trie. Matches multiple queries at once while sliding over the text.

* [Boyer-Moore](https://en.wikipedia.org/wiki/Boyer%E2%80%93Moore_string_search_algorithm) – begin matching from the end of the pattern and jump forward based on mismatches. After proprocessing, the size of each shift can be determined in constant time: align the text with the rightmost occurrence of current char in P or shift the pattern by its total length. Worst case is O(nm + δ).

* [KMP](https://en.wikipedia.org/wiki/Knuth%E2%80%93Morris%E2%80%93Pratt_algorithm) – for each mismatch at position i in the pattern, shift P by i - l, where l is the length of the longest proper prefix of P[0, i − 1] which is also a suffix of P[0, i − 1] and start matching from position l in the pattern. Worst case is O(n + m).

* [Rabin-Karp](https://en.wikipedia.org/wiki/Rabin%E2%80%93Karp_algorithm) – rolling hash, worst case is O(nm).

* [Shift-or](https://en.wikipedia.org/wiki/Bitap_algorithm) – based on bit-parallelism, pattern length must be smaller than the word size. Computes a mismatch mask for each character from the alphabet with unset bits corresponding to positions of this character in the pattern. At each step, the state mask is shifted and or-ed with the mask for the current character from the text.

##### Approximate

* [Hamming distance](https://en.wikipedia.org/wiki/Hamming_distance) – counts the number of mismatching characters at corresponding positions.
* [Levenshtein distance](https://en.wikipedia.org/wiki/Levenshtein_distance) – counts the number of single-character edits (insert, delete, substitute) needed to transform one word into another.

* [Needleman-Wunsch](https://en.wikipedia.org/wiki/Needleman%E2%80%93Wunsch_algorithm) –

* [Smith-Waterman](https://en.wikipedia.org/wiki/Smith%E2%80%93Waterman_algorithm) –

### Design patterns

The following summary is based on [Wikipedia](https://en.wikipedia.org/wiki/Software_design_pattern) page. Obvious patterns are only listed and not described.

#### Creational

* Abstract factory: encapsulate individual factories under a generic interface.

* Builder: separate construction from interpretation.

* Dependency injection

* Factory

* Lazy initialization

* Multiton: registry of singletons

* Object pool

* Prototype: create new objects from a skeleton.

* RAII: constructor/destructor

* Singleton

#### Structural

* Adapter: wrapper

* Bridge: decouple abstraction from implementation in order to facilitate changes.

* Composite: groups of objects treated the same as a single object.

* Decorator: dynamically add behavior to an individual object, without affecting the behavior of other objects (i.e. alter behavior at runtime).

* Extension: allows for adding new functionality to a class without inheritance (e.g., extension functions in Kotlin).

* Facade: a higher-level interface which is easier to use.

* Flyweight: use sharing to support large numbers of lightweight similar objects efficiently.

* Marker: use an empty interface to indicate specific behavior (e.g., Serializable).

* Proxy: used in order to control access to an object.

* Twin: multiple inheritance in languages that do not support it (two closely coupled subclasses, each derived from one superclass).

#### Behavioral

* Blackboard: knowledge sources publish potential solutions on the blackboard, the control component is in between.

* Chain of responsibility: a chain of processing objects receives the commands which are handled or passed along. Essentially if..elif..else which can be dynamically reconfigured.

* Command: object encapsulates all information needed to perform an action at a later time, including the receiver.

* Interpreter: use of DSL, e.g., SQL, user interface descriptions.

* Iterator: decouples algorithms from containers.

* Mediator: encapsulates communication between objects, reduces coupling.

* Memento: checkpointing, allows for undo via rollback.

* Null object/nullable type: avoid problems with null dereference.

* Observer: publish-subscribe, signals-slots, event-driven, observers are notified of any changes.

* Servant: provides behavior (methods) to a group of classes, objects for which the servant provides the service are taken as parameters.

* Specification: combining rules using boolean operators, mostly for data filtering.

* State: implement state machine where each state is a derived class calling parent interface methods.

* Strategy: enables selecting algorithm at runtime (e.g., validation algorithm based on incoming data).

* Template method: base class implements basic steps of an algorithm, specifics (variants) are implemented in derived classes.

* Visitor: separate algorithm from object structure on which it operates, allows for defining new operations without changing elements on which it operates. Visitor takes concrete elements as arguments.

### Architectural patterns

* Broker: coordination among components, for instance in between the client and servers.
* Client-server
* Layered: levels of abstraction, for instance UI layer, service, domain (business logic), persistence layer, e.g., general desktop app.
* Master-slave
* P2P
* Pipe-filter: `src | pipe1 | filter1 | pipe2 | filter2 | sink`, e.g., compiler.

####
MVC

* Model: data + state.
* View: lean, rendering UI, loosely coupled, not knowing what to do when the user presses the button (only forwards data).
* Controller: receives the input from the view and interacts with the model (e.g., activity in Android).

Problem is with the controller which is tightly coupled with a view and may get bloated, since most of the logic is there.

####
MVP

* Model: the same as in MVC.
* View: it is now up to the view which is a bit smarter than in MVC to determine which functions from the presenter to call.
* Presenter: is like a controller but is just an interface, not tied to the view in order to allow more flexibility.

####
MVVM

* Model: the same as in MVC.
* View: binds to the observables that are exposed by the viewmodel.
* Viewmodel: has observables for the view and allows the view to pass events to the model.

### Principles

* [ACID](https://en.wikipedia.org/wiki/ACID): for transactions: atomicity (all or nothing), consistency (one valid state to another), isolation (concurrent execution same result as sequential), durability (once committed remains so).

* [Broken windows theory](https://en.wikipedia.org/wiki/Broken_windows_theory): bad code encourages more bad code.

* [CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem): only 2/3 guarantees are simultanously possible: consistency (every read receives the most recent write or error), availability (every request has a response), partition tolerance (system works even if messages are dropped).

* [CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete): create, read, update, delete, 4 basic functions of persistent storage.

* [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself): avoid redundancy.

* [KISS](https://en.wikipedia.org/wiki/KISS_principle): keep it simple, stupid.

* [MoSCoW](https://en.wikipedia.org/wiki/MoSCoW_method): project planning: must have, should have, could have, won't have.

* [Not invented here](https://en.wikipedia.org/wiki/Not_invented_here): avoiding using products, guidelines, etc. created outside the company.

* [RAII](https://en.wikipedia.org/wiki/Resource_acquisition_is_initialization): constructor/destructor.

* [Reinventing the wheel](https://en.wikipedia.org/wiki/Reinventing_the_wheel): duplicating a common, known method.

* [SOLID](https://en.wikipedia.org/wiki/SOLID): single responsibility (per class), open/closed (open for extension, closed for modification, e.g., inheritance), Liskov substitution (subclass can be used as if it were its parent), interface segregation (expose only the required methods to clients), dependency inversion (program to an interface, not to an implementation).

* [SSOT](https://en.wikipedia.org/wiki/Single_source_of_truth): each data element is stored exactly once

* [Worse is better](https://en.wikipedia.org/wiki/Worse_is_better): less functionality is sometimes preferable (e.g., easier to use).

* [YAGNI](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it): don't add functionality until necessary.

### Project planning

* [Continuous integration](https://en.wikipedia.org/wiki/Continuous_integration): merging all working copies several times a day in order to mitigate integration problems.

* [Continuous delivery](https://en.wikipedia.org/wiki/Continuous_delivery): short cycles, software can be released at short notice.

* [Neutral build](https://en.wikipedia.org/wiki/Neutral_build): done in a neutral environment (outside deployment), catches errors such as different environmental variables, unchecked files, etc.

* [Nightly build](https://en.wikipedia.org/wiki/Daily_build): auto neutral build, mostly done when no one is working.

#### Things to consider

1. Specification, possibly start with abstract description and work towards the details.
1. Select the technologies and the development process.
1. Define features, perhaps in connection with the technologies.
1. Define the timeline: task planning, delegation, select a team, divide responsibilities, agree how progress/success will be measured/defined.
1. Before the start: check if we have everything we need (resources, etc.)

#### Scrum

[Scrum](https://en.wikipedia.org/wiki/Scrum_(software_development)): 3-9 people, sprints ~2 weeks, daily 15-minute stand-ups. Iterative, incremental, flexible.

* Product owner = stakeholders
* Development team
* Scrum master = servant-leader, helps the team

### Language-related concepts

* Declarative (functional, logic, reactive) vs imperative languages (procedural, object-oriented).
* Binding: early = at compile time (e.g., overloading), late (dynamic) = at run time (e.g., overriding).
* Introspection: ability to examine type or properties at runtime.
* Monkey patching: dynamic replacement of attributes at runtime.
* Reflection: modification of program structure at runtime.
* Static dispatch (e.g., function overloading) vs dynamic dispatch (for dynamic dispatch, declare a C++ method as virtual).
* Single dispatch (depends on object type as in C++) vs double dispatch (depends both on object type and parameters).

#### Object-oriented terminology

* Abstraction
* Encapsulation = hiding data
* Friend = defined outside a class but can access internal stuff
* Inheritance
* Interface = collection of methods (mostly abstract)
* [Polymorphism](https://en.wikipedia.org/wiki/Polymorphism_(computer_science)) = more than one form, examples: function overloading (ad-hoc polymorphism), generics, inheritance.
* Virtual function = can be overridden

### Unit testing

*TODO*

* [Hamcrest](https://en.wikipedia.org/wiki/Hamcrest) (matchers)

### Useful Linux commands

#### General

* `cat [file]` – print file contents
* `chmod [XXX] [file]` – change permissions to `[XXX]` (owner, group, anybody) for `[file]`, 4 = read, 2 = write, 1 = execute (can be combined)
* `grep ^alex /etc/passwd | cut -d: -f1` – grep lines starting with "alex", delimit on ":" and print the first field
* `df -h` – disk usage in human-readable
* `find / -name "*.txt" 2> /dev/null` – find all files with txt extension while ignoring error messages
* `ls -lah` – list current dir with hidden files and details in human-readable
* `man gcc | grep [-]std=c++11 -C2` – search for a switch and show 2 lines around the result
* `mv [src] [dst]` – move file `[src]` to `[dst]`, can be used for renaming
* `rm -rf [dir]` – remove `[dir]` recursively without prompting
* `touch [file]` – create `[file]`
* `whereis [cmd]` – check the location of `[cmd]`

#### Packages

* `apt-get update` – update package index
* `apt-get dist-upgrade` – install update and satisfy dependencies
* `dpkg --listfiles [pkg]` – list all files from package `[pkg]`
* `update-alternatives --config [pkg]` – select a different version for `[pkg]`

#### Conversions

* `dot -Tpdf [in].dot -o [out].pdf` – convert dot (graph) file `[in]` to `[out].pdf`
* `rsvg-convert -f pdf -o [out].pdf [in]` – convert SVG file `[in]` to `[out].pdf`
* `pdfcrop --margins '0 0 0 0' [in].pdf [out].pdf` – crop pdf file `[in].pdf`, write to `[out].pdf`

#### Net

* `host [url]` – get IP for `[url]`
* `wget -m -e robots=off --no-parent [url]` – download recursively from `[url]`
* `whois [IP]` – get information about `[IP]`

#### Compression

* `tar -xzf [in]` – extract, gunzip (j = bzip), input file `[in]`
* `unzip [file]`
* `zip [out] [file1] [file2]`

C++
--------------------

[C++](https://en.wikipedia.org/wiki/C%2B%2B) – compiled, static typing, object-oriented.

### Basic

* Abstract class has pure virtual functions: `virtual void fun() = 0;`

* Class has private fields/funs by default, struct has public fields/funs by default.

* Constructors: default (created when no other constructor is specified), parametric, copy, move.

* Placement new: `char *buf = new char[sizeof(string)];`, `string *p = new (buf) string("hi")`

* References cannot be null, reset or uninitialized.

* `assert(1 == 1 == 1)` doesn't fail, `assert(4 == 4 == 1)` doesn't fail, `assert(4 == 4 == 4)` fails, assert `assert(1 == 4 == 4)` fails.

* [Rule of three](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)) – destructor, copy constructor, copy assignment operator.

#### Memory management

`malloc`/`calloc` return NULL on error and they must be matched with `free`/`realloc`.
`new` must be matched with `delete` or `delete[]`, it throws `bad_alloc` on error or use `(std::nothrow)` to return NULL instead.

#### Operator overloading

```
Type operator+ (const Type &type);
friend Type operator+ (const Type &t1, const Type &t2);
```

#### Variadic functions

`int printf(const char* format, ...)`. Init with `va_list` , then `va_start`, `va_arg` for accessing each arg, finish with `va_end`.

#### Preprocessor directives

* Useful for [debug print](https://stackoverflow.com/questions/14251038/debug-macros-in-c):

```
#define DEBUG

#ifdef DEBUG
    #define D(code) code
    #define DEBUG_PRINT(msg) (cout << msg << endl)
#else
    #define D(code)
    #define DEBUG_PRINT(msg)
#endif

D(cout << "Hello debug" << endl;)
DEBUG_PRINT("Hello debug 2");
```

* Useful for code selection at compile-time:

```
#define ALG_TYPE 1

#if ALG_TYPE == 1
    cout << "Alg type 1" << endl;
#elif ALG_TYPE == 2
    cout << "Alg type 2" << endl;
#else
    #error Bad ALG_TYPE
#endif
```

* Useful for OS-specific code:

```
#ifdef __linux__
    cout << "Hello Linux" << endl;
#elif _WIN32
    cout << "Hello Windows" << endl;
#else
    #error OS not supported
#endif
```

* [Include guards](https://en.wikipedia.org/wiki/Include_guard) prevent double declaration and circular inclusion.

### C++11

* Use `-std=c++11` switch for compilation.

* `for (const int i : tab) { }` works for arrays and containers with `begin()` and `end()`.

* Enum class values require scoping: `enum class Letters { A, B, C }; cout << (int)Letters::A << endl;`

* `auto n = 5; cout << typeid(n).name() << endl;` prints `i`.

* Static class: `struct Test { Test() = delete; };`

* Mark overriden (virtual) functions with `override` keyword.

* `nullptr` is a pointer type NULL (NULL is just 0).

* `constexpr`: a constant value which must be initialized at compile time.

* [Rule of five](https://en.wikipedia.org/wiki/Rule_of_three_(C%2B%2B_programming)#Rule_of_Five): destructor, copy constructor, move constructor, copy assignment operator, move assignment operator.

#### Move semantics

* lvalue: has address and can be assigned.
* rvalue: a temporary object `string getName() { return "ala"; } string &&name = getName();`

```
MyString(const MyString &other) { }
MyString(MyString &&other) { } // steal the resources from other

MyString &operator= (MyString other) // pass-by-value
{
  swap(other);
  return *this;
}
```

#### Lambdas

```
sort(tab, tab + n, [](int a, int b) { return a > b; });
```
Lambdas automatically capture constants, in addition: `[x]` captures `x` by value, `[&x]` captures x by reference.

* `transform(tab, tab + n, tab, [&z](int x) { return x + z; });` works like map
* `for_each(tab, tab + n, [&z](int &x) { x = x + z; });` also works like map (the same)
* `int acc = 0; for_each(tab, tab + n, [&acc](int x) { acc = acc + x; });` works like reduce

* Removing elements from a vector using iterators

```
for (auto it = vec.begin(); it != vec.end(); )
{
    if (*it % 2 != 0)
    {
        it = vec.erase(it);
    }
    else
    {
        ++it;
    }
}
```

* Removing elements from a vector like filter

```
vector<int> filtered;
for_each(vec.begin(), vec.end(), [&filtered](int x) { if (x % 2 == 0) { filtered.push_back(x); } });
```

#### Multithreading

Before C++11 it was required to use OS-specific functionality, e.g., pthreads on Linux.
Launching a simple thread:

```
thread t1([]() { cout << "t1" << endl; });
t1.join(); // Blocks until t1 finishes
```

Threads with synchronization:

```
vector<thread> threads;
mutex mut;

for (int i = 0; i < 5; ++i)
{
    threads.push_back(thread([i, &mut]() {
        mut.lock();
        cout << "t: " << i << endl;
        mut.unlock();
    }));
}
```

* `std::promise` is the producer and `std::future` is the consumer.
* `future<void> res(async(fun));` – async can take fun with args or a lambda, `res.get();` blocks until the result is available.

#### Smart pointers

* `shared_ptr<int>tab (new int[size]);` – resource is deallocated when the last pointer is destroyed. Thread-safe for reference counting, not thread-safe for pointed object access.

Shared pointer can be created using the `make_shared` function:

```
struct Test { int a; };
auto ptr = make_shared<Test>(); // ptr is a shared_ptr<Test>
cout << ptr->a << endl;
```

* `weak_ptr` – doesn't increase the count, useful for preventing circular dependencies.
* `unique_ptr` – only one reference, cannot be copied, move semantics allow for ownership transfer.

### C++14/17

* Use `-std=c++14` or `-std=c++17` switch for compilation.

*TODO*

### Makefile

*TODO*

Python
--------------------

[Python](https://en.wikipedia.org/wiki/Python_(programming_language)) – interpreted, object-oriented, garbage-collected, name binding, duck typing (based on runtime object interface),  many libraries. Reference interpreter is called CPython, other: PyPy which is based on JIT. Stuff below is relevant to Python2.

[Not great](https://stackoverflow.com/questions/1017621/why-isnt-python-very-good-for-functional-programming) for functional programming:

* no tail recursion (i.e. no using equivalent memory to a loop)
* no pattern matching
* not too many list functions
* no concise way to combine functions

### Selected features

* `[1,2,3] == [1,2] + [3]`

* `[1,2,3,4][1 : 3] == [2,3]`, `[1,2,3][ : 1] == [1]`

* `[1,2,3,4][::2] == [1,3]`, `[1,2,3][::-1] == list(reversed([1,2,3]))`

* `l = [[]] * 5`: same reference replicated, doesn't work as expected. Use `l = [[] for _ in xrange(5)]` instead.

* Deep copy: `l = copy.deepcopy(x)`, works with nested lists.

* `dir(obj)` returns a list of defined members (functions and variables).

* Functions are first-class citizens in Python, nested functions are allowed, functions can be assigned, returned, etc.

* Import from subdir requires a present `__init__.py` file (may be empty).

* `reverse(l)` returns an iterator to `l` (if `l` changes, data pointed to by an iterator changes too).

* Serialization (translating data to storage/transmission format) can be realized using `pickle` or `cPickle` (the latter is faster).

* Tertiary operator: `x = 2 if len(s) > 5 else 10`

* Tuple `(1,2,3)` is immutable.

* `with` works like try/finally, requires context management protocol: `__enter__()`, `__exit()__`.

* `xrange` and `range` start from 0, Python2: `xrange` is a generator and `range` creates a list, in Python3 there is only `range` which is a generator.

* `zip([1,2,3],[4,5,6]) == [(1,4), (2,5), (3,6)]`

### List functions

* `del l[1]` removes an element at index 1.
* `l.pop(1)` removes an element at index 1 and returns this element.
* `l.pop(l.index(max(l)))` removes the max element.
* `l.remove(x)` removes the first value matching `x`.

### Functions

#### Calling with args

```
def add(x, y):
  return x + y

def add3(x, y = 3):
  return x + y

def addStar(*args): # All params as a tuple
  return sum(args)
```

* Default arg values must follow from the left.
* Calling with explicit arg names: `print add(x = 5, y = 4)`.
* `print addStar(1, 2, 3)`
* Unpacking operator: `print add(*[1, 2])`
* Partial application (argument binding): `add5 = functools.partial(lambda x,y: x + y, 5)`

#### Keyword args

```
def addKwargs(**kwargs): # All keyword params as a dict
  return sum(kwargs.values())
```

* `print addKwargs(x = 2, y = 3)`
* `print addKwargs(**{"x": 2, "y" = 3})`

### Filter, map, reduce

* List comprehension combines map with filter: `[2 * x for x in xrange(10) if x % 2 == 0]`.
* `map(lambda x: 2 * x, filter(lambda x: x % 2 == 0, xrange(10)))`
* `map(len, ["ala","ma","kota"]) == [3,2,4]`
* `sum([1,2,3]) == reduce(lambda x,y: x + y, [1,2,3], 0)`

### Classes

```
class Point(object):
  n = 5 # Static var, access as Point.n

  def __init__(self, x, y):
    self.x = x
    self.y = y

  def mysum(self): # Not passing self would mean a static function
    return self.x + self.y
```

* Always inherit from `object` for access to class names (new-style classes).
* Convention for private: `self._x`, private with a mangled name: `self.__x` (works for both functions and variables).
* Dictionary containing all member variables: `print p1.__dict__`
* Extend objects: `p1.z = 8`, now `print p1.z` works (only if z was set for this object).

#### Inheritance

```
class Point3D(Point):
  def __init__(sefl, x, y, z):
    Point.__init__(self, x, y)
    self.z = z

  def mysum(self):
    return Point.mysum(self) + self.z
```

### Plotting

```
import matplotlib.pyplot as plt

plt.title("title")
plt.xlabel("X")
plt.ylabel("Y")

plt.tight_layout()
plt.xlim(0.9, 3.1)
plt.ylim(3.9, 6.1)

plt.plot([1,2,3], [4,5,6], "ko-")
plt.show()
```

Git
--------------------

[Basic commands](https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html):

* `git init`
* `git clone [address]`
</br>

* `git add -u` – add all already-tracked files
* `git add .` – add all files from the current directory, also untracked
* `git checkout [branch-name]` – switch to branch `[branch-name]`
* `git commit -a` – commits changes to all tracked files (not only in the current directory)
* `git commit -m "[msg]"` – commit with message `[msg]`
* `git merge [branch-name]` – merge current branch with branch `[branch-name]`
* `git push` – push local to to the corresponding remote branch
* `git push origin [branch-name]` – push only branch `[branch-name]`
* `git rebase [branch-name]` – moves the entire current branch to the tip of `[branch-name]`
</br>

* `git log`
* `git pull` (this is `git fetch` followed by `git merge` to the current local branch)
* `git reset --hard origin/master` – remove all local changes
* `git rm [file]` – remove `[file]`
* `git rm --cached [file]` – stop `[file]` from being tracked

### GitFlow

[GitFlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow): workflow model based on branches.

* **master** branch: releases with version numbers (main branch number 1)
* **develop** branch: integration branch for features (main branch number 2)
<br />

* **feature**: branched out of and into develop, single feature = single branch
* **hotfix**: quick patches, the only branch out of master, merged both with master and develop/release
* **release**: branched out of develop, no new features can be added, merged into master when ready to ship, next also merged back into develop

This is in opposition to a [centralized](https://www.atlassian.com/git/tutorials/comparing-workflows) (SVN-like) workflow, where all features are branched out of and merged into a single master branch.
