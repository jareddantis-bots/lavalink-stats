lavalink-stats
=============

Expose Lavalink's stats via a simple REST API. Supports multiple Lavalink instances.

## Usage

1. Install the requirements with `pip install -r requirements.txt`. Make sure to use a virtual environment.
2. Create a file named `config.ini` in the same directory as `main.py` using the format in `config.ini.example`.
3. Run `main.py`. Tested on Python 3.10, but should work on 3.6+.

## Output

A single endpoint is made available at `/stats/<node_name>`. The output is a JSON object with format like the following:

```json
{
    "stats": {                   // The stats object received from Lavalink
        "cpu": {
            "cores": 3,
            "lavalinkLoad": 0.4416202135396792,
            "systemLoad": 0
        },
        "memory": {
            "allocated": 1006632960,
            "free": 467637192,
            "reservable": 1006632960,
            "used": 538995768
        },
        "op": "stats",
        "players": 6,
        "playingPlayers": 2,
        "uptime": 9639740844
    },
    "timestamp": 1670847028747   // Time at which the stats were received from Lavalink
}
```
