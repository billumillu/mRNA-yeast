# Quantification of mRNA Levels in Yeast

Quantification of mRNA levels is critical for the study of eukaryotic cells such as yeast. The handful existing pipelines that allow such quantification on smFISH images, although impressive, have their own advantages and disadvantages. One that has improved quite a lot in the past few years and is among the best for such quantification is FISH-quant’s Big-FISH package for Python. It offers excellent functions to segment nuclei and cells, detect spots and compute various features from the generated data. 

One major drawback, however, is that Big-FISH requires manual user input for the threshold value for nucleus segmentation and cell segmentation. This is a tedious approach, especially when dealing with a large set of images. We have attempted to solve this using two methods: a) calculating the threshold using the Mode and Standard Deviation of the given image
b) predicting the threshold using various features from the image as input 

We then checked and compared their performance. The main assessment criteria was the number of outliers detected using Tukey’s Method1. Using ML led to a better performance – About 400 more cells were detected, slightly lesser outliers were produced, and the Upper Bounds of Tukey’s Fences were now in a smaller range.

The result is a pipeline that is specialised for the data obtained by the Mellor Group2 and that does not require additional user input to determine thresholds.

Apart from this, we also conducted some additional analysis on the generated data. We looked at the method of mRNA production, specifically, Transcription Bursting3. This was done using the Kolmogorov–Smirnov test to check for Poissonian distribution in the mRNA produced. We also compared the mRNA production between genes, and between different sets of the same gene. This was achieved using the Mann–Whitney U test.
