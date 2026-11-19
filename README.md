# House Edge Index

A static data project that collects published and calculated house edge and RTP figures for common casino games. It is hosted as a GitHub Pages site. It is not a casino, a bonus page or a sales site.

The live page is at:

https://makedatskrilla.github.io/house-edge-index/

## Files

- `index.html` is the index itself: tables, methodology and sources, with inline CSS.
- `data/house-edge.csv` is the same dataset, one row per game variant, ready to reuse (including as a later Kaggle dataset).
- `LICENSE` is Creative Commons Attribution 4.0 for the data and the page text.
- `sitemap.xml` and `robots.txt` assume the Pages URL above. Update them if the username or repo name changes.

## CSV columns

| Column | Meaning |
| --- | --- |
| category | roulette, blackjack, baccarat, craps, video_poker, crypto_originals, slots, game_shows, keno, sportsbook, pvp |
| game | Game family |
| variant | Rules, paytable or operator-specific version |
| operator | Typical, Duel, Stake, or a typical crypto casino |
| rules | Short ruleset or paytable note |
| house_edge_percent | Raw house edge, empty when only a range is known |
| house_edge_low, house_edge_high | Bounds. Equal to the point figure when the number is exact. |
| rtp_percent, rtp_low, rtp_high | Return to player, same pattern |
| net_house_edge_percent | Edge after a published rakeback or refund. Same as the raw edge when no refund applies. |
| condition | Limits, strategy assumptions, or other constraints |
| method | exact_calculation, published_reference, published_operator, or published_tracker |
| source | Where the figure comes from, in words |
| source_url | The page that was checked |
| last_checked | ISO date of the check (Europe/Stockholm) |

All percentages are written without a percent sign, so 2.70% appears as `2.7027` when the exact fraction is known, and as `0.4561` for the Wizard of Odds 9/6 Jacks or Better total.

## How the numbers were built

Roulette edges are exact fractions (1/37, 2/38, 3/38, 3/39, 0.5/37) and were checked against Wizard of Odds. Baccarat, craps, Jacks or Better paytables, the land-keno range and the typical online blackjack band come from Wizard of Odds pages fetched on 19 November 2026. Duel's own pages were checked first. The zero-edge FAQ, the referral FAQ and the economics changelog are the primary source for Duel's published refund model, for Beef at 100% RTP, and for the blackjack scaling steps. ProvablyFair.org's audit is an independent earlier measurement of raw math, not the primary source for Duel's current published RTP. Live-game RTPs, the 99.39% video poker top tier and Duel Arena rake come from live WhyDuel pages that quote Duel's game info. Stake Original blackjack at 0.57% is recorded on those pages from a Stake game-page Wayback capture. FairGambling averages were read from FairGambling's Duel and Stake pages, including Stake's 99.0% top house-game line.

Every row has a source or an exact calculation. No figure was invented to fill a gap. A range stays a range.

The full write-up, including how 0% vs 0.57% is used for blackjack within Duel's daily limits, is in `index.html`.

## Pages setup

GitHub Pages deploys from the root of the default branch. No custom domain is used. The live URL is https://makedatskrilla.github.io/house-edge-index/. After a deploy, open that URL and confirm that `index.html` and `data/house-edge.csv` both load.

## License

Data and page text: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Please credit "House Edge Index" and link back to the Pages URL when you reuse the tables.

This project is not affiliated with, endorsed by or operated by any casino.
