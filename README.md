# British Airways Data Science Job Simulation 

– Task 1

## Objective

Develop a scalable lookup table to estimate passenger eligibility for British Airways lounges at Heathrow Terminal 3 and support future lounge demand forecasting.

---

## Business Problem

British Airways needs a flexible way to estimate future lounge demand without relying on specific flight schedules, aircraft types, or flight numbers.

The goal is to identify the percentage of passengers likely to be eligible for each lounge tier and create a reusable model that can be applied to future schedules.

---

## Lounge Tiers

### Tier 1 – Concorde Room

Premium lounge access for the highest-tier passengers.

### Tier 2 – First Lounge

Access for First Class passengers and eligible loyalty members.

### Tier 3 – Club Lounge

Access for Business Class passengers and eligible frequent flyers.

---

## Data Preparation

The flight schedule dataset was analyzed using the following information:

* Arrival Region
* Haul Type
* First Class Seats
* Business Class Seats
* Economy Seats
* Tier 1 Eligible Passengers
* Tier 2 Eligible Passengers
* Tier 3 Eligible Passengers

### Additional Calculations

**Total Seats**

```text
Total Seats = First Class Seats + Business Class Seats + Economy Seats
```

**Eligibility Percentage**

```text
Eligibility % = Eligible Passengers ÷ Total Seats × 100
```

---

## Flight Grouping Method

Flights were grouped by destination region:

* Europe
* North America
* Asia
* Middle East

This approach was chosen because passenger profiles and lounge demand are likely to differ by region while remaining applicable to future schedules.

---

## Lounge Eligibility Lookup Table

| Region        | Tier 1 (Concorde Room) | Tier 2 (First Lounge) | Tier 3 (Club Lounge) |
| ------------- | ---------------------- | --------------------- | -------------------- |
| Asia          | 0.21%                  | 2.86%                 | 10.98%               |
| Europe        | 0.34%                  | 4.40%                 | 16.85%               |
| Middle East   | 0.22%                  | 2.85%                 | 10.90%               |
| North America | 0.22%                  | 2.95%                 | 11.23%               |

---

## Methodology

* Calculated total seats for each flight.
* Calculated Tier 1, Tier 2, and Tier 3 eligibility percentages.
* Created Pivot Tables to calculate average eligibility percentages by region.
* Used these averages to create a reusable lookup table for future demand forecasting.

---

## Key Findings

* Europe showed the highest lounge eligibility across all tiers.
* Tier 3 (Club Lounge) demand was significantly higher than Tier 1 and Tier 2 demand.
* Tier 1 eligibility remained very low across all regions.
* The lookup table provides a scalable solution for estimating future lounge demand.

---

## Business Impact

The lookup table can help British Airways:

* Forecast future lounge demand.
* Plan lounge capacity and staffing requirements.
* Allocate food and facility resources efficiently.
* Support future investment decisions for premium lounge facilities.

---

## Conclusion

This project developed a simple and scalable lounge demand forecasting model using regional flight groupings and passenger eligibility percentages. The resulting lookup table enables British Airways to estimate future lounge usage and improve operational planning at Heathrow Terminal 3.

---

– Task 2

## Objective

Build a machine learning model to predict whether a customer will complete a booking and identify the factors that influence booking behaviour.

---

## Dataset

The dataset contains **50,000 customer booking records** with the following features:

* Number of Passengers
* Sales Channel
* Trip Type
* Purchase Lead
* Length of Stay
* Flight Hour
* Flight Day
* Route
* Booking Origin
* Wants Extra Baggage
* Wants Preferred Seat
* Wants In-Flight Meals
* Flight Duration

### Target Variable

**booking_complete**

* 1 = Booking Completed
* 0 = Booking Not Completed

---

## Data Preparation

The following preprocessing steps were performed:

* Checked for missing values and data quality issues.
* Converted categorical variables into numerical values using Label Encoding.
* Converted flight day values into numerical format.
* Split the dataset into:

  * Training Set (80%)
  * Testing Set (20%)

---

## Model Development

A **Random Forest Classifier** was used to predict customer booking completion.

### Libraries Used

* pandas
* numpy
* matplotlib
* scikit-learn

---

## Model Performance

| Metric                 | Value  |
| ---------------------- | ------ |
| Accuracy               | 85.41% |
| Cross Validation Score | 48.56% |

### Interpretation

The model achieved an accuracy of **85.41%**, indicating strong performance on the test dataset. However, the lower cross-validation score suggests that additional tuning and feature engineering may improve model consistency and generalization.

---

## Feature Importance Analysis

The most important factors influencing booking completion were:

1. Purchase Lead
2. Route
3. Flight Hour
4. Length of Stay
5. Booking Origin

### Key Insights

* Customers who book earlier are more likely to complete a booking.
* Flight route and departure time strongly influence booking decisions.
* Length of stay and booking origin also affect booking behaviour.
* Trip type and additional services such as baggage, meals, and preferred seats have a smaller impact on booking completion.

---

## Business Insights & Recommendations

### Insights

* Early bookings have a higher likelihood of conversion.
* Route and flight timing are major drivers of booking behaviour.
* Customer travel patterns provide useful information for predicting purchases.

### Recommendations

* Target early-booking customers with personalized offers.
* Focus marketing campaigns on key routes and travel periods.
* Use predictive analytics to improve customer targeting and conversion rates.
* Continuously improve the model by incorporating additional customer and booking data.

---

## Conclusion

The Random Forest model successfully identified the key factors influencing customer booking behaviour. **Purchase Lead** was the strongest predictor, followed by **Route** and **Flight Hour**. These insights can help British Airways improve customer targeting, optimize marketing strategies, and increase booking conversion rates.

---



