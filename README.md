# Encore — Festival Draft

A fantasy music festival drafting game, replacing the previous football game in the same Site. Includes 80 curated artists: 68 mainstream/legacy acts plus 12 discovery acts, including Michael Jackson, Taylor Swift, and slayr. Does not claim to include every artist.

Six slots: two headliners, two main-stage acts, two discovery-stage picks. Solo festival simulation and same-device multiplayer snake draft. Artists cannot be booked twice. Two rerolls per player. Sparse filters show a recoverable validation message.

## Ratings and provenance

Overall = normalized weighted sum of talent (50%), record performance (30%), Spotify streaming reach (20%). Talent values are subjective editorial game scores on a 0–99 scale, considering technique, songwriting/production, versatility, and performance. They are not measurable facts. Missing commercial values remain null and their weights are excluded. Talent-only overalls are explicitly provisional.

Commercial subscores use logarithmic scaling: 99 × log10(1 + value / 1 million) / log10(1 + reference / 1 million), capped at 99. References: 130 billion Spotify streams, 400 million non-stream equivalent album units. Data available for 68 artists' streaming totals and seven artists' record performance. Unknowns are never fabricated or set to zero.

Streams: ChartMasters lead-artist Spotify stream snapshot, September 29, 2026: https://chartmasters.org/most-streamed-artists-ever-on-spotify/ . Record score: estimated non-stream EAS = total EAS minus streaming EAS, September 28, 2026: https://chartmasters.org/best-selling-artists-of-all-time/ . These are estimates, not pure sales or official certifications. Removing stream EAS avoids including the same streams in both commercial components. All artist cards show their rating basis; the archive and footer expose source links and snapshot dates.

Slayr identity verified through SoundCloud: https://soundcloud.com/stories/post/slayr-exclusive-interview-sound-advice . Discovery is an editorial booking category, not a definitive claim about present popularity. Some acts are deceased; all bookings are fantasy and do not imply actual availability.

Festival result: average lineup OVR plus up to four genre-diversity points, then small simulated review/buzz variation. Crowd estimates are game fiction, not predictions. Discovery acts affect buzz. Saved results cannot be re-simulated without a new draft.

Build data: `python scripts/build_artists.py`. Serve: `python -m http.server --directory dist`. Verify: `node --check dist/game.js` and `node scripts/test_festival.cjs`.

## Test features

Daily challenges use a UTC day key, a deterministic offer generator and a lineup-derived result seed. Rating weights stay 50/30/20 in daily mode. Free custom rules normalize user weights. Cards replace unknown commercial stats with Stage appeal and Creativity, explicitly labeled derived game attributes; archive retains real source data.

Completed solo and local-versus lineups save to this browser (latest 20). A canvas generates 1080×1350 posters in Classic, Sunset or Midnight themes. Download PNG, native share when supported, or copy a validated hash-based lineup URL. The hash carries name, six artist IDs and score; no credentials. Scores are user-shareable game results and not trusted leaderboard submissions.

Visit days, return days, starts and completions are device-local only, not cross-user analytics. No ads, purchases, payment code, subscriptions or sponsors.

Budget is a fictional one-day/two-stage planning model: Discovery fee = $15,000 + Stage appeal × $700; other fee = $100,000 + (OVR/99)^4 × $1,900,000. Production = $300,000 + 35% of bookings. Overall range = ±30% of total. This is not verified real artist pricing, and deceased artists cannot actually be booked.
