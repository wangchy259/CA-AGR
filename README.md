# Content-Aware Adaptive Grid Refinement for Robust Homography Estimation

A method for robust homography estimation using content-aware adaptive grid refinement.

## Overview

We propose a content-aware adaptive grid refinement method for robust homography estimation. Our approach aims to improve feature matching and geometric alignment by adapting the grid refinement process to image content.

## Matching Results

### RoMa Matching Results

![RoMa Matching Results]<img width="2000" height="1000" alt="match_roma" src="https://github.com/user-attachments/assets/bd4b20ec-01b5-4466-961d-e213d477472b" />

*Feature matching results obtained using RoMa.*

### Our Method

![Matching Results](images/match.png)<img width="2000" height="1000" alt="match" src="https://github.com/user-attachments/assets/66161a4f-05e0-4fd2-bc12-96357bf57bb9" />


*Feature matching results of our method.*

## Network Architecture

![Network Architecture](images/network.png)

*Overview of the proposed content-aware adaptive grid refinement framework.*

## Network Framework Code

The network implementation will be released soon.

```python
import torch
import torch.nn as nn

class AdaptiveGridRefinement(nn.Module):
    """
    Content-aware adaptive grid refinement module
    for robust homography estimation.
    """

    def __init__(self, in_channels=128, hidden_channels=64):
        super().__init__()

        self.feature_extractor = nn.Sequential(
            nn.Conv2d(in_channels, hidden_channels, 3, padding=1),
            nn.ReLU(inplace=True),
            nn.Conv2d(hidden_channels, hidden_channels, 3, padding=1),
            nn.ReLU(inplace=True),
        )

        self.grid_refinement = nn.Conv2d(
            hidden_channels, 2, kernel_size=3, padding=1
        )

    def forward(self, features):
        refined_features = self.feature_extractor(features)
        grid_offsets = self.grid_refinement(refined_features)
        return grid_offsets

# Note: This is an illustrative module, not the complete
# homography estimation network.
```

## Code

**Our code is coming soon.**

The complete implementation, pretrained models, and evaluation scripts will be released soon.

## Citation

If you find this work useful, please consider citing our paper.
