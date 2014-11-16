The Cigarette Smokers Problem
====

Consider a simulation with three smoker threads and one agent thread.
 
* Each smoker continuously makes a cigarette and smokes it. 
But to make a cigarette, a smoker needs three ingredients: tobacco, paper, and matches. 
One of the smoker threads has only paper, another has only tobacco, and the third has only matches.
* The agent thread has an infinite supply of all three materials. 

1. The three smoker threads are initially blocked. 
2. The agent places two randomly chosen (different) ingredients on the table and unblocks the one smoker who has the remaining ingredient. 
3. The agent then blocks. 
4. The unblocked smoker 
    1. removes the two ingredients from the table, 
    2. makes a cigarette, and smokes it for a random amount of time, 
    3. unblocking the agent on completion of smoking the cigarette. 
5. The agent then puts out another random two of the three ingredients, and the cycle repeats.

* Write a multi-class multi-threaded Java program that uses a monitor to synchronize the agent thread and the three smoker threads. 
    * Do not mechanically translate semaphore code into monitor code! 
* The agent thread executes in an agent object created from an agent class. 
* Each smoker thread executes in a smoker object. 
* All smoker objects are created from one smoker class 
    whose constructor is used to specify the ingredient possessed by the smoker object. 
* A driver class with a main method constructs the objects and starts the threads. 
* Use a single monitor object instantiated from a class Control for synchronization. 
* Each of the four threads invokes a synchronized monitor method for its synchronization. 
* No semaphores are allowed. No synchronized blocks are allowed, only synchronized methods. 
* No busy waiting is allowed. 
* No calls to nap inside a synchronized method are allowed (do not nap while holding the monitor object's lock, that is, while inside
a synchronized method or while inside a method called by a synchronized method). 