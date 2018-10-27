# MountainSort

MountainSort is spike sorting software.

Whereas in the past it has been tightly linked to MountainLab (a more general framework for scientific data analysis) this spike sorting algorithm is now callable directly from python.

To run MountainSort spike sorting, you should first [prepare your data in .mda format](mountainsort_dataset_format.md)

Next, you can install the following python packages:

```
pip install spikeinterface spikewidgets spiketoolkit
pip install ml_ms4alg kbucket 
```

*Note that these packages are currently under alpha development and subject to breaking changes.*

(The code below is runnable as a [live jupyter notebook](https://colab.research.google.com/drive/1a47bPnkWnxrqkXngYSJz11xf5LDvTAVe) in google colab.)

Now, from within python, you can apply MountainSort spike sorting

```
# Imports
import spikeinterface as si
import spiketoolkit as st
import spikewidgets as sw

# Read in the recording from the dataset/ directory
recording = si.MdaRecordingExtractor(dataset_directory='dataset')

# Run the spike sorting
sorting = st.sorters.mountainsort4(
    recording=recording,
    detect_sign=-1,
    adjacency_radius=50,
    freq_min=300, freq_max=6000,
    whiten=True,
    clip_size=50,
    detect_threshold=3,
    detect_interval=10,
    noise_overlap_threshold=0.15
)

# Save the results as firings.mda
si.MdaSortingExtractor.writeSorting(sorting=sorting, save_path='firings.mda')

# View the average waveforms
sw.UnitWaveformsWidget(recording=recording, sorting=sorting).plot()
```
