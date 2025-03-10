# Intro
- review the problem description section
    - mainly check the references
- refine the project overview
- refine the results part
- refine the thesis structure part

# CH1
- Early visual system
    - how the signal travels
    - mainly V1
    - synaptic adaptation
    - inhibitory/excitatory neurons
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



# Chapter 1 - Biology of Visual Perception
- nearly half of the brain is responsible for visual perception

## Fields Intro
- visual fields - area perceived when the eyes are fixed
    - monocular - visible to one eye
    - `blind spot` - small area that cannot be seen
- color vision - ability to detect different wavelengths of light
    - trichromatic vision (blue, green, red)
    - mainly in the center (cones) -> peripheral areas are mainly for the light detection (rods)
        - center - works well in high illumination
    - rods are evenly distributed across the retina (except the blind spot)

## Image Formation
- curved lens -> light signal is curved

## Retina
- the innermost layer of the eye
- part of CNS
- 5 types of neurons (it would be nice to have the schema there):
    - the visual receptor cells
        - the `rods`
        - the `cones`
    - the `horizontal cells`
    - the `bipolar cells`
    - the `amacrine cells`
    - the `retinal ganglion cells`
        - only these fire action potential (rest changes in membrane potential)
    - NOTE: the cells are inside-out - receptor cells are in fact in the inner part of the layered structure
        - light needs to go around other retina neuronal cells (they are reasonably transparent)
        - reason is that pigmented epithelium - helps restoring cells (also secures other cells from light because of the pigment)
            - also minimizes the reflections of light from inside of the eye (back reflections) -> blur
- `fovea` - lot of receptor cells but less neurons (they are surround it)
    - results in thinner fovea and thicker surrounding area (the cell bodies of fovea)
        - better signal from fovea (light does not need to go through so many cells)
    - less receptor cells are connected to bipolar cells (and are mainly cones) -> sharper sight (bad in dim)
        - in contrast - more cells interconnected (with rods) in periphery -> better in weak light, not sharp (blurry) 

### Photoreceptors
- rods
    - wide wavelength range (white light - all in one)
    - more sensitive - because of the rhodopsin molecule
- cones
    - specific for wavelength (color)
    - need high illumination levels
- biochemical adaptation to light sensitivity
    - takes some time to adapt for differently illuminated areas
- normally there is circulation of Na+ - if dark -> depolarization -> neurotransmitter (glutamate)
    - when photoreceptor -> G-protein close the Na+ -> hyperpolarization -> no neurotransmitter
- light adaptation - partially by the pupil size (only factor 16)
    - major change in molecular circulation of opsine - regulators


### Visual Processing in Retina
- photoreceptors release high level of glutamate - neurontransmiter
    - affects the activity of the bipolar and horizontal cells
- bipolar - synapses to amacrine and retinal ganglion
- retinal ganglion - exits the eye as optic nerve -> terminates in brain
- direct path contains only: receptor cell -> bipolar cell -> ganglion cell
    - horizontal cell - modulates synaptic activity of receptor cells
        - indirectly affect the signal transmission by bipolar cells
    - amacrine cells - same as horizontal but for bipolar and ganglion
        - affects the signal of the ganglion cells

### Bipolar Cells
- connects multiple photoreceptor cells and summarize information from them (125M -> 10M)
    - also some horizontal cells (but only minority)
- do not generate action potentials 
    - responds to glutamate from receptors with graded potentials (polarization)
- at least 2 types based on glutamate (receptors) responses:
    - `OFF (bipolar) cells` - depolarized by glutamate 
        - detect dark objects in the lighter background
        - depolarize in dark
    - `ON (bipolar) cells`- hyperpolarized by glutamate
        - detect the light objects in the darker background
        - depolarize in light
            - is not result from excitation of presynaptic cell but rather reduction of inhibitory action of glutamate (more light -> less glutamate from photoreceptor)
- receptive fields:
    - two parts:
        - `the receptive field center` - direct information from the receptor cell
            - excitatory signal (for the bipolar cell)
        - `receptive field surround` - indirect information from the surrounding from horizontal cells
            - inhibitory signal
    - circumscribed by the position of the bipolar cell
        - radius depends on the position 
            - based on the population density of receptor cells (near fovea is very small - for cone bipolar cells)
    - concentric receptive fields
        - center has opposite response than the surroundings 
            - e.g. ON cell 
                - light in the center - depolarization
                - surrounding light - hyperpolarization
                - both lighten - something between

### Horizontal Cells
- large receptive field (with surrounding photoreceptor cells)
- serve as surround effect for bipolar cells (is lower than center effect)

### Retinal Ganglion Cells
- exits the eye and concludes the information from surround amacrine cells and bipolar cells -> LGN
    - approx. 3 degrees of visual field
- produces action potentials (voltage-gated)
    - because it needs to travel larger distances than the primary retina sensory cells
- depolarization of bipolar cell -> increased action potentials (hyperpolarization - decrease - inhibition) - excitation
    - also OFF/ON ganglion cells - basically passing the signal from the bipolar
