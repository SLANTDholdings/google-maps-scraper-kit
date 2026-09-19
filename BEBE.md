# Lead Finder

Aliases Bebe may hear: scout, private eye, lead list, find businesses in.
Not a named library skill. Job language fires it.
Drawer: G5. Seat: Mechanic runs the box. Clerk files the CSV to Drive.

## What it is

This repo is the local box. Docker up. API at http://localhost:8080.
Give a place and a trade. Get a clean list: name, phone, email, website, category, address, rating, reviews.
Engine is gosom/google-maps-scraper (MIT). This kit is the wrapper. Credit stays in CREDITS.md.

## How AZ talks

- Scout landscapers in Mansfield TX
- Lead list of equipment rental shops in Fort Worth
- Private eye: sitework contractors in Dallas, phones and websites

## How Bebe runs it

1. Confirm the box is up: `curl -s http://localhost:8080/api/v1/jobs`
2. If down: `docker compose up -d` from this repo root.
3. Create one job. Bake the city into each keyword. Depth 5 unless AZ says otherwise.
4. Poll until done. Download CSV.
5. File the CSV to Drive G5 / Long Acre leads. Do not keep the only copy in chat.

Required job fields: keywords[], lat (string), lon (string), max_time (seconds).

## Defaults for SLANTD / Long Acre

Place: Mansfield / DFW unless AZ names another city.
Trades that matter: landscapers, sitework, fencing, mowing, property managers, municipalities, contractors who rent mini-skid or attachments.

## Not this box

Do not install onto the HOST-C2 soak machine unless AZ says this machine.
Do not invent a second OPEN card to hold this repo.
Do not copy .claude/ into slantd-ops as furniture.
