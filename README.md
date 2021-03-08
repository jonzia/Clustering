# Unsupervised Clustering with Gaussian Mixture Modeling

## Summary
This repository contains code for performing Gaussian mixture modeling (GMM) to separate two-dimensional datasets into classes by modeling the data as samples from two or more Gaussian distributions.

## How to Use
A full description of function inputs/outputs can be viewed by using `help smart.cluster.gaussian` in the MATLAB command line. Generally, the function's inputs are the unlabeled data and model hyperparameters, and the output is a struct containing class labels for each input datapoint and the final model parameters contained in a struct. This output can be used to seed the model on subsequent function calls. The following is an example function call:

```matlab
new_model = smart.cluster.gaussian(data, true, 'startModel', old_model, 'numClusters', 3, 'iterations', 100);
labeled_data = new_model.indices; old_model = new_model.model;
```
Note that the `+cluster` package is contained within the `+smart` package for compatibility with other repositories, since they may contain other subpackages of the larger `+smart` package which rely on `+cluster` package functions. These other subpackages may be pasted in the `+smart` folder to add their respective functionality, though they will generally already contain all dependencies when cloned.

### Data Formatting
Data should be provided in a Mx2 matrix with M observations of two-dimensional data.

### Member Functions
| Function | Purpose |
| --- | --- |
| `evaluate()` | Compute the silhouette score for clustered data |
| `gaussian()` | Perform Gaussian mixture modeling |

## References
This code was used in the [linked manuscript](https://www.researchgate.net/publication/335795238_Automated_Identification_of_Persistent_Time-Domain_Features_in_Seismocardiogram_Signals), which contains a more detailed explanation of Gaussian mixture modeling.
