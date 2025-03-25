# SimPy based 3D Print Farm
SimPy-based Inventory Management Simultaion

# About Simulator
* This is a company simulation that regularly takes orders from customers, prints specific products with a 3D printer, and creates the final product through a series of work processes.
* There are four major processes involved in the work process : Build, Wash, Dry, Inspection
    * The Build process implements the process in which 3D printer prints products first. During the Build process, the Build machine proceeds, and each can be done by setting job capacity. Also, during the build process, defects can occur.
    * The Wash and Dry processes represent the steps to clean and dry the printed outputs, respectively. Similarly, each works with machines and can be done by setting the job capacity.
    * Inspection implements the process of conducting the inspection before the final deliverables are completed. This process is done through a worker, and only one task per worker is implemented.

# How to set parameters
Every parameters in config_SimPy.py
* 