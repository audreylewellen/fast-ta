# Fast Threshold Acceptance for Exam Scheduling

This project implements and evaluates the Fast Threshold Acceptance (FastTA) metaheuristic for combinatorial optimization, applied to the university exam timetabling problem. FastTA is a metaheuristic that belongs to the family of Simulated Annealing, designed to efficiently explore large discrete state spaces with probabilistic cost control. As compared to classic TA, FastTA solves the problem in fewer evaluations while maintaining solution quality.

The objective is to minimize exam conflicts and back-to-back penalties over a fixed set of time slots. Each solution is a mapping of exams to slots, with cost computed via a weighted function of overlapping student enrollments and adjacency. The state space is navigated through random local changes (neighborhoods), with acceptance conditioned on a time-decaying threshold function. FastTA extends classic TA by introducing threshold binning, which tracks solution transitions across exponentially shrinking acceptance regions. 

Key components:
- Construction of co-enrollment matrix and exam size inputs
- Cost functions weighted by hard (conflicts) and soft (back-to-back) constraints
- Two initial solution heuristics: uniform random and greedy largest-degree assignment
- Full implementation of both standard TA and FastTA, with exponential threshold cooling (`T(t) = Q_max * exp(-Rt)`)
- Dynamic bin creation for FastTA, based on empirical threshold sampling
- Visualizations of convergence behavior and cost progression via `matplotlib`

The implementation uses Python and Gurobi Optimizer.

---

## Reference

This implementation is based on:

> Kahar, M. N. M., Kendall, G., & Said, S. M. (2021).  
> *A Fast Threshold Acceptance Algorithm for the Examination Timetabling Problem*.  
> [https://www.researchgate.net/publication/354600697_A_Fast_Threshold_Acceptance_Algorithm_for_the_Examination_Timetabling_Problem](https://www.researchgate.net/publication/354600697_A_Fast_Threshold_Acceptance_Algorithm_for_the_Examination_Timetabling_Problem)
