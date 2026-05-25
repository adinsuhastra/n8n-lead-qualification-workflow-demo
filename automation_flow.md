# Automation Flow

## Trigger

Manual Trigger / webhook-style lead intake.

For the demo, the workflow starts with fictional sample data. In a real workflow, this could be replaced by:

- form submission
- CRM webhook
- spreadsheet row
- inbound email parser
- manual test trigger

## Input

Each lead contains:

- lead ID
- company
- contact name
- email
- requested service
- estimated budget
- urgency
- business fit
- source
- consent to be contacted

All sample data is fictional and safe for portfolio use.

## Processing

1. Load or receive lead records.
2. Validate required fields:
   - company
   - contact name
   - email
   - requested service
   - consent to be contacted
3. Score each lead:
   - budget level
   - urgency
   - business fit
   - completeness
   - approved contact consent
4. Categorize each lead:
   - Hot
   - Warm
   - Cold
   - Needs Review
5. Prepare a follow-up draft for Hot and Warm leads.
6. Hold all drafts for human approval.
7. Generate a report summary.

## Decision Logic

### Validation

A lead is considered complete only when:

- required fields are present
- email is present
- consent to contact is true

If consent is false or missing, the lead must not be contacted.

### Scoring

Suggested scoring:

- Complete and consented lead: 20 points
- Budget above 1000: 30 points
- Budget 500 to 999: 20 points
- Budget below 500: 8 points
- High urgency: 25 points
- Medium urgency: 15 points
- Low urgency: 5 points
- Strong fit: 25 points
- Medium fit: 15 points
- Low fit: 5 points

### Routing

- Hot: score 75 or above, complete, and consented.
- Warm: score 50 to 74, complete, and consented.
- Cold: score below 50, complete, and consented.
- Needs Review: missing required information or no contact consent.

## Human Approval Checkpoint

No follow-up message should be sent automatically.

Before any outreach, a human should review:

- source/platform rules
- contact consent
- lead category
- follow-up draft accuracy
- whether the message is appropriate and non-spammy

## Output

The workflow returns:

- lead ID
- company
- score
- category
- validation status
- recommended next action
- follow-up draft if appropriate
- approval status

## Error Handling

Possible error handling rules:

- Missing email: route to Needs Review.
- No consent: do not contact, route to Needs Review.
- Missing budget: use conservative scoring and ask for clarification.
- Duplicate company: flag for merge review.
- Invalid source: hold record.
- Unclear requested service: ask for clarification before scoring as Hot.

## Future Real Implementation Ideas

If implemented in real n8n, safe next steps could include:

- Use a Webhook node for intake.
- Use Code nodes for scoring and validation.
- Use IF/Switch nodes for routing.
- Use Google Sheets, Airtable, or a CRM as a storage layer.
- Use a manual approval step before email delivery.
- Add logging for every decision.
- Add a dead-letter or exception queue.
- Keep test data separate from real data.
