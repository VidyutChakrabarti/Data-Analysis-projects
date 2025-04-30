## ML Challenge Problem Statement
**Note:** This notebook was part of the Amazon ML Challenge 2024, organized in Unstop.

### Feature Extraction from Images

The goal is to create a machine learning model that extracts entity values from images. This capability is crucial in fields like healthcare, e-commerce, and content moderation, where precise product information is vital. As digital marketplaces expand, many products lack detailed textual descriptions, making it essential to obtain key details directly from images. These images provide important information such as weight, volume, voltage, wattage, dimensions, and many more, which are critical for digital stores.

<div align="center">
  <table border="0" cellspacing="0" cellpadding="0">
    <tr>
      <td style="padding-right: 30px;">
        <img src="assets/logo.jpeg" alt="Feature logo" width="280"/>
      </td>
      <td style="vertical-align: middle; font-size: 12px; font-weight: bold;">
        Access Solution<br><br>
        <a href="https://colab.research.google.com/drive/1QQcWvxkdcbSioluAJLTUnKrisKt52mTy?usp=sharing">
          <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab"/>
        </a><br><br>
        <a href="https://github.com/VidyutChakrabarti/Data-ML-projects/tree/main/Feature%20Extraction%20from%20images/src/README.md" 
           style="display: inline-block; padding: 6px 12px; background-color:rgb(255, 89, 139); color: white; text-decoration: none; border-radius: 4px; font-size: 12px;">
          Understand the solution
        </a>
      </td>
    </tr>
  </table>
</div>

### Data Description: 

The dataset consists of the following columns: 

1. **index:** An unique identifier (ID) for the data sample
2. **image_link**: Public URL where the product image is available for download. Example link - https://m.media-amazon.com/images/I/71XfHPR36-L.jpg
    To download images use `download_images` function from `src/utils.py`. See sample code in `src/test.ipynb`.
3. **group_id**: Category code of the product
4. **entity_name:** Product entity name. For eg: “item_weight” 
5. **entity_value:** Product entity value. For eg: “34 gram” 
    Note: For test.csv, you will not see the column `entity_value` as it is the target variable.

### Output Format:

The output file is a csv with 2 columns:

1. **index:** The unique identifier (ID) of the data sample.
2. **prediction:** A string which having the following format: “x unit” where x is a float number in standard formatting and unit is one of the allowed units (allowed units are mentioned in the Appendix). The two values should be concatenated and have a space between them. For eg: “2 gram”, “12.5 centimetre”, “2.56 ounce” are valid. Few invalid cases: “2 gms”, “60 ounce/1.7 kilogram”, “2.2e2 kilogram” etc.

### File Descriptions:

*source files*

1. **src/sanity.py**: Sanity checker to ensure that the final output file passes all formatting checks. Note: the script will not check if less/more number of predictions are present compared to the test file. See sample code in `src/test.ipynb` 
2. **src/utils.py**: Contains helper functions for downloading images from the image_link.
3. **src/constants.py:** Contains the allowed units for each entity type.
4. **sample_code.py:** A sample dummy code that can generate an output file in the given format. Usage of this file is optional. 

*Dataset files*

1. **dataset/train.csv**: Training file with labels (`entity_value`).
2. **dataset/test.csv**: Test file without output labels (`entity_value`). Generate predictions using your model/solution on this file's data.
3. **dataset/sample_test.csv**: Sample test input file.
4. **dataset/sample_test_out.csv**: Sample outputs for sample_test.csv.

### Dataset Download
Instructions for proper download of images form train and test are given here: 
<p align="center">
  <a href="https://github.com/VidyutChakrabarti/Data-Analysis-projects/tree/main/Feature%20Extraction%20from%20images/dataset/README.md" target="_blank">
    <img src="https://img.shields.io/badge/Dataset%20Download%20Instructions-Click%20Here-purple?style=for-the-badge" alt="Dataset Instructions Button"/>
  </a>
</p>



### Constraints

2.  The list of allowed units is given in constants.py and also in Appendix. The outputs must be in these units.

### Evaluation Criteria

Evaluated based on F1 score, which are standard measures of prediction accuracy for classification and extraction problems.

Let GT = Ground truth value for a sample and OUT be output prediction from the model for a sample. Then we classify the predictions into one of the 4 classes with the following logic: 

1. *True Positives* - If OUT != `""` and GT != `""` and OUT == GT
2. *False Positives* - If OUT != `""` and GT != `""` and OUT != GT
3. *False Positives* - If OUT != `""` and GT == `""`
4. *False Negatives* - If OUT == `""` and GT != `""`
5. *True Negatives* - If OUT == `""` and GT == `""` 

Then, F1 score = 2*Precision*Recall/(Precision + Recall) where:

1. Precision = True Positives/(True Positives + False Positives)
2. Recall = True Positives/(True Positives + False Negatives)

### Appendix

```
entity_unit_map = {
  "width": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "depth": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "height": {
    "centimetre",
    "foot",
    "millimetre",
    "metre",
    "inch",
    "yard"
  },
  "item_weight": {
    "milligram",
    "kilogram",
    "microgram",
    "gram",
    "ounce",
    "ton",
    "pound"
  },
  "maximum_weight_recommendation": {
    "milligram",
    "kilogram",
    "microgram",
    "gram",
    "ounce",
    "ton",
    "pound"
  },
  "voltage": {
    "millivolt",
    "kilovolt",
    "volt"
  },
  "wattage": {
    "kilowatt",
    "watt"
  },
  "item_volume": {
    "cubic foot",
    "microlitre",
    "cup",
    "fluid ounce",
    "centilitre",
    "imperial gallon",
    "pint",
    "decilitre",
    "litre",
    "millilitre",
    "quart",
    "cubic inch",
    "gallon"
  }
}
```
