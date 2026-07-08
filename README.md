# Abstract

`Context`: Previous research extracted software mentions from biomedical literature. However, methodologies of analysing these software mentions remain underexplored. This thesis investigates: (RQ1) the software ecosystems that have formed in scientific research; (R2) the patterns and relationship identified of software mentions within and across disciplines in communities generated with the Leiden algorithm, derived from a co-occurrence network; (RQ3), and finally, whether discipline-specific information, such as an abstract, is a valuable approach towards finding useful software mentions.  

`Methods`: Software mentions were extracted from a PMC OA commercial subset of
the CZ Software Mentions dataset and classified into disciplines using the publication classification of Van Eck and Waltman. Field-wide, and discipline-specific co-occurrence graphs were built from a reference subset, after which communities were identified using the Leiden algorithm. Test papers were assigned to communities by comparing abstract embeddings using frequency, -rank, or ratio-based metrics for the field-wide graph, while the discipline-specific approach assigned papers to the matching discipline as the best-fit. Performance was evaluated using modularity, reduced mutual information, the Silhouette coefficient, and manual annotations.

`Results`: More than 748,672 papers had at least one pair of co-occurring software mentions. The field-wide partitions scored a modularity greater than 0.3 with two exceptions, and a mean reduced mutual information (RMI) above 0.92 with mostly limited deviation. The discipline-specific graphs contained approximately 500 communities with an RMI below 0.75. Most of these communities had a median software community size of 7 and a relatively high modularity of 0.57, while the peak at a modularity of 0 primarily consisted of smaller communities (Median = 3).

`Evaluation and Conclusion`: The field-wide approach yielded mostly stable communities, largely centered around dominant all-purpose software, although some communities showed a preference towards specific disciplines. The discipline-specific graphs formed a substantial portion of unstable graphs (560 with an RMI below 0.75) and limited discernible differences within communities of a discipline could be found to indicate definitive separate workflows. The best-fit predictions were more effective for the discipline-specific approach than the field-wide. 

# Installation Instructions

```bash
# setup the virtual environment
python -m venv venv

# install the necessary packages
pip install -r requirements.txt
```

# Data acquisition

Required packages and directory specifications.
This paper used the software mentions extracted from a PMC OA commercial subset of the CZ Software Mentions dataset developed by the Chan Zuckerberg Initiative (CZI) (Updated Sep 27, 2022) [1] which were subsequently classified using the work from [2] who built a dataset from 71 million resources from various academic origin (acessible from Zenondo (version 2025aug Oct 29) [3]).

The notebooks assume that the dataset files are stored in a folder `data` that sits as the same level as the `notebooks` directory. The assumed directory structure is the following:

- `notebooks`
- `data`
  - `classification_openalex_2025`
    - clustering.tsv
    - main_field.tsv
    - macro_cluster_main_field.tsv
    - micro_cluster.tsv
  - `software_mentions`
    - `disambiguated`
      - comm_disambiguated.tsv.gz

# References

[1] A. - M. Istrate, B. Veytsman, D. Li et al. CZ Software Mentions: A large dataset of
software mentions in the biomedical literature. Dataset. 2022. doi: 10.5061/dryad.
6wwpzgn2c. github_url: https://github.com/chanzuckerberg/software-mentions?tab=readme-ov-file. url: https://datadryad.org/dataset/doi:10.5061/dryad.6wwpzgn2c.

[2] N. J. Van Eck and L. Waltman. An open approach for classifying research publications.
Jan. 2024. doi: 10.59350/qc0px-76778. url: https://www.leidenmadtrics.nl/articles/an-open-approach-for-classifying-research-publications. dataset_url:

[3] N. J. Van Eck. Classification of research publications based on data from OpenAlex.
Version 2025aug. Aug. 2025. doi: 10.5281/zenodo.17442025. url: https://doi.org/10.
5281/zenodo.17442025
