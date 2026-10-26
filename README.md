# Hopfield networks

Implementation of a classical Hopfield network in Python, used as an associative memory, and of its modern version with the softmax update rule.

The notebook covers:

- storing random patterns with the Hebb rule and checking that they are fixed points of the dynamics, with the energy decreasing during the evolution
- pattern recognition starting from noisy inputs (the network fails at about 35-40% of flipped neurons) and from partially masked ones
- spurious fixed points: negatives of the stored patterns and mixed states
- storage capacity, C ≈ N / (2 log₂ N), and what happens when it is exceeded
- the failure of the classical network with larger grayscale images, and the modern Hopfield network (update with a softmax over the similarities, log-sum-exp energy), which recalls them also from noisy and masked inputs
- the role of the inverse temperature β: at high temperature the modern network ends up in metastable states

The notebook comes from the Statistical Physics course of prof. S. Zapperi (University of Milan), and the theory parts are taken from the course material.

## Usage

```
pip install -r requirements.txt
jupyter notebook hopfield_networks.ipynb
```

The plotting functions (`visualise_hopfield_network`, `plot_energy`, `plot_patterns`, `animate_hopfield_network`) were provided by the course in a `utils.py` file, which is not included.

For the part on complex patterns, put some grayscale PNG images of the same size in the `images/` folder. The images originally used are not included since they are copyrighted, so the cells of that part have no saved output.
