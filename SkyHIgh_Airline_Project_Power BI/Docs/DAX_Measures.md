# DAX Measures

All measures are created in Power BI Desktop with **Home > New measure**.

## Required measures (from the project brief)

```DAX
-- 1. Total number of flights
Total Flights = COUNTROWS ( Airline_Flights )

-- 2. On-time rate for flights
On-Time Rate =
DIVIDE (
    CALCULATE ( COUNTROWS ( Airline_Flights ), Airline_Flights[Status] = "On-time" ),
    COUNTROWS ( Airline_Flights )
)

-- 3. Average delay (minutes)
Avg. Delay = AVERAGE ( Airline_Flights[Delay (min)] )

-- 4. Total revenue
Overall Revenue = SUM ( Airline_Revenue[Total Revenue] )

-- 5. Average feedback score
Avg. Feedback Score = AVERAGE ( Airline_Passengers[Feedback Score] )

-- 6. Frequent flyer rate
Frequent Flyer Rate =
DIVIDE (
    CALCULATE ( COUNTROWS ( Airline_Passengers ), Airline_Passengers[Frequent Flyer] = "Y" ),
    COUNTROWS ( Airline_Passengers )
)
```

## Supporting measure

```DAX
Total Flights = DISTINCTCOUNT(Airline_Flights[Flight ID]) 
Total Passengers = DISTINCTCOUNT(Airline_Passengers[Passenger ID])
```


## Where each measure is used

| Measure | Visual |
|---|---|
| Total Flights | Page 1 card, map bubble size |
| Total Passengers | Page 1 card, Page 3 card and charts |
| Overall Revenue | Page 1 card |
| Avg. Delay | Page 1 card, Page 2 cards and charts |
| Flights by Status | Page 1 column chart |
| Average Delay by Route | Page 2 bar chart |
| Flights by Aircraft Type | Page 2 column chart |
| On-Time Rate | Page 2 card |
| Avg. Feedback Score | Page 3 card, scatter plot |
| Frequent Flyer Rate | Page 3 card, scatter plot |
| Avg. Age | Page 3 card |

## Values to check against the full dataset

| Measure | Result |
|---|---|
| Total Flights | 3,000 |
| On-Time Rate | 58.57% |
| Avg. Delay | 14.95 min |
| Overall Revenue | 1,261,785 |
| Avg. Feedback Score | 3.00 |
| Frequent Flyer Rate | 31.2% |

## Model relationships

- `Airline_Airports[Airport Code]` to `Airline_Flights[Source]` (one-to-many, active)
- `Airline_Flights[Flight ID]` to `Airline_Passengers[Flight ID]` (one-to-many)
- `Airline_Flights[Flight ID]` to `Airline_Revenue[Flight ID]` (one-to-many)
