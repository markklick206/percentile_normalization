# percentile_normalization
Percentile-normalization method for correcting batch effects in case-control microbiome studies.

Here, we provide a python script for running the percentile normalization procedure described in Gibbons et al. (2018) [http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006102].

Briefly, features (i.e. bacterial taxon relative abundances) in case (i.e. disease) samples are converted to percentiles of the equivalent features in control (i.e. healthy) samples within a study prior to pooling data across studies. Pooled studies must have similar case and control cohort definitions.

## Usage

To access the help function and view script inputs, run `python percentile_norm.py --help` in Terminal.

There are three required inputs:
* `-i`: OTU table, samples as rows and OTUs/phylotypes as columns
* `-case`: list of case sample names in the OTU table
* `-control`: list of control sample names in the OTU table

The output file name can be specified by the `-o` flag, and the default output file is `out_percentile_norm.txt`.
The delimiter for the OTU table file can be altered with the `-otu-d` flag and the delimiter for the sample lists with the `-sample-d` flag.
The options are: `tab`, `newline`, or `comma`. `tab` is the default for both.

Example data files have also been provided. An example command that uses these files as inputs is pasted below:

```
python percentile_norm.py -i baxter_crc_data.txt -case baxter_crc_samples.txt -control baxter_h_samples.txt -o baxter_percentile_norm.txt
```
