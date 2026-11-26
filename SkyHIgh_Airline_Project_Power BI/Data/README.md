# Data

Four CSV files used by the Power BI report. No columns were added to the source files.

| File | Rows | Columns | Description |
|---|---|---|---|
| `Airline_Flights.csv` | 3,000 | 10 | One row per flight |
| `Airline_Passengers.csv` | 3,000 | 8 | One row per passenger |
| `Airline_Revenue.csv` | 3,000 | 5 | Ticket price, fees and total revenue per ticket |
| `Airline_Airports.csv` | 10 | 5 | Airport reference list |

## Airline_Flights.csv

| Column | Type | Description |
|---|---|---|
| Flight ID | Text | Unique flight ID (FL0001 to FL3000) |
| Airline | Text | Airline name (5 airlines in the file) |
| Source | Text | Departure airport code |
| Destination | Text | Arrival airport code |
| Departure Time | Date/time | Scheduled departure |
| Arrival Time | Date/time | Scheduled arrival |
| Status | Text | On-time, Delayed or Cancelled |
| Delay (min) | Whole number | Delay in minutes (0, 15, 30, 90 and other values up to 120) |
| Aircraft Type | Text | Airbus A320, Airbus A350, Boeing 737, Boeing 777 or Embraer 190 |
| Date | Date | Flight date |

## Airline_Passengers.csv

| Column | Type | Description |
|---|---|---|
| Passenger ID | Text | Unique passenger ID (P0001 to P3000) |
| Flight ID | Text | Flight taken (several passengers share a flight) |
| Ticket Class | Text | Economy, Business or First |
| Age | Whole number | Passenger age |
| Gender | Text | Male, Female or Other |
| Feedback Score | Whole number | Satisfaction score from 1 to 5 |
| Check-in Luggage | Text | Y or N |
| Frequent Flyer | Text | Y or N |

## Airline_Revenue.csv

| Column | Type | Description |
|---|---|---|
| Flight ID | Text | Flight the revenue belongs to (repeats, like the passengers file) |
| Ticket Price | Whole number | Base ticket price |
| Baggage Fee | Whole number | Baggage fee |
| Extras | Whole number | Extra purchases |
| Total Revenue | Whole number | Revenue for the ticket (sum = 1,261,785) |

## Airline_Airports.csv

| Column | Type | Description |
|---|---|---|
| Airport Code | Text | Three-letter code (ATL, BOS, DEN, DFW, JFK, LAX, MIA, ORD, SEA, SFO) |
| City | Text | City name (generated names, not real cities) |
| Country | Text | USA |
| Region | Text | Region label |
| On-Time % | Decimal | Given value; not used in the report |

## Notes

- Flights run only in January to May, November and December, so November looks low.
- The flights file holds five airlines. The report analyses all 3,000 flights.
- Cancelled flights carry delay minutes (90 to 120), which are included in Avg. Delay.
- The `On-Time %` column does not match the flights data. On-time rate is calculated from the Status column.
