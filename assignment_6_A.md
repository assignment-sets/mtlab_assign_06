# mtlab_assign_06_A

clc
load patients
whos -file patients


T1 = table(Age, SelfAssessedHealthStatus, Smoker);
T2 = table(Height, Weight, Systolic, Diastolic);

%first five rows display
head(T1, 5)
head(T2, 5)

%concatenation of tables
T = [T1, T2]
head(T1, 5)
head(T2, 5)

%adding vars in workspace in table
T = addvars(T.LastName.'Before' : 'Age');
T.Lastname = string(T.Lastname);
head(t, 5)

% add vars using dot syntax
T.BloodPressure = [Systolic Diastolic];
head(t,5)
