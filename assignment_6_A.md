clc %clearing the cmd window

%loading data from matlab to fill up tables
load patients
whos -file patients

%creating two tables
T1 = table(Age, SelfAssessedHealthStatus, Smoker);
T2 = table(Height, Weight, Systolic, Diastolic);

%printing the tables
head(T1, 5)
head(T2, 5)

%concatenating two tables
T = [T1, T2];
head(T, 5)

%adding new col to the merged table
T = addvars(T, LastName, 'Before', 'Age');
T.LastName = string(T.LastName);
head(T, 5)

%adding col without using addvars
T.BloodPressure = [Systolic Diastolic];
head(T, 5)

