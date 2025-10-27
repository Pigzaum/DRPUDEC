# Benchmark instances and detailed results for the DRPUDEC paper

This repository contains all benchmark instances and the complete set of detailed results associated with the paper:

> **"A Dynamic Drone Routing Problem with Uncertain Demand and Energy Consumption" [[1](#references)]**

The benchmark instances are derived from those of Ulmer and Thomas [[2](#references)], which we obtained directly from the first author. They provided 400 instances with 500 customers each: 200 generated using a uniform distribution and 200 using a normal distribution for customer coordinates. From each set of 200, we randomly selected 50 and adapted them for use in this study.

First, we reduced all pairwise distances by 15% to account for the fact that Ulmer and Thomas [[2](#references)] designed the original instances for a heterogeneous fleet (drones and ground vehicles), whereas our model only considers drones. After scaling the distances, we removed all unreachable customers, i.e., customers who cannot be served via a drone round trip due to battery limitations.

Then, we randomly sampled customers and created three sets of instances with $m \in \{200, 300, 400\}$, resulting in a total of 300 instances. In each instance, a customer node $r$ is assigned:

- A demand $q_r \in [0.225\text{ kg}, 1.5\text{ kg}]$;
- A service time $\eta = 3$ minutes;
- A time of appearance $a_r$, randomly selected in $(0, T - 240\text{ min}]$;
- A soft deadline $l_r = a_r + 240\text{ min}$.

The instances were solved using:
- $n = 12$ drones for $m = 200$;
- $n = 18$ drones for $m = 300$;
- $n = 24$ drones for $m = 400$.

---

## Instances

The benchmark instances are located in the `instances/` folder, organized into three subfolders:
- `200/`: Instances with 200 customers;
- `300/`: Instances with 300 customers; 
- `400/`: Instances with 400 customers.

---

## Results

The file [`results/DRPUDEC_detailed_results.ods`](results/DRPUDEC_detailed_results.ods) contains the detailed outcomes of our experiments for all tested configurations.

---

## References

**[\[1\] G. O. Chagas, L. C. Coelho, D. Laganà and P. Beraldi. A dynamic drone routing problem with uncertain demand and energy consumption. Transportantion Rsearch Part B: Methodological, 202:103335, 2025]( https://doi.org/10.1016/j.trb.2025.103335)**

**[\[2\] M. W. Ulmer and B. W. Thomas. Same-day delivery with heterogeneous fleets of drones and vehicles. Networks, 72(4):475–505, 2018]( https://doi.org/10.1002/net.21855)**

