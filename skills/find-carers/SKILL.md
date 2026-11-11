---
name: find-carers
description: Find an independent care business in Australia on VidaKind's Find Carers list and compare options. Use when someone wants companionship, home care, help at home, lifestyle support or NDIS supports for themselves or a family member and names (or can name) a suburb or town, or asks what a VidaKind business offers.
---

# Find care businesses on VidaKind

VidaKind is software that independent care businesses in Australia use to run their services, with a free public Find Carers list. This skill uses the VidaKind connector's `find_carers` and `get_business_details` tools.

## 1. Get what you need, briefly

Before searching, make sure you know:

- **Where:** the suburb or town where the care happens. Add the state if the person mentioned it or the suburb name is common in several states.
- **What help** (optional): for example companionship, shopping and outings, meal preparation, help around the house.
- **How it's paid** (optional): NDIS participant, or paying privately. Only ask if it isn't clear and it matters to them.

Ask only for what is missing, in one short question. Don't ask about diagnoses, medications or health conditions; they aren't needed to find a business.

## 2. Search

Call `find_carers` with `suburb`, and `state`, `service` and `funding` when known. Use `funding: "ndis"` only when the person is an NDIS participant.

## 3. Show the options plainly

For each business, give in a few lines:

- its name and the area it covers, with the distance when the result has one;
- the services it lists, and whether it is NDIS-friendly;
- the checks it has recorded (ABN, worker screening, insurance), described as "recorded with VidaKind", not as verified;
- a link to its page.

Label a business marked `featured` as **Featured**: it pays for a top spot and it is not a recommendation. Keep VidaKind's order otherwise, and don't rank businesses on your own opinion.

If `results` is empty, say plainly that no business on VidaKind covers that area yet. Don't offer businesses from other areas as if they cover it. You can suggest trying a nearby larger suburb or town if the person wants to.

## 4. Details and prices

When the person picks a business, or asks about prices, call `get_business_details` with its `business_id`. Show:

- the visit options from `prices` (weekday, Saturday, Sunday and public holiday prices in AUD, and the minimum hours), as the business's published guide;
- the NDIS note, if there is one;
- the services its enquiry form accepts (`services_for_enquiry`).

Say that only the business can confirm the final price and availability. If `prices` is null, say the business hasn't published prices and the person can ask in an enquiry. Never estimate or invent a price, a time or availability.

## 5. Next step

Offer to send an enquiry to the business they choose (the `send-care-enquiry` skill). Don't send anything in this skill.
