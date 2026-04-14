an optimized version of ironclust with better detection threshold controls, faster merging and splitting.
written by Shahaf Weiss 2025
# Ironclust_but_faster  commands:
## setup sorting a new session
0.	Python: Run Project_hierarchy\hir_new_main\preprocessing\check_probe_histology.py on the session to get histology csv
1.	MATLAB: Run SGLXMetaToCoords_PAG.m to make a probe file that only takes PAG.
2.	Create a .prm file:
Irc makeprm bin-file probe-file optional-template-prm file
3.	Check and adjust parameters.
4.	Run irc preview. Set thresholds, save to prm and save to thresholds .mat file.
5.	Set tlim_load = [0,10 ]; and run run irc detect; irc traces; to confirm spikes are detected correctly. And irc sort; irc traces; to check the sorting. Repeat steps 3-5 if not.
6.	Set tlim_load = []; and run the sorting: irc spikesort or irc all to launch the gui when done
7.	If gui didn’t launch, run irc manual and “load previous results- Yes”
8.	Go to Edit menu and select reorder by x then y
9.	If clustering is off (too many / to few), adjust parameters and run irc auto.

## Controls:
### cluster annotations
1 – single unit
2- MUA
3- noise
4- axonal
### general
S- split using multi-channel
M- mark for merge
D- mark for deletion
U- apply marked annotations and update




![IronClust logo](img/ironclust_logo.png)

# IronClust
Terabyte-scale, drift-resistant spike sorter for multi-day recordings from [high-channel-count probes](https://www.nature.com/articles/nature24636)


## original Authors

- James Jun, Center for Computational Mathematics, Flatiron Institute
- Jeremy Magland, Center for Computational Mathematics, Flatiron Institute

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

## Acknowledgments

* We thank our collaborators and contributors of the ground-truth datasets to validate our spike sorting accuracy through spikeforest.flatironinstitute.org website.
* We thank [Loren Frank's lab](https://www.cin.ucsf.edu/HTML/Loren_Frank.html) for contributing the terabyte-scale 10-day continuous recording data.

* We thank [Dan English's lab](https://www.englishneurolab.com/) for contributing four-day uLED probe recordings.
