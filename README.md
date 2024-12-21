# axonemalyze
Calculate the circularity of axoneme picks from cryo-ET images.

# Functions
The code is split into two command-line functions:
- `segment_axonemes.py`
- `estimate_circularity.py`

The command-line functions are to be run in that order.

## segment_axonemes.py
The function takes a directory as input. This directory should contain all files in the `.coords` format with the xyz coordinates of the picks.

Here is an example of how to run this function:
```
python segment_axonemes.py test_data/
```

This function outputs a directory (default `segmented/`) in the input directory with a single `.csv` file per axoneme.

## estimate_circularity.py
This function takes a directory as input. This directory should contain all files in the `.csv` format as outputted by `segment_axonemes.py`.

Here is an example of how to run this function:
```
python estimate_circularity.py test_data/segmented/
```

This function prints an average circularity for each axoneme that contains at least five doublets to the standard output.
