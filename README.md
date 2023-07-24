# **Maplet in Microbiome Analysis**

Maplet is an R package for statistical data analysis specifically focusing on metabolomics datasets (Chetnik et al. "maplet: An extensible for modular and reproducible omics pipelines". Bioinformatics, 2021). 

To get started, you need to install the latest stable version of maplet using the following command:

```
devtools::install_github(repo="krumsieklab/maplet@v1.2.1", subdir="maplet")
```

Additional information about the installation of maplet and examples on how to use it can be found on the github page of the package [here](https://github.com/krumsieklab/maplet). 


# **The Aim of this Project**

The usage of multi-omics and bioinformatics approaches in the gut microbiome and metabolome field has gained more attention recently. 

Here, we used "maplet" and R to analyze a publicly available dataset from the paper "Gut microbiome structure and metabolic activity in inflammatory bowel disease" (Franzosa et al., 2019). [Link to publication](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6342642/pdf/nihms-1510763.pdf). 

We did that to: 
     
      1- Check the feasibility of using maplet in metabolome and gut microbiome data analysis 
      2- Check the reproducibility of the results generated from the article 

# **Getting Started with the Project**

To get started, we first downloaded and saved the supplementary dataset from the above paper. 

You can find the supplementary data [here](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6342642/).

The supplementary files show the results of two metabolome and microbiome datasets for patients with CD, UC, or control (PRISM: 155 samples and validation cohort: 65 samples) - as a start we focused in this exercise on the PRISM samples. 

We then used the supplementary files to create a new excel file with all the necessary data we need for our analysis under the name: **"Metabolome_data.xlsx"**. 

The new excel file "Metabolome_data.xlsx" has the metadata, metabolite abundance, and features of the 155 PRISM samples in three separate sheets (Metabolome_metadata_PRISM, Metabolite_abundance_PRISM, and the Metabolite_features).

**You can find the "Metabolome_data.xlsx" file under the "Metabolites_Dataset" folder above** 

# **Starting the Analysis**

In this section, we will mention briefly the steps we followed in this analysis.

To start, we first loaded the "Metabolome_data.xlsx" data and annotations in R. We then preprocessed the data based on the three diagnosis and performed:(quotient normalization, imputation, and missing values filtering) and then generated an html report of the pre-processing results. The html report gives a summary output of all the functions/ tests performed on the data.

**Below is a screenshot of the html report generated:** 

![Screen Shot 2023-07-22 at 11 45 35 AM](https://github.com/RKA2020/Maplet_Gut_Data/assets/127655038/fbc58eb7-2ae9-4410-ac0b-a020e8c4ea9f)

You can find the codes for the preprocessing part and the full html report in R_Codes folder under the file "STARTING_The_METABOTOOLS_PIPELINE" above.
                 
After preprocessing the data, we performed different statistical analysis (either using maplet or R codes). Such tests include: PCA, linear regression for the phenotypes, Chisquare, and others. 

All the codes uded for the statistical analysis can be found in R_Codes folder under the files "Stat_with_maplet"and"Stat_with_R" above.

**Below are screenshots of some of the results generated:** 

**A)PCA Graph:**

![Screen Shot 2023-07-22 at 12 07 14 PM](https://github.com/RKA2020/Maplet_Gut_Data/assets/127655038/798741c5-d531-40ff-9e38-d6a9607a9cad)

**B) Metabolic enrichment (Control Vs. CD):**

<p align="center">
  <img src="https://user-images.githubusercontent.com/127655038/255533946-dc626780-0d85-48f7-b402-468ceda7046c.png">
</p>

We also used R to create additional variables to compare between diagnosis (ANOVA and Pairwise comparisons) at a Bonferroni significance of 0.05. **A screenshot of the excel file generated is below:**

<p align="center">
  <img width="600" height="400" src="https://user-images.githubusercontent.com/127655038/255521530-262320dd-ea61-4bcd-89f5-499255981b13.png">
</p>

After applying a stringent cutoff for filtering the five variables, most of the metabolites across the three diagnosis appeared to follow one of the four patterns:(ladder, CD different, Control different, and UC different). 

**Below is a screenshot of a schematic we generated for the four observed patterns:** 

<p align="center">
  <img width="660" src="https://user-images.githubusercontent.com/127655038/255524806-7689df54-706d-4f60-a745-9e74ff5348bb.png">
</p>

**Here are examples on how the patterns look in the data:**

<p align="center">
  <img width="660" src="https://user-images.githubusercontent.com/127655038/255528662-3220b88d-d661-4848-a61a-0b4071bf3276.png">
</p>

