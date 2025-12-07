
# DAX Measures Reference

## 1. Admissions

Total Admissions =
COUNTROWS('Admissions')

## 2. Length of Stay

Avg LOS =
AVERAGE('Admissions'[length_of_stay])

Avg LOS (All) =
CALCULATE([Avg LOS], ALL('Admissions'))

LOS Efficiency Score =
IF([Avg LOS] <= [Avg LOS (All)], 1, 0)

## 3. Cost Measures

Total Charges = SUM('Admissions'[total_charges])

Total Costs = SUM('Admissions'[total_costs])

Avg Cost per Stay =
AVERAGE('Admissions'[total_costs])

Avg Cost per Stay (All) =
CALCULATE([Avg Cost per Stay], ALL('Admissions'))

## 4. Profitability

Profit Margin =
DIVIDE([Total Charges] - [Total Costs], [Total Charges])

## 5. Severity Metrics

Extreme Severity Count =
CALCULATE(COUNTROWS('Admissions'),
'Admissions'[Severity] = "Extreme")

% Extreme Severity =
DIVIDE([Extreme Severity Count], [Total Admissions])

## 6. Cost-to-Charge Ratio

Cost-to-Charge Ratio =
DIVIDE([Total Costs], [Total Charges])

## 7. Dynamic Titles

Dynamic Title =
VAR Facility = SELECTEDVALUE('Facilities'[Facility])
VAR County = SELECTEDVALUE('Facilities'[County])
VAR Area = SELECTEDVALUE('Facilities'[Health Service Area])
RETURN
IF(NOT ISBLANK(Facility), Facility,
IF(NOT ISBLANK(County), County,
IF(NOT ISBLANK(Area), Area, "All Facilities")))

## 8. Dynamic Recommendation Engine

Hospital Recommendation =
SWITCH(
    TRUE(),
    [Avg LOS] > [Avg LOS (All)],
        "Reduce LOS by improving discharge planning and patient flow.",
    [Avg Cost per Stay] > [Avg Cost per Stay (All)],
        "Optimize cost drivers and review clinical resource usage.",
    [% Extreme Severity] > 0.25,
        "Strengthen critical care capacity and emergency preparedness.",
    [Avg LOS] <= [Avg LOS (All)] &&
    [Avg Cost per Stay] <= [Avg Cost per Stay (All)],
        "Hospital performing efficiently. Maintain operational excellence.",
    "Monitor performance trends to identify improvement opportunities."
)


