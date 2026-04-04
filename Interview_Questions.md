# Interview Questions 2 - 2026

# Siemens

<span style="color: red;">1) Explain how virtual pointer used vptr and vtable ?</span>
<span style="color: red;">2) Explain about Dynamic casting?</span>

<span style="color: red;">3) What is RAII?</span>

<span style="color: green;">Answer:</span>
<span style="color: green;">RAII stands for "Resource Acquisition Is Initialization" ✅</span>
<span style="color: green;">When an object is created, resources are acquired in the constructor ✅</span>
<span style="color: green;">When the object goes out of scope, resources are released in the destructor ✅</span>
<span style="color: green;">This ensures automatic and exception-safe resource management ✅</span>

<span style="color: green;">Example resources:</span>

<span style="color: green;">- Memory</span>
<span style="color: green;">- File handles</span>
<span style="color: green;">- Mutexes</span>
<span style="color: green;">- Network sockets</span>

<span style="color: red;">4) What is Deep copy and Shallow copy?</span>

<span style="color: red;">5) Explain the memory layout code code?</span>
<span style="color: green;">Answer: Code, Data, Heap and Stack section.</span>

<span style="color: red;">6) Explain the line:</span>
<span style="color: red;">	int a = 10;</span>
<span style="color: red;">	ptr = new int(a);</span>

<span style="color: green;">Answer:</span>
<span style="color: green;">A memory of size 4 bytes is created and it has a value same as "a". Do not get confused; it is not pointing to a.</span>
<span style="color: green;">Similarly, unique_ptr<int> uptr = make_unique<int>(10); means variable of size 4 bytes is created and it contains value of 10.</span>

<span style="color: red;">7) Tell the size of following class:</span>
<span style="color: red;">a) class empty{};</span>
<span style="color: red;">b) class abc{ int a; };</span>
<span style="color: red;">c) class def{ int a; empty e; };</span>

<span style="color: green;">Answer (with or without padding):</span>

| <span style="color: green;">Class</span> | <span style="color: green;">Without Padding</span> | <span style="color: green;">With Padding</span> |
| --- | --- | --- |
| <span style="color: green;">empty</span> | <span style="color: green;">1 byte</span> | <span style="color: green;">1 byte</span> |
| <span style="color: green;">abc</span> | <span style="color: green;">4 bytes</span> | <span style="color: green;">4 bytes</span> |
| <span style="color: green;">def</span> | <span style="color: green;">5 bytes</span> | <span style="color: green;">8 bytes</span> |