# World Cup Database ⚽

A PostgreSQL database project that stores and queries data from the 2014 and 2018 FIFA World Cup tournaments.

Part of the **FreeCodeCamp Relational Database** certification.

## ✨ Features

- Relational database with `teams` and `games` tables
- Script to insert data from a CSV file
- Collection of useful SQL queries (goals, winners, rounds, etc.)
- Clean normalized schema with foreign keys

## 📊 Database Schema

### `teams` table
| Column   | Type         | Description          |
|----------|--------------|----------------------|
| team_id  | SERIAL       | Primary Key          |
| name     | VARCHAR      | Unique team name     |

### `games` table
| Column         | Type         | Description                  |
|----------------|--------------|------------------------------|
| game_id        | SERIAL       | Primary Key                  |
| year           | INT          | Tournament year (2014/2018)  |
| round          | VARCHAR      | Round name (Final, Semi-Final, etc.) |
| winner_id      | INT          | Foreign key → teams.team_id  |
| opponent_id    | INT          | Foreign key → teams.team_id  |
| winner_goals   | INT          | Goals scored by winner       |
| opponent_goals | INT          | Goals scored by opponent     |

## 🚀 How to Use

### 1. Create the database
```bash
psql -U freecodecamp -c "CREATE DATABASE worldcup;"
