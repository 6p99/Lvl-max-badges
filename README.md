# Lvl-badges — Usage Guide

## 1. Requirements

- Python 3.10 or newer
- Windows for the fingerprint feature
- An active internet connection

No additional Python packages are required for the provided script.

## 2. Running the Script

Open CMD in the folder containing `script.py` and run:

```cmd
py script.py
```

If that doesn't work, try:

```cmd
python script.py
```

## 3. First Run

On the first launch, the script may ask for:

- `token` — Your Discord account token.
- `cookie` — The required session cookie data.

**Security note:** Never share your account token or session cookies with anyone.

## 4. Main Menu

The script provides the following options:

```text
1 · claim games
2 · refresh auth
3 · set fingerprint
4 · exit
```

- **1 — Claim Games:** Select the number of games and the duration value per game.
- **2 — Refresh Auth:** Attempt to refresh authentication data.
- **3 — Set Fingerprint:** Generate a fingerprint associated with an executable or running process.
- **4 — Exit:** Close the script.

## 5. Files

- `script.py` — Main Python script.
- `science_state.json` — Stores the script's state and configuration.
- `data/games.json` — Local game list, if available.

## 6. Troubleshooting

- **Python not found:** Install Python and make sure it is available from CMD.
- **Game list unavailable:** Check your internet connection.
- **Authentication error:** Check the error message and review the script's authentication requirements.
- **Fingerprint error:** Make sure you're using Windows and providing a valid executable path or process ID.

## Disclaimer

This project is for educational and technical research purposes. Successful requests do not guarantee that Discord will credit playtime or update game-related statistics. Use the script responsibly and protect your account credentials.
