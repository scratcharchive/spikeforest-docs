### Meeting 11/8/2018, Liz, Jeremy, Alex

All to change 'Datasets' term to 'Recordings' and 'Recording'
JM to change "Processing" to "Summarizing"
Def: Study: a group of recordings whose accuracy results it is meaningful to aggregate together.

To the studies table add:
1. Number of datasets
2. File size total
3. Channels (in a range 4, 128, 1M!)
4. Duration in seconds (use Moment.js to standardize times)
5. Type: Synthetic / In Vivo / In Vitro
6. Probe type
7. Brain Region
8. Groundtruth Units

Algos page:
- Add wrapper repo links and copy about welcoming other collabs

Python Wrapper:
- A Python script that does daily runs to download the data for the website from the KBucket and the stores them on a directory on the cluster users directories.
- Liz to ask Dylan to confirm security / auth on home directory.

For Next Week:
- Liz: viz of SNR/Accuracy charts (*) for each sorter aggregated by the study. Overlay the sorters on the same plot, allow for interactions.
- Liz: requirements list to JM
- Liz: Recordings pages structure (edited)

Algos on X and Studies on Y
Number of units greater than 90% (With slider bar).
on the SNR/accuracy plots. (edited)

Number of units with accuracy over a threshhold, this would be interactively set  via the slider.

Blue = great red = junk.
on this heatmap.
normalize colors across the rows rather than overall.

Jeremy -> Liz
Here's the gist: https://gist.github.com/magland/59990693052fbe8d65c0c53223a49748
And the corresponding live notebook: https://colab.research.google.com/gist/magland/59990693052fbe8d65c0c53223a49748/load_spikeforest_accuracies.ipynb (edited)

So right now the 2 batches to load are:
key=dict(batch_name='ms4_magland_synth')
key=dict(batch_name='ironclust_magland_synth')
