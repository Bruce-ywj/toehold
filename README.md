# Installation
toehold requires the following packages to be installed  
1. python >= 3.8.15
```
pip install -r requirements.txt
```
# Usage
## 1. Predict ON & OFF & ONOFF value
```python
from predict import Infer_ON,Infer_OFF,Infer_ONOFF
seqs = ['AAAATAAGTTAGCTGGATATTGATAAATTTAACAGAGGAGAAAATTTATGAATATCCAG','ATAAACAAAATGGATATTATAGACAAAAAAAACAGAGGAGATTTTTTATGTATAATATC','GATGTTACAAACGATAATATAGACAAAAATAACAGAGGAGAATTTTTATGTATATTATC']
print("ON value:",Infer_ON(seqs))
# ON value: [0.9851788 0.7870039 0.8512967]
print("OFF value:",Infer_OFF(seqs))
# OFF value: [0.71163505 1.         0.9980813 ]
print("ONOFF value:",Infer_ONOFF(seqs))
# ONOFF value: [ 0.12640211 -0.17399795  0.00854342]
```
## 2. Optimize given seqs
```python
from optimize import optimize_toehold
seqs = ['AAATTTTATAACCGTTAATATTGATAAAAAAACAGAGGAGATTTTTAATGATATTAACG','ATCTAAGACTAGTGATTTTCTGACTTTCTTAACAGAGGAGAAAGAAAATGAGAAAATCA']
optimized_seqs, new_onoff = optimize_toehold(seqs,num_of_optimization_rounds = 2)
# optimized_seqs ['GGGTTTTACAGCCCTCAATAGATAGATCATAACAGAGGAGAATGATCATGCTATTGAGG','CCCCTCCCCATAAGTTTTGCTACCCTCCCTAACAGAGGAGAAGGGAGATGAGCAAAACT']

# new_onoff [0.9699408, 0.6616005]
```