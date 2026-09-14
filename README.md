# GA-PSO-Delivery-Location-Optimization
Optimization of delivery location selection using Genetic Algorithm (GA) and Binary Particle Swarm Optimization (PSO), considering vehicle capacity, parcel priority, and travel distance. Implemented in Python using Google Colab.

# GA vs Binary PSO – Delivery Location Optimization

## Overview

This project applies **Genetic Algorithm (GA)** and **Binary Particle Swarm Optimization (PSO)** to solve a delivery location selection problem in Kuala Lumpur.

The objective is to select the best combination of delivery locations while considering:

* 🚚 Maximum van capacity: **75 kg**
* 📦 Parcel weight
* ⭐ Delivery priority
* 📍 Travel distance from the depot

The depot is located at **Masjid India, Kuala Lumpur**, with 8 possible delivery locations.

## Problem

The delivery company needs to determine which locations should be selected for delivery. The total parcel weight must not exceed the van's 75 kg capacity while maximizing delivery priority and minimizing travel distance.

The fitness function used is:

```text
Fitness = Total Priority Score - Total Distance - Penalty
```

A penalty is applied when the selected parcel weight exceeds the van capacity.

## Algorithms

### Genetic Algorithm (GA)

The GA uses:

* Binary chromosome representation
* Population size: 20
* 40 generations
* Roulette wheel selection
* Single-point crossover
* Crossover rate: 0.85
* Bit-flip mutation
* Mutation rate: 0.05

### Binary Particle Swarm Optimization (PSO)

The Binary PSO uses:

* Binary particle representation
* 20 particles
* 40 iterations
* Inertia weight (w): 0.70
* Cognitive coefficient (c1): 1.50
* Social coefficient (c2): 1.50
* Sigmoid function for binary position updates

## Dataset

| Location     | Distance (km) | Weight (kg) | Priority |
| ------------ | ------------: | ----------: | -------: |
| KLCC         |           3.2 |          12 |        5 |
| Chow Kit     |           2.1 |           8 |        3 |
| Titiwangsa   |           4.5 |          15 |        4 |
| Ampang       |           7.8 |          10 |        5 |
| Wangsa Maju  |           9.2 |          20 |        2 |
| Setapak      |           8.5 |           9 |        3 |
| Kampung Baru |           1.8 |          14 |        5 |
| Brickfields  |           5.3 |          11 |        4 |

The total weight of all parcels is **99 kg**, which exceeds the 75 kg vehicle capacity. Therefore, an optimization algorithm is required to determine the most suitable combination of locations.

## Results

| Criteria           |      GA |  Binary PSO |
| ------------------ | ------: | ----------: |
| Best Fitness       |   279.9 |   **283.3** |
| Total Weight       |   71 kg |   **70 kg** |
| Priority Score     | **311** |         308 |
| Total Distance     | 31.1 km | **24.7 km** |
| Selected Locations |       6 |           6 |
| Within Capacity    |     Yes |         Yes |

### Best GA Solution

```text
[1, 0, 1, 1, 0, 1, 1, 1]
```

Selected locations:

**KLCC, Titiwangsa, Ampang, Setapak, Kampung Baru, Brickfields**

Fitness: **279.9**

### Best Binary PSO Solution

```text
[1, 1, 1, 1, 0, 0, 1, 1]
```

Selected locations:

**KLCC, Chow Kit, Titiwangsa, Ampang, Kampung Baru, Brickfields**

Fitness: **283.3**

## Conclusion

Binary PSO achieved a higher fitness value and a shorter total travel distance compared with GA. Both algorithms successfully produced feasible solutions within the 75 kg vehicle capacity. Based on the results, **Binary PSO performed better for this delivery location optimization problem**.

## Technologies

* Python
* NumPy
* Pandas
* Matplotlib
* Google Colab

## File

`GA_PSO_Delivery_Optimization.ipynb` — Google Colab notebook containing the implementation, calculations, visualizations, and comparison of GA and Binary PSO.

