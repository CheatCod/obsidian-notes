
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

We are often interested in whether a gaussian model is appropriate for a particular sample.

- Is the sample mean close to the sample median?
- Are appr. 95% of points within two sample standard deviations of the sample mean?
- Is the sample skewness close to 0
- Is the sample kurtosis close to 3

Side project idea: a note taking app that records and transcribe the audio as you are taking note and uses LLM to integrate notes to the transcription