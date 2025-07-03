---
title: '[Pytorch] Same child-module with different instance name'
date: 2025-07-03
permalink: /posts/2025/07/same-module-with-different-name/
tags:
  - pytorch
  - python
  - AI
---
This is short article about problem I faced during AI-engineering.

### Pytorch Model
Model of `pytorch` is `torch.nn.Module` object in python and so as any layer inside the model, e.g. `Linear` layer.

## Problem
For sake of convenience, I defined a instance object of model, submodule with only purpose of returning
it's child modules to the model. So, those child modules had two access,
namely `self.submodule.child_module1` and `self.child_module1`. 
This caused problem when loading checkpoint. 
For both names were inside `.named_parameters()` even they are same object,
`load_state_dict` required weight for both names.

## Solution
As long as two modules were same, it was okay to load with only one of it's name. 
This requires one to set `strict=False` or duplicate weight with differently named keys.

I have checked those weights were equal after such loading, and did test and found no difference.