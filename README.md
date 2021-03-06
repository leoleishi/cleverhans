# cleverhans (v1.0.0)

<img src="https://github.com/openai/cleverhans/blob/master/logo.png?raw=true" alt="cleverhans logo">

This repository contains the source code for `cleverhans`, a Python library to
benchmark machine learning systems' vulnerability to
[adversarial examples](http://karpathy.github.io/2015/03/30/breaking-convnets/).

The `cleverhans` library is under continual development, always welcoming
contributions of the latest attacks and defenses.

## Setting up `cleverhans`

### Dependencies

This library uses `TensorFlow` to accelerate graph computations performed by
many machine learning models. Some models are also defined using `Keras`.
Installing these libraries with GPU support is recommended for performance.
Note that you should **configure Keras to use the TensorFlow backend**, as
explained [on this page](https://keras.io/backend/). Installing `TensorFlow`
and `Keras` will take care of all other dependencies like `numpy` and `scipy`.

### Updating the `PYTHONPATH` environment variable

On UNIX machines, it is recommended to add your clone of this repository to the
`PYTHONPATH` variable so as to be able to import `cleverhans` from any folder.

```
export PYTHONPATH="/path/to/cleverhans":$PYTHONPATH
```

You may want to make that change permanent through your shell's profile.

## Tutorials

To help you get started with the functionalities provided by this library, it
comes with the following tutorials:
* **MNIST with FGSM** ([code](tutorials/mnist_tutorial.py), [tutorial](tutorials/mnist_tutorial.md)): this first
tutorial covers how to train a MNIST model using TensorFlow,
craft adversarial examples using the [fast gradient sign method](https://arxiv.org/abs/1412.6572), 
and make the model more robust to adversarial
examples using adversarial training.
* **MNIST with JSMA** ([code](tutorials/mnist_tutorial_jsma.py), [tutorial](tutorials/mnist_tutorial_jsma.md)): this second
tutorial covers how to train a MNIST model using TensorFlow and
craft adversarial examples using the [Jacobian-based saliency map approach](https://arxiv.org/abs/1511.07528). 
* more to come soon...
 
## Reporting benchmarks

When reporting benchmarks, please:
* Use a versioned release of `cleverhans`.
* Either use the latest version, or, if comparing to an earlier publication, use the same version as the earlier publication.
* Report which attack method was used.
* Report any configuration variables used to determine the behavior of the attack.

For example, you might report "We benchmarked the robustness of our method to adversarial attack using v1.0.0 of `cleverhans`. On a test set modified by the `fgsm` with `eps` of 0.3, we obtained a test set accuracy of 71.3%."

## Contributing

Contributions are welcomed! We ask that new efforts and features be coordinated
on the mailing list for `cleverhans` development: [cleverhans-dev@googlegroups.com](https://groups.google.com/forum/#!forum/cleverhans-dev). 
Bug fixes can be initiated through Github pull requests.

## About the name

The name `cleverhans` is a reference to a presentation by Bob Sturm titled “Clever Hans, Clever Algorithms: Are Your Machine Learnings Learning What You Think?" and the corresponding publication, ["A Simple Method to Determine if a Music Information Retrieval System is a 'Horse'."](http://ieeexplore.ieee.org/document/6847693/) Clever Hans was a horse that appeared to have learned to answer arithmetic questions, but had in fact only learned to read social cues that enabled him to give the correct answer. In controlled settings where he could not see people's faces or receive other feedback, he was unable to answer the same questions. The story of Clever Hans is a metaphor for machine learning systems that may achieve very high accuracy on a test set drawn from the same distribution as the training data, but that do not actually understand the underlying task and perform poorly on other inputs.

## Authors

This library is managed and maintained by Ian Goodfellow (OpenAI),
Nicolas Papernot (Pennsylvania State University), and
Ryan Sheatsley (Pennsylvania State University).

The following authors contributed (ordered according to the GitHub contributors page):
* Nicolas Papernot (Pennsylvania State University)
* Ian Goodfellow (OpenAI)
* Ryan Sheatsley (Pennsylvania State University)
* Reuben Feinman (Symantec)

## Citing this work

If you use `cleverhans` for academic research, you are highly encouraged 
(though not required) to cite the following paper:

```
@article{papernot2016cleverhans,
  title={cleverhans v1.0.0: an adversarial machine learning library},
  author={Papernot, Nicolas and Goodfellow, Ian and Sheatsley, Ryan and Feinman, Reuben and McDaniel, Patrick},
  journal={arXiv preprint arXiv:1610.00768},
  year={2016}
}
```

A new version of the technical report will be uploaded for each major
revision. GitHub contributors will be added to the author list.

## Copyright

Copyright 2016 - OpenAI and Pennsylvania State University.
