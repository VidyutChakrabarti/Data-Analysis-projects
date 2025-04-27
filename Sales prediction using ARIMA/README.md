## ARIMA Time series forecasting

Problem statement is to predict 3 months of item-level sales data at different store locations. 

Data contains 5 years of store-item sales data, for 50 different items at 10 different stores.

Build an ARIMA model.

Use SMAPE metric for model evaluation - https://en.wikipedia.org/wiki/Symmetric_mean_absolute_percentage_error

Data fields
date - Date of the sale data. There are no holiday effects or store closures.
store - Store ID
item - Item ID
sales - Number of items sold at a particular store on a particular date.


<div align="center">
<table border="0" cellspacing="0" cellpadding="0">
    <tr>
      <td style="padding-right: 30px;">
        <img src="assets/arimalogo.jpg" alt="Logo" width="280"/>
      </td>
      <td style="vertical-align: middle; font-size: 12px; font-weight: bold;">
        Access full inference and data explanations.<br><br>
        <a href="https://colab.research.google.com/drive/1bV5xsfM5UXhRlRGmRN-Mrz47wY-sF1R2?usp=sharing">
          <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open in Colab"/>
        </a>
      </td>
    </tr>
</table>
</div>

### Graphs at a glance: 

<div align="center">
<table border="1" cellspacing="15" cellpadding="15">
  <tr>
    <td align="center">
      <img src="assets/train.png" alt="train" width="350"/><br>
      <p>Explore the training data</p>
    </td>
    <td align="center">
      <img src="assets/predict.png" alt="predict" width="350"/><br>
      <p>See the predictions properly</p>
    </td>
  </tr>
  </table>
  </div>
