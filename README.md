# TheSpread.io API

An API that aggregates sports betting odds/lines.

This API is **FREE** and designed for readability and easy integration.


# Requests

This API is currently in beta. The two available endpoints are:

 - https://thespread.azureedge.net/odds/nfl.json
 - https://thespread.azureedge.net/odds/college-football.json

This API will eventually be hosted at api.thespread.io

# Response

The structure of an odds json response is similar to the following:

```
[
    {
        "Event": "Bears at Buffalo",
        "Date": "2018-11-04T18:00:00+00:00",
        "Odds": [
            {
                "Source": "Unibet",
                "Team1Spread": "CHI -10 (-111)",
                "Team1Money": "CHI -500",
                "Team2Spread": "BUF +10 (-109)",
                "Team2Money": "BUF +360",
                "OverUnder": "37.5 -111/-109"
            },
            {
                "Source": "Westgate",
                "Team1Spread": "CHI -10 (-110)",
                "Team1Money": "CHI -550",
                "Team2Spread": "BUF +10 (-110)",
                "Team2Money": "BUF +400",
                "OverUnder": "38 -110/-110"
            }
        ]
    },
    {
        "Event": "Tampa Bay at Carolina",
        "Date": "2018-11-04T18:00:00+00:00",
        "Odds": [
            {
                "Source": "Unibet",
                "Team1Spread": "TB +6.5 (-110)",
                "Team1Money": "TB +245",
                "Team2Spread": "CAR -6.5 (-110)",
                "Team2Money": "CAR -312",
                "OverUnder": "54.5 -115/-105"
            },
            {
                "Source": "Westgate",
                "Team1Spread": "TB +6 (-110)",
                "Team1Money": "TB +230",
                "Team2Spread": "CAR -6 (-110)",
                "Team2Money": "CAR -280",
                "OverUnder": "56 -110/-110"
            }
        ]
    }
]
```

Notes:
 - Response contains Events within the past 48 hours, and known future events.
 - Spread, Money Line, and O/U values may contain `null`.
 - Not all Sources will exist for every Event.
 - Not all Events will always be listed.

## How to read the odds:

<br /> 

 **Spread**: "`[TeamAbbreviation] [PointSpread] ([Vigorish])`"

| Value Part | Description |
| --- | --- |
| TeamAbbreviation | Shortened Team Name/Identifier. |
| PointSpread | The point spread that should be applied to that team's final score.<br />ex: A value of `-5` would mean that team needs to win by more than 5 points.<br />ex: A value of `+10` would mean that team needs to lose by less than 10 points. |
| Vigorish | aka: Juice, Vig, Cut, Take.<br />The amount of money to risk/lay for a $100 bet.<br />ex: A value of `-110` means a better would need to lay $110 to win $100. |

<br />

**MoneyLine**: "`[TeamAbbreviation] [MoneyLine]`"

| Value Part | Description |
| --- | --- |
| TeamAbbreviation | Shortened Team Name/Identifier. |
| MoneyLine | The amount of money to risk/lay for a $100 bet.<br />ex: A value of `-500` means a better would need to lay $500 to win $100.<br />ex: A value of `+360` means a better would need to lay $100 to win $360.<br />note: Unlike a Point Spread bet, the team needs to win outright. |

<br />

**OverUnder**: "`[TotalPoints] [OverLine]/[UnderLine]`"

| Value Part | Description |
| --- | --- |
| TotalPoints | A value that represents the estimated combined final scores of both teams. The total points scored during the Event. This is the value the better is betting against, will the combined final score be over or under this value. |
| OverLine | The amount of money to risk/lay for a $100 bet if the better believes the total points scored will be over/more than the TotalPoints value.<br />ex: A value of `-110` means a better would need to lay $110 to win $100. |
| UnderLine | The amount of money to risk/lay for a $100 bet if the better believes the total points scored will be under/less than the TotalPoints value.<br />ex: A value of `-110` means a better would need to lay $110 to win $100. |


<br />

# Data Source

The Odds Sources that are currently available within each file/for each event:
 - Caesar's
 - Unibet
 - Westgate
 - William Hill
 - Wynn

Note: there is no guarantee of accuracy at this time.


# Roadmap

Short roadmap of future enhancements:
 - Include 'open' values
 - Include 'last change date' values and previous value
 - Include local event time in addition to UTC time
 - Include complete history of lines for a single event
 
# Questions/Comments

Please feel free to open issues with any questions you may have.

