# How Health Lifestyle Habits Predict America’s Excess Weight Crisis

I picked this topic since health is very personal to me; I see good health as a prerequisite for everything we ought to accomplish in this life, and poor health as a waste of potential.

---

## The Dataset
The dataset in this project originates from the Center for Disease Control and Prevention (CDC), specifically titled “Nutrition, Physical Activity, and Obesity - Behavioral Risk Factor Surveillance System” (BRFSS). 

It’s a massive telephone survey that aims to track health behaviors, chronic conditions, and how people take care of themselves across all 50 states and U.S. territories. 

### Limitations & Biases
While the CDC is highly reputable as an official U.S. government source, there are a few built-in downsides to the data:
* **Self-Reported Data:** Due to human bias, respondents tend to underreport their actual weight and exaggerate their consumption of fruits/vegetables along with how much they exercise.
* **Sampling Bias:** The survey risks missing populations who are too busy to answer the phone or who refuse to participate altogether (though the CDC applies statistical weighting to try and counteract this).

---

## Data Cleaning & Methodology
I cleaned the data using a Google Colab notebook. Because the original dataset was incredibly messy—with numbers fragmented by age, gender, and education—I took the following steps:

1. **Demographic Filtering:** I filtered the dataset to look only at rows where Stratification1 was equal to 'Total'. This removed the individual demographic splits and isolated the overall state totals.
2. **Pivoting the Data:** Different health questions were asked in different years, leaving many rows missing values. I executed a pivot operation using LocationDesc (states/territories) as my rows, and turned every unique CDC question asked over the years into individual columns.
3. **Aggregating with Mean:** I averaged out the percentages over multiple years using the mean operation. I chose mean over median because large state-level percentages do not contain extreme outliers. Using the median would have simply grabbed the middle value and ignored the rest, eliminating subtle year-to-year shifts.
4. **Combining Metrics:** I decided to combine both the overweight and obesity columns to get a clearer picture. When kept separate, the correlations were unintuitive and misleading (e.g., there was a confusing positive correlation between overweight rates and exercise, likely because overweight individuals were actively exercising to lose weight, whereas obese individuals faced higher barriers to doing so).

---

## Insights & Ethical Considerations

The data clearly shows how much of America’s excess weight crisis can be linked to lifestyle interventions. However, it is worth noting that the figures here appear slightly outdated; the combined overweight and obesity rate in America has jumped from the 65.6% shown in this dataset to 72.4% in recent estimates.

> ### Ethical Concern
> There is a risk that people may use these numbers to body-shame individuals or make jokes about Southern states and their cuisine. Obesity is a systemic and cultural issue in the U.S., not a failure of personal willpower. Reporting on these numbers without this vital context downplays systemic flaws and unfairly places the blame on individuals.

### Moving the Story Forward
To make this a more complete and ethical piece of journalism, we must look at local environments and socioeconomic factors:
* **Built Environment:** Colorado consistently tracks among the states with the lowest obesity rates. This is largely because active recreation is a social norm backed by infrastructure—cities are deeply ingrained with parks, hiking trails, and bike lanes, making active commuting a default option.
* **Socioeconomic Factors:** Poverty and low income are strictly associated with excess weight. It is no coincidence that the Southern states scoring the highest in obesity rates also happen to be the states struggling with the highest poverty rates in the nation.
