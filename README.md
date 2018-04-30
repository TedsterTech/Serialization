
# A lightweight serialization solution
There are several libraries already out there which support serialization like Protobuffer, Flatbuffers and Capnproto.
However, these need schema file for generating source files, which is cool between peers. 
But that is too heavy for me (zk4), so I wrote this lightweight version, which only supports C++.
If you just want to serialize and deserialize data on the same machine, I think that this is a good choice.
# You only need the header file:
```cpp
src/core/serialization.h 
```
And you're good to go!

# This supports: 
* vectors
* lists
* maps
* set
* strings
* primitives (integers, doubles,longs, etcetera)
* nesting container support
```cpp
Obj : implements serialize:I interface
vector<map<int, Obj*> >  
vector<vector<string> >  
vector<list<string> >  
vector<customer_struct>
vector<Obj> 
vector<string>  
```
* endian auto conversion  
  There's no need for endian concern - all data is written in little endian.


[Use characters instead of booleans in Standard Template Library](http://stackoverflow.com/questions/15809157/why-is-the-size-of-stdvectorbool-16-byte)


# How to build
you can build this project using CMake, or you can import **serialization.h** into your project.

Build process with Cmake:

```sh
	mkdir prj
	cd prj
	cmake ..
```
If this doesn't work, ensure that you're building under the C++11 spec.


# Demonstration
Check out src/testSerialization.cpp 