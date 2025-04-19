# SVM hyperparameter Optimization

This project involves optimizing a Support Vector Machine (SVM) classifier using the Optuna library for hyperparameter tuning on a multi-class dataset. The main objective is to achieve the best classification accuracy by systematically tuning the SVM's kernel, `C`, and `gamma` values.

---

## Methodology

### Dataset Selection & Preprocessing

- A multi-class dataset from the UCI Machine Learning Repository was used.
- Dataset size: ~5,000 to 30,000 samples
- The dataset was split into 10 random train-test sets (70% train, 30% test), labeled from `S1` to `S10`.

### Model & Optimization Strategy

- Classifier: Support Vector Machine (SVM)
- Hyperparameter tuning performed using [Optuna](https://optuna.org/)
- Parameters optimized:
  - `kernel`: `'rbf'` or `'poly'`
  - `C`: Regularization parameter
  - `gamma`: Kernel coefficient (for both `rbf` and `poly`)
- Each split was optimized for 100 iterations using `study.optimize()` from Optuna.

---

## Evaluation Strategy

For each of the 10 splits:
- Recorded best test accuracy
- Logged best hyperparameter combination
- The sample with the highest accuracy was chosen for detailed convergence graph analysis

---

## Results Summary

| Sample | Best Accuracy (%) | Best SVM Parameters |
|--------|-------------------|----------------------|
| S1     | 63.54             | Kernel: `rbf`, C: 8.811, Gamma: 0.00298 |
| S2     | 61.25             | Kernel: `rbf`, C: 3.0188, Gamma: 0.09086 |
| S3     | 60.42             | Kernel: `rbf`, C: 1.7888, Gamma: 0.05165 |
| S4     | 66.88             | Kernel: `rbf`, C: 49.4097, Gamma: 0.06708 |
| S5     | 64.38             | Kernel: `rbf`, C: 6.0602, Gamma: 0.04667 |
| S6     | 65.42             | Kernel: `rbf`, C: 4.6435, Gamma: 0.08755 |
| S7     | 63.96             | Kernel: `poly`, C: 95.3259, Gamma: 0.02517 |
| S8     | 63.33             | Kernel: `rbf`, C: 31.381, Gamma: 0.09886 |
| S9     | 63.96             | Kernel: `rbf`, C: 2.4908, Gamma: 0.05054 |
| S10    | 65.21             | Kernel: `rbf`, C: 12.8308, Gamma: 0.0682 |

---

## Convergence Graph – Best Sample: `S4`

This graph shows the progression of accuracy over 100 optimization trials using Optuna.  

- Blue dots represent accuracy values for each trial.
- Red line shows the best-so-far accuracy (running maximum).

> The optimization converged rapidly within the first 20 iterations, eventually reaching an optimal test accuracy of 66.88%.

### Convergence Graph

![Convergence Graph for S4]![graph](https://github.com/user-attachments/assets/cb6c25f2-ddf2-414f-95af-0d9d17e84009)


---

## Output table

This is the output result of the best model,:

![Sample Output Result]![output table](https://github.com/user-attachments/assets/e72c32b3-4647-4341-b826-0b7d06ddff78)


---

## References

- UCI Machine Learning Repository: [https://archive.ics.uci.edu/](https://archive.ics.uci.edu/)
- Optuna Documentation: [https://optuna.readthedocs.io/](https://optuna.readthedocs.io/)