- important for shape and movement of the objects
- two types:
    - `P ganglion cells` - more of them than M cells (100:1)
        - only a few bipolar cone cells
        - slow-adapting, color-sensitive, small-range signal
        - good for presence signaling (not stimulus movement)
    - `M ganglion cells` - larger cells
        - many bipolar synapses
        - more sensitive to center surround brightness differences 
        - rapid adaptation to change of stimuli

### Amacrine cells
- similar to horizontal but one layer below (bipolar concatenation)
- partially signal from bipolar to ganglion
- several function dependent types


## From Retina to Cortex
- axons of ganglion cells form optic nerve (approx 3 degrees)
- they cross in `optic chiasm` and go to the opposite site as 
`optic tract` - left field to right (and the other way around)
    - terminate i 4 nuclei (visual perception, eye movement, pupillary light reflex, hormonal changes) - typically hypothalamus
    - for visual perception is important LGN
- the path:
    1. `optic nerve` - goes through optic dist, fatty and bony tissue and reach the crossing where nerves from both eyes combine
    2. `optic chiasm` - crossing section - nasal parts of the nerves cross (to represent correct site of image)
        - called `decussation` - only partial (second part stays on its site)
    3. `optic tract` - bundle that comes after the decussation
        - majority to LGN

### Lateral Geniculate Nucleus (LGN)
- 1 in each side
- majority of optic tract fibers ends there (in the thalamus)
- majority of the outputs goes to V1 - `optical radiation`
    - defects in the pathway: eye -> LGN -> V1 
        - results in blindness
    - conscious visual perception
    - based on the architecture we can track the optical deficiencies (in nerve x in tract)
- layered architecture (based on input retinal ganglion cells)
    - 6 layers
    - `monocular neurons` - 1 neuron corresponds to one eye only
        - concentric receptive fields
        - each layer corresponds to one eye - (3 layers for left/3 for right)
- only minority of the inputs are from retina (10-20%)
    - rest is from higher levels (V1, etc.)
        - modulation of the flow of information
        - not fully understanded its reason

### Primary Visual Cortex (V1)
- located at the back of the brain (occipital lobe of the cerebrum)
- most of the LGN axons terminate in V1
- inputs from various layers - modulation of the signal
- encodes: size, orientation, motion, depth
    - sends the signal to higher areas
- all V1 neurons respond to visual stimuli exclusively
- removing results in blindness (stimulation -> visual sensation)
- two streams:
    - P-stream - orientation and location (not motion)
        - object perception, discrimination, memory, spatial orientation
    - M-stream - motion sensitive - detect objects motion, direction and velocity and guides eye movements)
 
#### Retinoscopy
- phenomenon when 2 neighboring places target 2 neighboring places in the previous part (LGN, resp. retina)
    - 2D surface is in fact mapped to 2D surface in V1 
- need to remember that it is not uniformly precise
    - some parts of the space are perceived in higher amount than the other parts (edges of the visual field)
    - one cell in retina activates multiple cells in higher complexes 

#### Lamination
- 6 principal layers (add overview figure) - named by Roman numerals
    - from outside to inside
    - L4 - highly myelinated due the high amount of inputs from LGN
        - input: most of the LGN outputs (especially to L4C)
            - sublayers for left and right signal from LGN
        - output: L3, L5, L6
        - sublayered to:    L4A,B,C (and CAlpha, CBeta)
        - mostly monoocular input
    - L2/3: (L2, L3 are functionally similar)
        - input: projections from L4
        - output: extrastrite areas (V2, V3, etc.)
            - mainly V2
        - inside L3 there are also intra connections
        - mostly binocular input, but there are also monocular inputs
    - L1:
        - input: modulatory signal from LGN
        - output: other parts of V1
        - almost devoid of neurons (mainly axons from other layers)
    - L5, L6:
        - input: projections from L4
        - output: subcortical areas (thalamus, pons, and midbrain)
        - L6 - back to the LGN

- spiny stellate and pyramidical cell types
    - stellate are mainly in L4C
        - inner layer connections
        - also inhibitory cells (they are not spiny though)
            - they are present in all layers only as intra layer connections (does not cross the layers)
    - rest pyramidical - are spread across the layers

#### Receptive field properties of V1 cells
- transform signal from LGN
- `orientation selectivity:`
    - till L4C there is clear preference of circular reception fields in neurons (dot pattern elicits the greatest response)
        - after L4C - more complex shapes
    - majority of V1 neurons prefer line stimuli
        - they prefer specific angle of the line
        - the neighbor parts of the cortex prefer similar orientations 
            - in fact they change periodically in distance (approx. 1 mm in L3)
    - orientation specific neurons are thought to be specialized for the analysis of object shape
- `direction selectivity`:
    - neurons specialized for detection of motion in perpendicular direction only in one direction (opposite is much less preferred)
- other types for motion, depth and feedback (for plasticity)
- the cells form maps of the selected properties (overlapping maps)
- `binocularity`:
    - till L4C it is mainly monocular
        - after the majority of neurons in binocular (there is only a strong signal from one eye (not whole signal))
    - necessary proper combination of the neuronal paths from both retinas (eyes) - to capture same visual field
