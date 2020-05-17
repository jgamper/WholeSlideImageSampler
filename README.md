<p align="center">
    <br>
    <img src="docs/source/imgs/syntax_logo_text.png" width="600"/>
    <br>
<p>

# Help building our code and community!

Add sourcerer link here.

All contributions are welcome! Please see our [Contributing Guide](https://github.com/jgamper/wsi-syntax) for more details.

# Quick Start

### Tissue mask and tiling pipeline
```python
from syntax.slide import Slide
from syntax.transformers.tissue_mask import OtsuTissueMask
from syntax.transformers.tiling import SimpleTiling
from syntax.transformers import Pipeline, visualize_pipeline_results

slide = Slide(slide_path=slide_path)
pipeline = Pipeline([OtsuTissueMask(), SimpleTiling(magnification=40,
                                                  tile_size=224,
                                                  max_per_class=10)])
slide = pipeline.fit_transform(slide)
visualize_pipeline_results(slide=slide,
                           transformer_list=pipeline.transformers,
                           title_list=['Tissue Mask', 'Random Tile Sampling'])
```
<p align="center">
    <img src="docs/source/imgs/simple_pipeline.png" width="600"/>
<p>

# Install

`pip install compay-syntax`

You will need to install openslide. This is included in the dependencies so may be automatically installed. If not I found this to help:

```bash
#!/bin/bash

sudo apt-get install openslide-tools
pip install openslide-python
```
