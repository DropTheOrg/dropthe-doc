# Data Freshness

Streaming availability changes constantly. Here's how [DropThe](https://dropthe.org) keeps records current.

## Update Frequency

- **Daily scans**: Automated pipelines check platform catalogs every 24 hours
- **Event-driven updates**: Major platform announcements trigger immediate re-scans
- **Staleness detection**: Records older than 7 days are flagged for priority refresh

## Accuracy

No streaming tracker is 100% accurate in real-time -- platforms can add or remove content at any moment. DropThe aims for next-day accuracy on major platforms and publishes the last-verified timestamp on entity pages.

## Coverage Gaps

If a movie or series on [dropthe.org](https://dropthe.org) shows no streaming data, it may be:
- Not currently available on any tracked platform
- Available on a platform we don't yet track
- Recently added and not yet captured in the daily scan

We continuously expand platform coverage and improve scan frequency.
