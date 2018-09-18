# FreeRTOS
## Basic Information
FreeRTOS is a real-time operating system kernel for  embedded devices which has been ported to 35 microcontrollers.
It is distributed under the MIT License.

## Implementation
Its goal is to be small and simple. That is why it consists of only three C files. To keep it readable and easy to maintain it is mostly written in C, only few parts are assembly functions (e.g. in architecture-specific scheduler routines).

FreeRTOS provides methods for multiple threads or tasks, mutexes, semaphores and software timers. A tick-less mode is provided for low power applications. Also thread priorities are supported. FreeRTOS applications can be completely statically allocated or dynamically allocated with five schemes of memory allocation:

* allocate only
* allocate and free with a very simle, fast, algorithm
* a more complex but fast allocate and free alforith with memory coalescence
* an alternative to the more complex scheme that includes memory coalescence that allows a heap to be broken across multiple memory areas
* and C library allocate and free with some mutual exclusion protection.

There are no advanced features typically found in operating systems like Linux or Windows, such as device drivers, advanced memory management, user account, networking, ...
The goal of FreeRTOS is to be compact, simple and fast. It can be thought of as a 'thead library' rather than an 'operating system', although command line interface and I/O abstraction add-ons are available.

# Thread Management
A thread tick methos switches tasks depending on priority and a round-robin scheduling scheme.
The usual interval is 1/1000 of a second to 1/100 of a second. It is interrupted from a hardware timer, which is often changed to suit a paricular application.
