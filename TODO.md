# Intro
- review the problem description section
    - mainly check the references
- refine the project overview
- refine the results part
- refine the thesis structure part

# Chapter 1
- add pictures:
    - synaptic transition diagram
        - maybe also inhibitory and excitatory
        - maybe combination of the signals
    - LGN - diagram of the structure and path to V1
    - V1 - layers
        - other paths to different regions
        - location in head
    - retinoscopy - visual field
    - orientation selectivity
        - orientation map

# Chapter 2
- picture of leaky-integrate-and-fire as electric circuit


# Chapter 3 - Methods
- picture of dataset sequence of stimuli
- picture of single experiment
- define base model architecture
    - outer RNN
    - how it is connected
    - mathematical description of the model
    - picture of the model architecture
- define model variants
    - ideally also mathematically and mention the motivation behind each of the model (the biological motivation)




# Chapter 4: Results
- some dataset analysis
    - how many spikes in each time bins
        - histogram -> good approximation with the time step 20
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
        - it would be nice to select the highly spiking neurons and not spiking neurons on the stimulus and compare their predictions with the real measure
- if possible then also `dnn_joint` plot of the neuron behavior to show what function it learned
- comparison for `different model sizes`
    - probably only for one setup
- comparison for `different train set sizes`
- comparison for `different time step size`






https://nba.uth.tmc.edu/neuroscience/m/s2/chapter15.html
https://dspace.cuni.cz/handle/20.500.11956/176078
https://dspace.cuni.cz/handle/20.500.11956/183997
