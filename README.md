# Genetic-Algorithm

The goal of this project is to perform simple experiments using a genetic algorithm (GA). The experiment should compare related evolutionary processes, i.e., how fitness or other factors evolve, for different evolutionary models.

## Abstract

This study analyzes the efficacy of a simple genetic algorithm (GA) built around evolving a population of genomes to a target sequence consisting of all ‘A’s. It uses **tournament selection, single-point crossover, and random mutation** as method components. The main goal is to determine how **population size and mutation rates** affect the smoothness of the fitness curves over generations.  

These results suggest that **larger population sizes, lower mutation rates, and the use of elitism together** greatly contribute to smoother fitness progression. The experiment elucidates how a simple GA works and enhances the understanding of **parameter tuning** for achieving desired evolutionary outcomes.

---

## Experiment Description  

The goal of the experiment is to see how effective a **genetic algorithm** is in evolving a population of genomes toward a final sequence of all 'A's. The algorithm **mimics natural selection** by ensuring that better individuals have a greater chance of reproducing and passing on their genetic information.  

### Hypothesis  
Smoother, upward-sloping fitness graphs will be produced by **increasing population size and lowering mutation rates**, indicating overall improvement in the **average fitness** of the population over generations.  

### Variables  

- **Independent Variables:**  
  - Population size  
  - Mutation rate  

- **Dependent Variable:**  
  - Average fitness of the population over generations  

---

## Algorithm Description  

The genetic algorithm implemented in this experiment comprises the following key components:

### **1️⃣ Individual Representation**  
- Each individual in the population is represented by a **genome**, which is a sequence of characters chosen from the set `['A', 'T', 'G', 'C']`.  
- The **genome length is fixed** (e.g., 10 in the initial code, but adjustable).  

### **2️⃣ Fitness Function**  
- The `calcFitness()` function is called for each individual.  
- It iterates through the individual's genome (a list of characters) and **counts the occurrences of the letter 'A'**. This count is then assigned as the individual's **fitness score**.  
- **Formula:**  
  ```python
  self.fitness = self.genome.count('A')



## 🧬 Initialization

- **Random Generation**: Initial individuals are generated **randomly**.
- **Genome Representation**: Each individual's **genome** consists of a sequence of bases randomly chosen from `['A', 'T', 'G', 'C']`.
- **Genome Length**: The genome length is **fixed** but adjustable.
- **Implementation**:  
  - Inside the `indiv` class constructor (`__init__`), a **loop iterates `genomeLength` times**, selecting a random character from the base set.
  - Population size (`popSize`) is typically set to **100 or higher**.

---

## 🎯 Selection: Tournament Selection

- The **`tourn()` function** implements a **tournament selection** process.
- **Process**:
  - Randomly selects **multiple individuals** from the population.
  - **Compares their fitness** values.
  - The individual with the **highest fitness** in the tournament is selected as a **parent** for the next generation.
- **Tournament size** is **adjustable** (default = `6`).

---

## 🔗 Crossover: Single-Point Crossover

- **Single-point crossover** is used to generate offspring.
- **Process**:
  - A **random crossover point** is selected within the genome.
  - Genome segments **after the crossover point** are swapped between **two parents** to generate new offspring.

---

## 🔄 Mutation: Random Mutation

- **Mutation introduces genetic diversity** in offspring.
- **Process**:
  - For each **position** in the offspring’s genome:
    - A **random number** between `0` and `1` is generated.
    - If the number is **less than `mutationRate / 100`**, the base at that position is **mutated** by selecting a **new random base** from `['A', 'T', 'G', 'C']`.
- **Implemented in the `mutate2()` function**.

---

## 📈 Plotting the Results

- **Matplotlib** was used to **visualize the evolutionary progress**.
- **`plot_results()` function** generates graphs illustrating **fitness trends** over generations.
- **Graph Axes**:
  - **X-axis** → **Generations**
  - **Y-axis** → **Fitness**

---

## 📊 Summary of Key Parameters

| Parameter        | Value(s)          |
|-----------------|------------------|
| Genome Bases    | `['A', 'T', 'G', 'C']` |
| Population Size | `100` |
| Mutation Rate   | `1, 10, 20` |
| Crossover Rate  | `100%` |
| Tournament Size | `6` |
| Generations     | `100` |

---
## Output/Result
![](https://github.com/sthasafal/Genetic-Algorithm/blob/main/GeneticAlgorithm.png)

## Observations from Graphs: 
-	Larger population sizes lead to smoother fitness curves with less fluctuation.
-	Lower mutation rates result in a more gradual and consistent increase in average fitness.
-	There appears to be an optimal balance between population size and mutation rate for achieving the smoothest upward trend in fitness.
-	While the fitness curve exhibited some fluctuations, the overall upward trend demonstrated the algorithm's effectiveness in guiding the population towards increasingly better solutions over successive generations.
-	By comparing the fitness curves created with different settings, we can learn how things like population size and mutation rate change the algorithm's progress

## Conclusion
Our evolutionary algorithm could develop genomes toward a target of all 'A's. Sufficiently larger populations created more smooth and anticipatable improvement in fitness, corroborating the necessity to maintain genetic diversity. Lower rates of mutation, particularly in the vicinity of 1%, fostered incremental and consistent progress, exemplifying the sensitive balance between exploitation and exploration. Overall, our experiment suggested that genetic algorithms are powerful tools, but precise tuning of parameters like population size and mutation rate is important for optimum results. This research gives useful insights regarding the working of genetic algorithms and how they can be used to solve different kinds of problems.



