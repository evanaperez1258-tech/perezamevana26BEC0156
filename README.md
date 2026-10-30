# Sentinel-1 SAR Oil Spill Detection — EDA

Exploratory Data Analysis of grayscale satellite images labelled
as oil-spill or non-oil-spill.

## Objective

Explore the dataset structure, class distribution, visual patterns,
image brightness, contrast and potential outliers.

## Tools

Python, NumPy, Pandas, Matplotlib, OpenCV and Jupyter Notebook.

## Dataset

Source:
https://www.kaggle.com/datasets/harikrishnacs/sentinel-1-sar-oil-spill-detection-dataset

The downloaded class folders contain 5,538 readable images,
each measuring 400 × 400 pixels:

| Class | Images | Percentage |
|---|---:|---:|
| Non-oil-spill | 3,695 | 66.72% |
| Oil-spill | 1,843 | 33.28% |

Class_0 represents non-oil images, including look-alikes.
Class_1 represents images containing oil features.

The metadata lists 5,630 images. The reason for the difference
remains unconfirmed. The separate sample folder was excluded
because its class labels were not established.

## Analysis

- Counted images and calculated class percentages.
- Displayed reproducible random samples from both classes.
- Calculated each image's mean pixel intensity and standard deviation.
- Compared distributions using histograms, box plots and a scatter plot.
- Displayed the darkest and brightest images in each class.
- Flagged potential outliers using the class-wise 1.5 × IQR rule.
- Investigated flagged examples without automatically removing them.

## Main Findings

The dataset has approximately twice as many non-oil images as
oil images. Oil-spill images had lower average brightness and
lower average global contrast, but both classes overlapped
substantially.

Some flagged images contained large white regions beside dark
areas. Other examples contained dark features against bright
backgrounds. Their physical causes were not confirmed.

These measurements describe stored JPEG values, not calibrated
radar backscatter. The EDA does not establish detection accuracy.

## Project Files

- oil_spill_eda.ipynb — analysis, visualizations and conclusions.
- outputs/ — generated figures and summary tables.
- requirements.txt — Python dependencies.

## How to Run

1. Download and extract the dataset from the source above.
2. Install the packages listed in requirements.txt.
3. Open oil_spill_eda.ipynb in VS Code or Jupyter.
4. Update data_folder to your extracted kaggle/data folder.
5. Select your Python environment and run the cells from top to bottom.

The raw dataset is not included in this repository.