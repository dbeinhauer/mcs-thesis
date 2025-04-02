# Intro
- review the problem description section
    - mainly check the references
- refine the project overview
- refine the results part
- refine the thesis structure part

# CH1
- add pictures:
    - neuron description
    - action potential
        - the diagram in time
        - maybe diagram of the potential propagation and some ion channels
    - myelination and saltatory conduction
    - synaptic transition diagram
        - maybe also inhibitory and excitatory
        - maybe combination of the signals
    - early visual system
        - general structure
    - eye - description
    - retina - diagram of different cells
        - maybe also fovea, blind spot etc.
    - LGN - diagram of the structure and path to V1
    - V1 - layers
        - other paths to different regions
        - location in head
    - retinoscopy - visual field
    - orientation selectivity
        - simple and complex cells
        - orientation map
    - maybe binocularity and direction specificity (not needed imho)
    - diagram of pathways to higher regions

- modeling approaches
    - classical approaches
    - SNNs
    - DNNs
- ML
    - RNNs, LSTMs
    - some techniques
    - Pearson's CC
    - Normalized CC (maybe in results)
# CH2
- problem and solution description

# CH3
- analysis and results


# Chapter 2 - Computational neuroscience
- mention RNNs
- mention synaptic adaptation and biological plausibility
- SNNs
- metrics:
    - Pearson's, Normalized CC
- mention blank stimuli
- 


# Model definition
- define the dataset
- define the task
- define base model architecture
    - outer RNN
    - how it is connected
    - mathematical description of the model
- define model variants
    - ideally also mathematically and mention the motivation behind each of the model (the biological motivation)




# Experimental outline
- some dataset analysis
- maybe need to generate more model subsets - how many of them?
    - ideally around 20
- comparison of all models (`simple`, `dnn_joint`, `dnn_separate`, `rnn_joint`, `rnn_separate`, `syn_adaptation`, `syn_adaptation_lgn`)
    - how to compare the results: using `CC_NORM`
        - it is worth to do the comparison to use also `CC_ABS`
            - maybe experiment on all variants of the model with same parameters to check the validity
- model parameters check:
    - different learning rates - probably test all on the `dnn_joint` model
- for `rnn` models - it would be nice to also compare different `TBTT`
- compare also the temporal behavior of the responses
    - `at least population behavior`
    - if there is a time also show the neurons itself or across all images
    - good to have some measure of temporal dynamic capture
        - difference of the spike
        - somehow measure the difference between the steady state and the blank state
- if possible then also `dnn_joint` plot of the neuron behavior to show what function it learned
- comparison for `different model sizes`
    - probably only for one setup
- comparison for `different train set sizes`
- comparison for `different time step size`






https://nba.uth.tmc.edu/neuroscience/m/s2/chapter15.html
https://dspace.cuni.cz/handle/20.500.11956/176078
https://dspace.cuni.cz/handle/20.500.11956/183997
