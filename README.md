# About
This repository contains the LaTeX sources for my master thesis.

* Implementation part available in 
[mcs-source repository](https://github.com/dbeinhauer/mcs-source).

* The PDF of the thesis is available [here](https://github.com/dbeinhauer/mcs-thesis/blob/master/thesis.pdf).

# Abstract
Recent advances in computational neuroscience and machine learning have enabled increasingly sophisticated models of neuronal systems. However, standard deep neural networks (DNNs) often prioritize task performance over biological plausibility, limiting their ability to capture complex neural dynamics.

In this thesis, we propose a novel approach that integrates biologically inspired constraints into recurrent neural network (RNN) architectures to model the primary visual cortex (V1). Using synthetic data generated from a biologically detailed spiking neural network (SNN) model of cat V1, we develop RNN architectures incorporating anatomical structure alignment, excitatory-inhibitory neuron differentiation, biologically motivated neuronal modules, and synaptic depression mechanisms.

Our results show that RNN architectures without complex internal modules can predict mean neuronal responses but struggle to capture full system dynamics. Introducing shared DNN neuron modules improves dynamics slightly, while RNN-based neuron modules substantially enhance the temporal fidelity of predictions. Conversely, synaptic depression modules did not improve performance, likely due to computational constraints and suboptimal hyperparameter tuning.

This work demonstrates the promise of combining deep learning with biological realism to bridge the gap between predictive accuracy and interpretability, laying the groundwork for future applications to real neural recordings.




# Original template
LaTeX templates are based on the (un)official MFF CUNI template for typesetting bachelor 
thesis available [here](https://github.com/mff-cuni-cz/better-thesis).