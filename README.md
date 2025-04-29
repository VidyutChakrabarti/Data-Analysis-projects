## Data Analysis Projects

This repo consists of some data analysis and data visualization projects, mostly done in Jupyter notebooks. 

The current list includes: 
***1. RHESSI - Data analysis and visualization:***
A study on the RHESSI data from NASA to interpret certain conclusions based on visualizations generated.

Inferences and detailed explaination of data can be found within the notebook.

Preview: 
<div align="center">
<table border="1" cellspacing="15" cellpadding="15">
  <tr>
    <td align="center">
      <img src="RHESSI - data analysis/assets/1.png" alt="Sun" width="180"/><br>
      <p>Values showing linear relationships</p>
    </td>
   <td align="center">
         <img src="RHESSI - data analysis/assets/2.png" alt="Sun" width="220"/><br>
         <p>Variance of EPSY w.r.t Latitudes and Longitudes</p>
       </td>
    <td align="center">
          <img src="RHESSI - data analysis/assets/3.png" alt="Sun" width="220"/><br>
          <p>R_value w.r.t parameters</p>
        </td>
    <td align="center">
          <img src="RHESSI - data analysis/assets/big2.png" alt="Sun" width="220"/><br>
          <p>Heatmaps for more visualizations</p>
        </td>
  </tr>
  </table>
  </div>

***2. Sales prediction using ARIMA:***
Problem statement is to predict 3 months of item-level sales data at different store locations.
Data contains 5 years of store-item sales data, for 50 different items at 10 different stores.
Build an ARIMA model.
Use SMAPE metric for model evaluation

Preview: 
<div align="center">
<table border="1" cellspacing="15" cellpadding="15">
  <tr>
    <td align="center">
      <img src="Sales prediction using ARIMA/assets/train.png" alt="Sun" width="350"/><br>
      <p>Explore the training data</p>
    </td>
   <td align="center">
         <img src="Sales prediction using ARIMA/assets/predict.png" alt="Sun" width="350"/><br>
          <p>See the predictions properly</p>
       </td>
  </tr>
  </table>
  </div>

***3. Feature Extraction from Images:***
The goal is to create a machine learning model that extracts entity values from images. These images provide important information such as weight, volume, voltage, wattage, dimensions, and many more, which are critical for digital stores. Based on all the extracted dimensions with units, the model must output one single "x unit" pair in consideration to the entity_name provided like "weight" or depth.

Preview: 
<div align="center">
<table border="1" cellspacing="15" cellpadding="15">
  <tr>
    <td align="center">
      <img src="Feature Extraction from images/assets/sample1.png" alt="Sample1" width="240"/><br>
      <p>Extracted entities:  ['14.0 centimetre', '26.0 centimetre', '55.0 centimetre', '23.5 centimetre', '17.0 centimetre', '23.5 centimetre', '21.0 centimetre', '19.5 centimetre']</p>
    </td>
   <td align="center">
         <img src="Feature Extraction from images/assets/sample2.png" alt="Sample2" width="250"/><br>
          <p>Extracted entities: ['12.1 centimetre', '4.76 inch', '1.0 metre', '28.3 centimetre', '11.4 inch', '17.9 centimetre', '7.04 inch', ]</p>
       </td>
    <td align="center">
         <img src="Feature Extraction from images/assets/sample3.png" alt="Sample2" width="280"/><br>
          <p>Extracted entities: ['7.0 centimetre', '4.0 centimetre', '1.5 centimetre', '1.2 metre']</p>
       </td>
  </tr>
  </table>
  <b>From the extracted entities we use another model to decide based on the group code and placement of the entity which one best fits the final result.</b>
  </div>

  #### - Please relocate to the desired folder for getting the full description of the specific project.
