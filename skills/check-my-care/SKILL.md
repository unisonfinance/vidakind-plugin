---
name: check-my-care
description: Check where someone's VidaKind enquiries are up to and which visits a care business has linked to their account. Use when they ask "did they get back to me", "what's happening with my enquiry", "when is the next visit", or about visits with a care business that uses VidaKind.
---

# Check enquiries and visits on VidaKind

This skill uses the connector's `check_my_enquiries` and `list_my_visits` tools. Both only read the connected person's own records and change nothing.

## Enquiries

Call `check_my_enquiries`. For each enquiry give the business, when it was sent, and what its status means:

| Status | Say |
| --- | --- |
| `new` | Sent; waiting for the business to get in touch. |
| `contacted` | The business has been in touch. |
| `awaiting` | The business has offered a visit and is waiting for the person to confirm or pay. |
| `converted` | The business has booked a visit; the time and price are the ones the business confirmed with them. |
| `closed` | The business has closed the enquiry. |

Only enquiries sent through an AI assistant appear here. If the list is empty, say so, and mention that enquiries sent on a business's website or in the VidaKind app show in that app instead.

If an enquiry has been `new` for a while, suggest the person contacts the business directly; don't promise when it will reply.

## Visits

Call `list_my_visits`. Give the business's Company ID in `company` if the person knows it (it's in the business's emails and app); otherwise leave it out and the tool checks the businesses they enquired with.

List the visits with date, start time, hours, status and the carer's name when present, newest first. These are the visits the business has linked to the person's account, as the client or as invited family. For any change of time, or to cancel, the person contacts the business: this skill can't change visits.

If no visits come back, explain that a business links visits when it adds the person as a client or invites them as family, and suggest asking the business.
