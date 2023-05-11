# Robust Drone-Vehicle Routing Problem Instances

This repository contains problem instances and solutions for the working paper "An Exact Algorithm for Robust Drone-Vehicle Routing Problem with Time Windows" written by Jaegwan Joo and Chungmok Lee.

## Instances

- UPS Instances: Randomly generated from a real-life use case of UPS in the area of NC, US. Refer to Kang and Lee (2020) for details.
- Solomon Instances: Well-known VRPTW instances by Solomon (1987).

## Solution file format

Each JSON file contains the following information:

{
- "problem": {
  - "name": *problem name*, 
  - "datafile": *data file name*, 
  - "num_cust_nodes": *number of customers*, 
  - "num_tot_nodes": num_cust_nodes + 2 *(including depots)*, 
  - "Gamma": *𝚪*, 
  - "t_range": *coefficient for truck's travel time uncertainty*, 
  - "Delta": *𝛥*, 
  - "d_range": *coefficient for drone's flight time uncertainty*, 
  - "num_drones": *number of drones*, 
  - "drone_time_multiplier": *a constant to be multiplied to drone's flight time*, 
  - "drone_cost_multiplier": *a constant to be multiplied to drone's cost*, 
  - "flight_limit": *drone's maximum flight range*, 
  - "demand_ratio": *drone's demand limit ratio*
  }, 
- "timelimit": *time mimit in seconds*, 
- "num_cpus": *numbe of threads*, 
- "alg": *name of algorithm*, 
- "root_LP": *root LP bound*, 
- "tot_cg_iterations": *total number of CG iterations*, 
- "global_lb": *global lower bound*, 
- "time": *solving time in seconds*, 
- "obj": *best integer objective value*, 
- "tot_mp_time": *total time spent for solving MP*, 
- "tot_sp_time": *total time spent for solving SP*, 
- "tot_sp_heu1_time": *total time spent for solving SP-heuristic 1*, 
- "tot_sp_heu2_time": *total time spent for solving SP-heuristic 2*, 
- "tot_sp_exact_time": *total time spent for solving SP-exact*, 
- "tot_num_sp_heu1": *total number of solving SP-heuristic 1*, 
- "tot_num_sp_heu2": *total number of solving SP-heuristic 2*, 
- "tot_num_sp_exact": *total number of solving SP-exact*, 
- "tot_sp1_time": *total time spent for solving SP1 (summed for all threads)*,
- "tot_sp2_time": *total time spent for solving SP2 (summed for all threads)*,
- "tot_heu_time": *total time spent for solving primal heiristic*,
- "raw_solution": *[value, truck pattern, [drone patterns]]*,
- "solution": *[truck pattern, [drone dispatching sequences]]*,
- "num_bnb_nodes": *number of explored BnB nodes*, 
- "num_bnb_remaining_nodes": *number of remaining BnB nodes*, 
- "tot_num_gen_cols": *total number of generated columns*,  
- "tot_num_labels": *total number of generated labels(truck routes)*,  
- "termination_status": *solution status*
}

## References

- Kang, Munjeong, and Chungmok Lee. "An exact algorithm for heterogeneous drone-truck routing problem." Transportation Science 55, no. 5 (2021): 1088-1112.
- Solomon,  Marius M. "Algorithms for the Vehicle Routing and Scheduling Problems with Time Window Constraints." Operations Research 35, no, 2 (1987): 254–265.

