
Method of summarizing data (numerical measures)

## Measure of location

### Medium

If the size of the set is odd then the medium is just the middle value

If the median is not unique in the case of an even number of observations, the average of the middle two observations is chosen for convenience.

Medium is more **Robust** than the mean. (not affected by outliners)


### Mode

The most frequent data



## Measure of variability or dispersion

### Percentiles and quantiles

There are multiple ways to compute quantiles in a discrete distribution.

The 25th, 50th, and 75th percentiles are known as **quartiles**

The **interquartile range** or **IQR** is defined as 

$$IQR = q(0.75) - q(0.25)$$
i.e., the difference between the upper and lower quartiles, or "middle 50%"

The IQR is often used as a measure of spread instead of the crude range. It is more **robust** as it is less affected by extreme outliers.

## Measures of shape

Skewness and kurtosis defines the shape of the data

### Skewness

Data that have a long right tail have a positive sample skewness

![[Pasted image 20230912153308.png]]

### Kurtosis

Kurtosis measures whether data are concentrated in a central peak, or in the tails

![[Pasted image 20230912153731.png]]

Data that look Gaussian (or "bell-shaped") have a sample kurtosis close to 3.

Data with large tails (more prone to extreme values) have a sample kurtosis larger than 3.

Data with shorter tails (most points fall near the mean than in a normal distribution) have a sample kurtosis less than 3

Data that look uniform have a sample kurtosis close to 1.8

![[Pasted image 20230912153925.png]]

--- 

# Gaussian Data

We are often interested in whether a gaussian model is appropriate for a particular sample.

- Is the sample mean close to the sample median?
- Are appr. 95% of points within two sample standard deviations of the sample mean?
- Is the sample skewness close to 0
- Is the sample kurtosis close to 3


Statements to use when describing whether data appear to be from a Gaussian distribution:

- The sample mean and median reasonably similar
- The skewness is reasonably close to 0
- Kurtosis is reasonably close to 3
- Approx 95% of observations lie within 2 standard deviations of the mean


# Non-Gaussian Data

Any one of the numerical summaries(mean, median, mode, sample variance, sample std, range, etc) taken on its own does **NOT** provide a good summary of the entire set

A useful data summary is provided by the **five number summary**

- The minimum
- The lower quartile
- The median
- The upper (third) quartile
- The maximum

The minimum and maximum gives us a good way to catch bad data

# Graphical Summaries

## Histograms

Histograms allow us to compare the distribution of a dataset with a p.d.f

An empirical c.d.f, in contrast, lets us compare the distribution of a dataset with c.d.f. of a random variable

## Box Plots

Boxplots can help demonstrate skewness

![[Pasted image 20230914151848.png]]

## Run chart

A run chart gives a graphical summary of data which are varying over time

![[Pasted image 20230914152332.png]]

## Scatterplot

![[Pasted image 20230914152451.png]]

## Correlation

The sample correlation gives us a numerical summary of a **bivariate** dataset.

The sample correlation takes values between -1 and +1, it is a measure of the **linear** relationship between x and y.

If the value of $r$ is close to 1 then we say that there is a strong positive linear relationship between the two variates.

**Notes:**

- A strong linear relationship is not necessarily a **casual** relationship
- Just because $r = 0$ does not mean that x and y are unrelated, merely that they are **uncorrelated**
![[Pasted image 20230914153407.png]]

## Bivariate Categorical Data

The **relative risk** is the relative change in magnitude from one data to another.

For ex.

"Students with a Canadian hometown are over 3 times as likely to
like hockey!
214"

Pie Charts may be tempting, but human are bad at interpreting area, especially area and angular judgement




%% Side project idea: a note taking app that records and transcribe the audio as you are taking note and uses LLM to integrate notes to the transcription %%