- simple and complex receptive fields (in terms of orientation receptive fields)
    - `simple cells` - sum of LGN cell fields (simple just take few LGN cells with receptive field in line)
        - respond to a line of light in specific orientation
        - receptive fields vary in length and orientation
        - similar to ON/OFF cells but around line
    - `complex cells` - input from several simple cells with the same orientation
        - they do not have distinct ON and OFF regions (the line can be transposed)
        - respond to line stimuli of specific orientation anywhere within larger receptive field
        - there depends mainly on the correct orientation

### Extrastriate Visual Cortex
- all surrounding areas of the V1
    - 3 subareas: V2, V3, V4
- damage results in perceptual deficits (not overall loss of vision)


## Neuron
- neuron consist of the soma, dendrides and the axon
    - the soma:
        - typical cell body (nothing so special in comparison to other cells)
            - there is a nucleus, ER and so on
    - the axon:
        - highly specialized part of the cell to transfer information over distances
        - starts in `axon hillock` - there typically starts the signal
        - there is special set of proteins in comparison to soma
            - large number of microtubules to transport proteins from/to soma
        - the most important part is `axon terminal` - it meets with other neuron in `synapse`
            - `innervation` - contact with other cell (not neuronal)
            - there are `synaptic vesicles` - with neurontransmiter
            - high number of mitochondria - high energy demand
    - the dendrites:
        - specialized structure with receptor to detect signal from the axons (in synapse)

### Neuronal Membrane
- the important aspect of the signal transmission is the movement of ions and maintanation of 
the specific concentration levels
    - the levels are maintained by the ion pumps that create the concentration gradients
- `membrane potential` - voltage across the membrane
- `equilibrium potentials` - state where ionic concentration gradient and electrical potential eliminates
    - they are the same
    - no ions travel to either site
- main point is that Na+, Ca2+ and Cl- are more concentrated outside the cell and K+ inside
- majority of the brain energy is used to maintain the correct concentration gradients

### Action Potential
- neuronal membrane at rest has around -65mV
- during action potential it becomes positive
    - rising phase -> till 40mV - overshoot -> falling phase - more negative than resting -> undershoot - restoration
- typically we detect some signal -> send response -> Na+ channels are open -> depolarization - `generator potential`
    - if generator potential reaches threshold -> `action potential`
    - it does not need to be Na+ only
    - it is typically response to neurotransmitter
        - might be also to other signal though
- there is a limit in firing frequency - it is not true that high depolarization cause appropriately 
that much fires (neurons need to regenerate)
    - `refractory period`
        - `absolute` - impossible to elicit spike
        - `relative` - still very hard to elicit spike - neuron did not regenerate fully yet
- key workflow:
    - `threshold` - opening of the Na+ channels
        - it reaches the threshold that the permeability favors Na+ over K+
    - `rising phase` - negative membrane potential -> Na+ ions go inside
        - rapid depolarization
    - `overshoot` - above 0mV to positive
    - `falling phase` - Na+ channels inactivate + K+ channels open
        - K+ strongly outside -> negative potential again
    - `undershoot` - reach the resting K+ potential - only K+ open
    - `absolute refractory period` - K+ inactivate - need to fix the voltage to be available
    - `relative refractory period` - still hyperpolarized membrane
        - there needs to be stronger depolarizing current to bring membrane to action potential

#### Conduction of the AP
- the AP needs to travel only one-directionally from soma to axon terminate
- axonal membrane is excitable - it can elicit AP all along its length
- the propagation is done by inactivation of the ion channels (where the signal has been before) 
- `myelination` - axons coathed in myelin sheath with the `nodes of Ranvier`
    - electrical insulation - helps the electrical conduction
    - farther and faster current spread
- mainly in axons because of its high amount of the ion-channels

#### Synaptic Transmission
- `synapses` - places where the neurons (or other cell) communicate with each other
    - from pre- to post-
    - electrical and chemical synapses
- `chemical synapses` - `synaptic cleft` - extracelulate space where the neurotransmitters efflux
- typically to axon to either dendrite, soma or axon
- `neurotransmitters` - small chemicals that propagate the signal in chemical synapses
    - main: glutamate, gamma-aminobutyric acid (GABA), glycine and acetylcholine
        - fast synaptic transmission (slow are also many others)
    - different neurotransmitters have different selectivity to ion channels
- the synapses that tent to bring the membrane potential towards the threshold for generation potential
are called `excitatory` - `excitatory postsynaptic potential` (EPSP)
- hyperpolarization of the postsynaptic cell (Cl- channels) - `inhibitory` - `inhibitory postsynaptic potential` (IPSP)
- it needs to be swept out of the cleft
- there are various ways how to modulate the signal




https://nba.uth.tmc.edu/neuroscience/m/s2/chapter15.html
https://dspace.cuni.cz/handle/20.500.11956/176078
https://dspace.cuni.cz/handle/20.500.11956/183997


