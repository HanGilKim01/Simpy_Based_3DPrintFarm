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
* SIM_TIME : Simulation time settings (unit : minutes)
* PALLET_SIZE_LIMIT : Maximum items in one pallet
* PROC_TIME_BUILD/WASH/DRY/INSPECT : Process time for build, wash, dry, inspect (unit :minutes)
* NUM_MACHINES_BUILD/WASH/DRY : Number of 3d print machines, wash machines, dry machines
* CAPACITY_MACHINE_BUILD/WASH/DRY : Job capacity for build, wash, dry machines
* DEFECT_RATE_PROC_BUILD : defect rate in build process
* NUM_WORKERS_IN_INSPECT : Number of workers in inspection process
* POLICY_NUM_DEFECT_PER_JOB : Number of defective items to collect for rework
* POLICY_REPROC_SEQ_IN_QUEUE : Policy for placing rework jobs in queue
* POLICY_DISPATCH_FROM_QUEUE : Policy for extracting jobs from queue
* POLICY_ORDER_TO_JOB : Policy for dividing orders into jobs: "EQUAL_SPLIT" or "MAX_PER_JOB"
* CUST_ORDER_CYCLE : Customer order cycle (1 week in minutes)
* ORDER_DUE_DATE : Order due date (1 week in minutes)

# base_Customer
* It deals with classes related to Customer
* Defines properties for Item, Patient, and Order. Create an order and assign that order

# base_Job
* Defines the properties of the job that are applied to the manufacturing process

# base_Process
* Define a large framework for the overall flow of the manufacturing process. The framework defined in that class is inherited to certain processes
* Define the connection function between processes, the processor registration function, and build a seize/delay/release process to implement the entire process.

# base_Processor
* It deals with processors (workers, machines), which are the resources of the process.
* Defines each attribute, and defines whether the processor starts and uses the task.

# config_SimPy
* It contains all parameters for the operation of the process.
* It is defined for the number of machines and workers, capacity, and processing time.

# log_SimPy
* Implement the entire log history of the simulation.
* It contains an overall statistics comprehensive and Gantchart implementation.

# main_Customer
* File for functional verification and validation of Customer part

# main_Process
* File for functional verification and validation of process part

# main_SimPy
* Proceed with the simulation for a predetermined period of time and record the results
* Sets random seeds for reproducibility

# manager
* control the manufacturing processes and track orders
* Divide the job to be done in the process, and collect the defects that occurred in the process to proceed with the rework

# specialized_Process
* Define detailed properties for the Build, Wash, Dry, Inspection process
* Organize the manner and probability of defects occurring during the Build process

# specialized_Processor
* Additional properties are defined for processors, which are workers and machines