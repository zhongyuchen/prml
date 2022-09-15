# Week 1: Outline

## Resources

* 课本：《神经网络与深度学习》（邱锡鹏著）
* Text book and slides: [nndl](https://github.com/nndl) / [nndl.github.io](https://github.com/nndl/nndl.github.io)

## Course Info

* pattern recognition == machine learning

## Machine Learning

1. input: vectors (high dimensions -> lay it flat into a one-dimensional vector)
2. goal: find out a function f() to make predictions
3. types
    * supervised learning: train with labeled training set
        + classification problem (discrete)
            - face recognition: face? Not a face? If yes, front face? profile face?
            - spam detection: spam? non-spam? How to turn a doc into a vector?
        + regression problem (continuous)
            - stock price prediction
    * unsupervised learning
        + clustering
        + ...
    * reinforcement learning

## Curve Fitting

### Basic ML Structure

1. training set: {(xi, ti)} 1 <= i <= N
2. model: y(x): x -> t, find out mapping y
    * linear: linear fitting t = Wx, where W is a (m-dimensional) vector
    * non-linear: neural network with 2 layers is already enough for any non-linear curve fitting
    * non-linear => linear: low-dimensional non-linear problem can be turned into a linear problem in higher-dimension
        + x (m-dimension) can be turned into x* (n-dimension) where n > m
        + get new elements through calculations using elements in x, and append them after x to get x*
3. criterion (how to measure success?)
    * loss function: sum of square errors E(w)
        + `partial(E(w))/partial(wi) = 0`, and get the best w with the least error
    * best coefficient (empirical risk minimum): find out `w* = arg minE(w)` to get min E(w), where `y(x) = w*x`
    * found using pseudo-inverse (more later)
4. optimization

### Problems: Model Selection

1. parameter: can be learned
    + e.g. the curve fitting vector w, where `y = wx`
2. hyper-parameter: can not be learned, must be given by human (combination optimization problem)
    + e.g. M, the rank of vector w
    + when M = 9, the fitting curve travels through all the data points => over-fitting
    + generalization error
3. generalization(泛化性)
    + 0 error in training set is useless => over-fitting
    + goal: lowest error in all(new) data, not just in training data
    + if 0 error in training set is achieved, it's very likely the model has low generalization and performs bad on other data
    + more complex, lower generalization
4. control over-fitting: regularization
    + as M increases, so do coefficient magnitudes
    + structured risk minimum: control over-fitting with lambda
    + over control: under-fitting
    + dataset size: the larger the dataset, the less likely it will be over-fitting

### Experiences: Validation Set 

1. split training data into training set and validation set
2. early stop
    - for training set, the error rate always go down
    - but for validation set, the error rate will go up at certain point
    - => this is called early-stop
    - it indicates the point it goes over-fitting
3. cross-validation
    - S groud of data, use S - 1 to train and 1 to validate
    - train and validate the model for S times
    - S times => slow

### Summary

1. model selection
    * get models that generalize to new data: high generalization
    * which model?
    * how many layers?
    * how many neurons in one layer?
    * the best combination of hyper-parameters?
2. balance optimization and regularization
3. use a validation set
4. cross-validation
    * downside: slow
5. theorems
    * Occam's Razor
    * No free lunch
    * Ugly duckling

## Decision Theory

## Probability Theory

## Conclusion
