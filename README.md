## Dictionary 

This is simple and generic dictionary. You can instantiate multiple dictionaries with
the constructor. See interface below.

Each dictionary has space for 1000 elements. 

You need add the files **dic.c** and **dic.h** in your project directory.
After that you include dic.h

### Overview about functions

``` c
Dictionary * create_dict(void);
```
create_dict: is a simple constructor for creating 
​             a dictionary and setting up the 
​             member field 'number_of_elements'
​             and prepares the inner array 'elements'

``` c
int add_item_label(Dictionary *,char label[],void *);
```
add_item_label: adds item (void*) to the dictionary at given label 
​                returns 0 if adding was sucessful otherwise -1


``` c
int add_item_index(Dictionary *, int index, void *);
```
 add_item_index: adds item (void*) to the dictionary at given index (int) 
​                returns 0 if adding was sucessful otherwise -1

``` c
void * get_element_label(Dictionary *, char []);
```
get_element: returns the element at given label 


``` c
void * get_element_index(Dictionary *, int);
```
get_element: returns the element at given index 


``` c
void destroy(Dictionary *);
```
simple destructor function for avoiding memory leaks.



## Build && Install

```
➜  dictionary-C git:(master) ✗ ./configure 
checking for a BSD-compatible install... /usr/bin/install -c
checking whether build environment is sane... yes
checking for a thread-safe mkdir -p... ./install-sh -c -d
checking for gawk... no
checking for mawk... no
checking for nawk... no
checking for awk... awk
checking whether make sets $(MAKE)... yes
checking for gcc... gcc
checking whether the C compiler works... yes
checking for C compiler default output file name... a.out
checking for suffix of executables... 
checking whether we are cross compiling... no
checking for suffix of object files... o
checking whether we are using the GNU C compiler... yes
checking whether gcc accepts -g... yes
checking for gcc option to accept ISO C89... none needed
checking for style of include used by make... GNU
checking dependency style of gcc... gcc3
checking how to run the C preprocessor... gcc -E
checking for grep that handles long lines and -e... /usr/bin/grep
checking for egrep... /usr/bin/grep -E
checking for ANSI C header files... yes
checking for sys/types.h... yes
checking for sys/stat.h... yes
checking for stdlib.h... yes
checking for string.h... yes
checking for memory.h... yes
checking for strings.h... yes
checking for inttypes.h... yes
checking for stdint.h... yes
checking for unistd.h... yes
checking for stdlib.h... (cached) yes
checking for stdlib.h... (cached) yes
checking for GNU libc compatible malloc... yes
checking that generated files are newer than configure... done
configure: creating ./config.status
config.status: creating Makefile
config.status: creating config.h
config.status: executing depfiles commands
➜  dictionary-C git:(master) ✗ make
/Applications/Xcode.app/Contents/Developer/usr/bin/make  all-am
gcc -DHAVE_CONFIG_H -I. -I ./src    -g -O2 -Wall -MT dict.o -MD -MP -MF .deps/dict.Tpo -c -o dict.o `test -f 'src/dict.c' || echo './'`src/dict.c
mv -f .deps/dict.Tpo .deps/dict.Po
gcc -DHAVE_CONFIG_H -I. -I ./src    -g -O2 -Wall -MT test_program.o -MD -MP -MF .deps/test_program.Tpo -c -o test_program.o `test -f 'src/test_program.c' || echo './'`src/test_program.c
mv -f .deps/test_program.Tpo .deps/test_program.Po
gcc  -g -O2 -Wall   -o dict_demo dict.o test_program.o  
➜  dictionary-C git:(master) ✗ ./dict_demo 
My age is 28
My name is Christian
My age at index 0 is 28
```

