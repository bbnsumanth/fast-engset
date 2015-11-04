fast-engset
===========

Python code to compute the blocking probability ```P``` in the Engset model:

```
                         m                              
         binom{N - 1}{m}A                            E        
P = --------------------------    where    A = -------------.
     __ m                    X                  N - E(1 - P)   
    \        binom{N - 1}{X}A                           
    /__ X = 0                                           
```

```N``` denotes the number of *sources*, ```m``` the number of *servers*, and ```E``` the *offered traffic* from __all__ sources. 

```E``` is given by ```E = N * lambda / mu```, where ```lambda``` is the *arrival rate* of a source and ```1/mu``` is the *mean service time* for a given request.

If you are using this in an academic work, please cite the corresponding paper:

```@article{azimzadeh2015fast,
  title={Fast Engset computation},
  author={Azimzadeh, Parsiad and Carpenter, Tommy},
  journal={arXiv preprint arXiv:1511.00291},
  year={2015},
  url={http://arxiv.org/pdf/1511.00291.pdf}
}```

__Warning__: Certain texts use instead the __normalized__ offered traffic,  which is instead defined as ```alpha = lambda / mu```. In this case, ```E = N * alpha```.

Installation
=======
`pip install fast_engset`

Example
=======

```python
from fast_engset import fe

m = 5  # Number of servers
N = 10 # Number of sources
E = 2  # Total offered traffic from all sources

# Blocking probability
P = fe.compute(m, N, E)
```
