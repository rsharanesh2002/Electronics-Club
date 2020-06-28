# Using FreeRTOS multi-tasking in Arduino
## Description
The Arduino IDE and environment has many drivers and libraries available within an arm's reach, but the Arduino environment is limited to just setup() and loop() and doesn't support multitasking effectively. This is a simple, easy to use and robust FreeRTOS implementation that can just shim into the Arduino IDE as a Library and allow the use of the best parts of both environments, seamlessly. By implementing the above, we can perform multi-tasking in Arduino.
To implement the process of Real-Time Operating System, we just include the RTOS library  #include <Arduino_FreeRTOS.h> at the start of the sketch. That’s all there is to having FreeRTOS running in your sketches.If we write out any code that does perform two different tasks then both the tasks perform their duties, managed by the FreeRTOS scheduler.
## What is Multitasking?
Most operating systems appear to allow multiple programs or threads to execute at the same time. This is called multi-tasking. In reality, each processor core can only be running a single program at any given point in time. A part of the operating system called the scheduler is responsible for deciding which program to run when and provides the illusion of simultaneous execution by rapidly switching between each program.
## Why RTOS?
The scheduler in a Real-Time Operating System (RTOS) is designed to provide a predictable (normally described as deterministic) execution pattern. This is particularly interesting for embedded systems, like the Arduino devices, as embedded systems often have real-time requirements.
Traditional real-time schedulers, such as the scheduler used in FreeRTOS, achieve determinism by allowing the user to assign a priority to each thread of execution. The scheduler then uses the priority to know which thread of execution to run next. In FreeRTOS, a thread of execution is called a Task.
## What is a Scheduler in an OS?
The process scheduling is the activity of the process manager that handles the removal of the running process from the CPU and the selection of another process on the basis of a particular strategy.
Process scheduling is an essential part of Multi-programming operating systems. Such operating systems allow more than one process to be loaded into the executable memory at a time and the loaded process shares the CPU using time multiplexing.
Schedulers are special system software that handles process scheduling in various ways. Their main task is to select the jobs to be submitted into the system and to decide which process to run. 
Schedulers are of three types −
1. Long-Term Scheduler
2. Short-Term Scheduler
3. Medium-Term Scheduler
