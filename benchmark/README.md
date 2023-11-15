# Benchmarking

## Table of Contents

1. [Introduction](#introduction)
2. [Deep Learning methods](#deep-learning-methods)
3. [Ruled-based methods](#rule-based-methods)



## Introduction

## Deep Learning methods

### U-FISH

### deepBlink

### SpotLearn

### DetNet

## Rule-based methods

### Big-FISH

We employ dense region decomposition for spot detection. As Big-FISH calculates a default value for each parameter automatically, the grid search range for some parameters was derived from the default value. 
                 * grid search parameters:
                 
                    sigmaYX: default + [-0.5, -0.25, 0, 0.25, 0.5]
                    threshold: default indices: [-6, -3, -2, -1, 0, 1, 2, 3, 6]
                    alpha: 0.5-0.8, step size += 0.1
                    beta: 0.8-1.2, step size += 0.1
                    Gamma: 4-6, step size += 0.5

### RS-FISH
Given that RS-FISH possesses a parameter known as intensityThreshold, the selection range for this parameter can vary significantly based on different image data types. To preclude the generation of a substantial computational load, we scaled the seven categories of datasets to (0, 255) prior to executing the subsequent grid search.
                 * grid search parameters:
                    DoGSigma = 1-2, step size += 0.25
                    DoGthreshold = 0.003-0.06, step size *= 1.5 
                    supportRadius: 2-4, step size +=1
                    inlierRatio: 0.1
                    maxError: 1.5000
                    intensityThreshold: [0, 10, 50, 100, 150, 200, 255]
### Starfish
 Starfish offers several methods for spot detection, and we have chosen the BlobDetector as our analysis pipeline.
                  * grid search parameters:
                    sigs = 1-6, step size += 1
                    thrs = 0.000095-0.15, step size +=0.00005
### TrackMate
Similar to the RS-FISH method, images need to be scaled to the range of (0,  255) when using TrackMate grid search best parameters.

                  * grid search parameter:
                    Detector: options are 'log', 'dog'
                    radius = [0.01, 0.1, 0.2, 0.5, 0.75, 1.0, 2.0, 3.0, 4.0, 5.0, 7.5, 10.0]
                    thr = 0.1-15 step_size *=1.05 
