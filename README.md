# Steam Game Recommender

A simple Python project that shows how a content-based recommendation
system works behind the scenes, using your own Steam library.

## How it works

1. **Get your games**: fetches your Steam library and playtime using the Steam Web API (`GetOwnedGames`).
2. **Get game metadata**: downloads genres and developers from the Steam Store API, and community tags from SteamSpy.
3. **Build your profile**: each game becomes a vector of tags. Your profile is the sum of those vectors, weighted by the time you spent playing each game (using `log(1 + hours)`, so a single game doesn't dominate).
4. **Find candidates**: searches SteamSpy forr games with your most common tags, removing the ones you already own.
5. **Rank them**: compares your profile with each candidate using **cosine similarity** and returns the closest matches.

## Tech stack

- Python
- pandas
- NumPy
- scikit-learn
- requests

