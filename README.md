# **Parametric Crop Insurance for Indore's Soyabean Farmers**

## **The Problem**

For soyabean farmers in Indore, the October harvest is a critical time. Unfortunately, it's also a time when a few days of heavy, sustained rain can wipe out a season's hard work. Traditional crop insurance often involves slow, complicated claims processes, meaning farmers don't get the money they need when they need it most.

## **Our Solution: A Simpler, Faster Insurance**

We've designed a **parametric insurance product** that's built to be simple, transparent, and fast.

Instead of assessing individual farm damage, our product pays out automatically based on a single, clear metric: **the heaviest 5-day rainfall total** during the harvest month of October.

* **What's Covered**: Financial loss from excessive rainfall.  
* **Who It's For**: Soyabean farmers in the Indore Block.  
* **When It's Active**: October 1st to 31st.  
* **Coverage Amount (Sum Insured)**: **₹50,000 per acre**.

This approach is designed to capture the kind of prolonged, soaking rain that causes the most damage, leading to waterlogged fields and ruined crops.

## **How We Built It**

Our work was entirely data-driven, using 20 years of historical weather data (2005-2024) for the Indore region.

1. **Combined the Data**: First, we averaged the daily rainfall from 15 different weather grid points to get a single, representative rainfall number for the entire Indore Block each day.  
2. **Defined the Index**: We then calculated our key metric—the "Maximum 5-Day Rolling Cumulative Rainfall"—for every October in the last 20 years. This gave us a clear history of severe rain events.  
3. **Set the Triggers**: We used the historical data to define three payout tiers based on how rare and severe a rainfall event was:  
   * **Tier 1 (Severe)**: A 1-in-5-year rainfall event (exceeds the 80th percentile).  
   * **Tier 2 (Extreme)**: A 1-in-10-year event (exceeds the 90th percentile).  
   * **Tier 3 (Catastrophic)**: A 1-in-20-year event (exceeds the 95th percentile).  
4. **Calibrated the Payouts**: Finally, we ran a simulation to see how often these triggers would have been hit historically. We adjusted the payout amounts for each tier to ensure the product was priced fairly, targeting a final premium rate of **5%** of the sum insured.

## **The Final Product**

Here’s a summary of the designed insurance cover:

| Tier | Trigger (Max 5-Day Rainfall) | Payout (% of Sum Insured) | Payout Amount (per Acre) |
| :---- | :---- | :---- | :---- |
| **Tier 1 (Severe)** | \> 90.08 mm | 14.29% | ₹7,143 |
| **Tier 2 (Extreme)** | \> 116.32 mm | 28.57% | ₹14,286 |
| **Tier 3 (Catastrophic)** | \> 132.89 mm | 57.14% | ₹28,571 |

* **Final Premium Rate**: **5.00%**  
* **Premium Cost Per Acre**: **₹2,500**

## **Why This Approach is Better**

* **Objective & Transparent**: Payouts are based on publicly available weather data. There are no subjective, on-the-ground damage assessments.  
* **Fast**: Claims can be processed and paid almost instantly, getting cash to farmers quickly after a bad harvest.  
* **Simple Rules**: The trigger levels and payout amounts are set in advance. Everyone knows the rules from the start.

## **How to Run the Analysis**

Want to see the code?

1. **Get the Files**: Make sure the Jupyter Notebook (insurance\_analysis.ipynb) and the data (Historical Weather Data \- ERA5-Land Rain Data.csv) are in the same folder.  
2. **Install Libraries**: You'll need a Python environment with pandas and numpy.  
3. **Launch Jupyter**: Open your terminal, navigate to the folder, and run jupyter notebook.  
4. **Run the Cells**: Open the .ipynb file and run the cells to see the analysis unfold.