# khurshe_kuas
Before:

The dataset used in this work consisted of simultaneous glucose measurements and multi-modal wearable data.
Glucose was sampled every 5 minutes using a Dexcom G6 CGM sensor.
Blood Volume Pulse (BVP), Tri-axial Accelerometer (acc_x, acc_y, acc_z), Electrodermal Activity (EDA), Skin Temperature (Temp), and Heart Rate data were sampled at the following sampling resolutions from the Empatica E4:

BVP: 64 Hz
acc_x, acc_y, acc_z: 32 Hz
EDA: 4 Hz
Temp: 4 Hz
HR: 1 Hz

The following pipeline was applied for initial pre-processing:

Tri-axial accelerometry data was used to compute the vector magnitude of the acceleration (ACC).
Outlier removal and filtering
i) HR and Temp signals were filtered in the time-domain by removing infeasible values.
ii) EDA, ACC, and BVP signals were filtered in the frequency-domain using the following filters:
EDA: low-pass filter, cutoff = [0.5] ​ACC: band-pass filter, cutoff = [0.29, 10] ​BVP: band-pass filter, cutoff = [0.5, 5]
Epoch-wise segmentation
Each signal was segmented into 5-minute epochs based on the available glucose timestamps.
Missing value imputation

Now: 

I computed all available Cross Entropies between pairs of signals and calculated the epoch-wise cross-correlation/pearson’s correlation between all combinations of signal pairs. In order to interpret the calculation, I compared male and female subjects, as well as subjects with HbA1C levels in the High-Normal (HN) range (5.2–5.6) and subjects classified as Prediabetes (PD) with HbA1C levels of 5.7–6.4. I stated low: 0.00−0.33, moderate: 0.34−0.66, high: 0.67 and above (including values greater than 1.0)

Future:

transforming the signal to normal distribution before calculating pearson correlation
calculating pearson correlation separted by glucose level
longer epoch size - more than 5 mins - to get a more significant change when graining the signal
