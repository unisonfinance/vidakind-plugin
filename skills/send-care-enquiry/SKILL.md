---
name: send-care-enquiry
description: Send an enquiry to one VidaKind care business, the safe way. Use when someone wants to contact, enquire with, ask about availability from, or "book" a care business found on VidaKind. Explains the terms, shows exactly what will be sent, and sends only after the person agrees.
---

# Send an enquiry to a care business on VidaKind

An enquiry is a request, not a booking. It goes straight into the chosen business's VidaKind Bookings as a new request, and the business contacts the person to confirm suitability, times and price. This skill uses the connector's `how_vidakind_works`, `get_business_details` and `send_enquiry` tools.

If the person asks to "book" a time or "confirm" a price, explain that only the business can do that, and offer to send an enquiry instead.

## 1. Know the business and its services

You need the business's `business_id` (from `find_carers`). Call `get_business_details` if you haven't yet: the enquiry's services must be chosen from its `services_for_enquiry` list, using the exact wording, or "Not sure yet".

## 2. Collect the details

Ask only for what is missing:

- **Contact name** (who the business should get back to);
- **Suburb** where the care happens;
- **Who the care is for** ("Myself", "My mother", …);
- **Services** from the business's list;
- **Private or NDIS**;
- optional: preferred days, preferred time, hours per visit, a phone number, and a short practical note.

Replies go to the email of the person's connected VidaKind account; don't ask for an email address.

Keep health details out. Don't include diagnoses, medications, health records, or another person's private information. If the person offers them, say the business will ask what it needs, and leave them out of the enquiry.

## 3. Tell them the terms and show the enquiry

Call `how_vidakind_works` and tell the person the terms in plain words, in particular:

- VidaKind is software and a free list; it doesn't provide care or recommend businesses;
- this is a request, not a booking: nothing is booked and no time or price is agreed until the business confirms it;
- any agreement and payment is between them and the business; families pay VidaKind nothing;
- the business will contact them about this enquiry.

Then show the exact enquiry you will send (business, contact name, suburb, who it's for, services, private or NDIS, days, time, hours, phone, note) and ask: "Shall I send this to {business}?"

## 4. Send only after a clear yes

When the person agrees, call `send_enquiry` with the details, `customer_agreed_terms: true`, `consent_to_contact: true`, and a new unique `request_key` for this enquiry. If the call fails part-way, retry with the same `request_key` so it isn't sent twice.

Never set `customer_agreed_terms` or `consent_to_contact` without the person's yes, and never send to more than one business without asking for each one.

## 5. Report what happened

- **Sent:** say it went to the business as a new request, the business will contact them to confirm suitability, times and price, nothing is booked yet and no payment was taken, and a confirmation email is on its way. Give the reference.
- **`outside_service_area`:** say plainly that this business doesn't visit that address, and offer to look for another business with `find_carers`.
- **`unknown_service`:** pick from the `services_for_enquiry` it returns and confirm with the person before trying again.
- **Any other error:** explain it in plain words; nothing was sent.
