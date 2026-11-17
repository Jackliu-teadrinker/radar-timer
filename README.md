# radar-timer

External timer for [ai-news-radar](https://github.com/Jackliu-teadrinker/ai-news-radar).

ai-news-radar is a **fork** (parent: LearnPrompt/ai-news-radar), and GitHub throttles `schedule`
triggers on forks: on 2026-11-17 only 1 of 24 hourly slots fired. This repo is a standalone
public repo, so its schedules trigger normally.

Every 15 min it reads the radar Pages freshness; when data is older than 22 min with no run in
flight, it dispatches `update-news.yml` through the Actions API (PAT).

Requires repo secret `RADAR_PAT` (token with `repo` + `workflow` scope on ai-news-radar).
