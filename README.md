# TheSpread.io API

An API that aggregates sports betting odds/lines.

This API is FREE and designed to be easy to read and integrate with.

This API is currently in beta. The two available endpoints are:

 - https://thespread.azureedge.net/odds/nfl.json
 - https://thespread.azureedge.net/odds/college-football.json
 
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
                "OverUnder": "37.5; o: -111; u: -109"
            },
            {
                "Source": "Westgate",
                "Team1Spread": "CHI -10 (-110)",
                "Team1Money": "CHI -550",
                "Team2Spread": "BUF +10 (-110)",
                "Team2Money": "BUF +400",
                "OverUnder": "38; o: -110; u: -110"
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
                "OverUnder": "54.5; o: -115; u: -105"
            },
                        {
                "Source": "Westgate",
                "Team1Spread": "TB +6 (-110)",
                "Team1Money": "TB +230",
                "Team2Spread": "CAR -6 (-110)",
                "Team2Money": "CAR -280",
                "OverUnder": "56; o: -110; u: -110"
            }
        ]
    }
]
```

The Odds Sources that are currently available within each file/for each event:
 - Caesar's
 - Unibet
 - Westgate
 - William Hill
 - Wynn


Note: there is no guarantee of accuracy at this time


Please feel free to open issues with any questions you may have.
