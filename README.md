# project1-sequence-analysis

Purpose: this python pipeline analyses Next-Generation Sequencing(NGS) data to validate reads, find substitution mutations against a reference genome and run sample level statistical comparisons to view the effects of genotoxic treatment.

How to run the program: to run this program, open the Jupyter notebook in google colab by uploading the .ipynb file or clone the repository. Then run the cells by pressing the play button from top to bottom to load the data and run the functions.

Inputs and outputs: the inputs expected are a list of dictionaries which contain read data like - read_id, sample, group and sequence - and a reference string. it outputs read dictionaries that have been edited with validation statuses, mutation lists sample level summary metrics (valid reads, mismatches, top positions) and group statistical comparisons. 

Code design: the code was designed into different functions like validate_read, analyse_reads and summarise_samples which makes it easier to debug. nested dictionaries were used for sample summaries which makes looking things up easier when organising data like substitution counts. for invalid reads wrong_length ans invalid_characters error codes were used to keep the order of input rather than getting rid of the data completely. this allowed quality control metrics to show the sequencing failures accurately.

Testing: three tests used to check the correctness/robustness of the code was handling invalid reads by asserting sequences with incorrect bases like ATN to shoe that the status was invalid, checking the mutation mapping accuracy so that mismatched sequences gave back the correct position indices and substitution types like A>G and checking the edge case stability by testing empty inputs to make sure that summarise_samples returned {} 
