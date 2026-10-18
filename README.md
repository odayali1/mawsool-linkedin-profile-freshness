# LinkedIn Profile Scraper Alternative | Current Company

**Before you pay for a LinkedIn profile scraper, get the current company and headline. Starting from $0.40 per 1,000 profiles.**

You already have the profile URLs. This Actor returns the current company and the headline. You compare those two fields to the company and headline in your CRM, Clay table, or spreadsheet. If they differ, run [LinkedIn Profile Scraper](https://apify.com/oday/mawsool-linkedin-profile-details) on those rows only.

This Actor does not decide whether a company matches. It does not ask you for the old company, and it does not return `needsUpdate`.

No LinkedIn login. No cookies. You supply the URL.

## What 10,000 profiles cost

10,000 checks cost $4. The free plan is $0.60 per 1,000. Run the full profile scraper only on the rows you choose.

## If you need a different Mawsool Actor

| If this is what you need | Open |
| --- | --- |
| You have an email and want the LinkedIn profile. | [Reverse Email Lookup](https://apify.com/oday/mawsool-email-linkedin-lookup) |
| You have a name and company and want the profile URL. | [LinkedIn Profile Finder](https://apify.com/oday/mawsool-linkedin-profile-finder) |
| You have a profile URL and want the personal email. | [LinkedIn Email Finder](https://apify.com/oday/mawsool-linkedin-personal-email-finder) |
| You want the full profile, after you decide a row changed. | [LinkedIn Profile Scraper](https://apify.com/oday/mawsool-linkedin-profile-details) |
| You have a large file of profile URLs to scrape in full. | [Mass Profile Scraper](https://apify.com/oday/mawsool-mass-linkedin-profile-scraper) |
| You want a scheduled alert when the employer or headline changes. | [Job Change Tracker](https://apify.com/oday/mawsool-linkedin-job-change-watch) |
| You want this Actor to compare a company you already stored and return needsUpdate. | [Current Company Checker](https://apify.com/oday/mawsool-linkedin-company-checker) |

## What a row looks like

```json
{
  "inputUrl": "https://www.linkedin.com/in/example",
  "fullName": "Example Person",
  "currentCompany": "Example Inc",
  "headline": "VP Sales at Example Inc",
  "linkedinNumId": "123456789",
  "success": true,
  "error": null,
  "checkedAt": "2026-10-18T12:00:00.000Z"
}
```

A failed lookup is still one row, with `success: false` and `currentCompany: null`. You are charged for each URL processed.

## How you decide who needs a full update

1. Export `currentCompany` and `headline`.
2. Compare them to the values already in your CRM. Use whatever match rule you trust.
3. Send only the rows you want refreshed to [LinkedIn Profile Scraper](https://apify.com/oday/mawsool-linkedin-profile-details).

If you would rather hand the saved company to an Actor and get `needsUpdate` back, use [Current Company Checker](https://apify.com/oday/mawsool-linkedin-company-checker). You supply the company from your CRM. That Actor does the comparison. This one does not.

## Price

One profile URL is one charge, whether or not the company is filled in.

| Plan | Per 1,000 profiles |
| --- | --- |
| Free | $0.60 |
| Bronze | $0.55 |
| Silver | $0.50 |
| Gold | $0.40 |
| Platinum | $0.40 |
| Diamond | $0.40 |

Starting from $0.40 per 1,000. Gold, Platinum, and Diamond are the same price. The free plan is $0.60 per 1,000.

## Use with AI agents

Apify exposes this Actor to ChatGPT, Claude, Gemini, Grok, and other agents through the Apify MCP server. The setup prompt is:

> I have LinkedIn profile URLs. Run Mawsool's profile freshness Actor and return the current company and headline. Do not decide if the company changed. I will compare the fields to my CRM, then run the LinkedIn profile scraper only on the rows I choose.

## FAQ

### How do I avoid paying for a full LinkedIn profile scraper on every contact?

Run this Actor on the URL list first. It returns the current company and headline, starting from $0.40 per 1,000. Compare those fields to your CRM, then scrape only the rows you want to refresh.

### Does this tell me whether the person changed jobs?

No. It returns the current company and headline. You compare them to the company and headline you already stored.

### Does this need a LinkedIn login or cookies?

No. You supply the profile URL.

### Is one URL one charge?

Yes. A row with an empty company is still a processed URL.
