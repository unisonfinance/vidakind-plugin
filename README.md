# VidaKind

![VidaKind](assets/icon.png)

Find a care business that visits your suburb in Australia, compare what it offers and charges, and send it an enquiry, by asking your AI assistant in plain words.

VidaKind is software that independent care businesses use to run their services (companionship, home care, lifestyle support and NDIS supports), with a free public [Find Carers](https://vidakind.com/find-carers/) list. Families pay VidaKind nothing.

This plugin has two parts:

- **The VidaKind connector.** It connects your assistant to your own VidaKind account at `https://vidakind.com/mcp`. You sign in on vidakind.com (Google or email; a free account is enough), tick the permission box and press **Allow and connect**.
- **Four skills.** They teach the assistant to do the common jobs properly:
  - **find-carers**: find businesses that visit a suburb, filter by type of help and NDIS or private, and show their services, recorded checks and published prices fairly.
  - **send-care-enquiry**: explain the terms, show exactly what will be sent, and send an enquiry to one business only after you say yes.
  - **check-my-care**: see where your enquiries are up to, and the visits a business has linked to your account.
  - **care-business-overview**: for people who run a care business on VidaKind, a read-only look at their own visits, clients and team.

## Use it

After installing, connect the VidaKind connector and sign in. Then ask things like:

- "Find companionship carers who visit Southport on the Gold Coast."
- "Which care businesses near Labrador take NDIS participants?"
- "What does GoldieCare charge for a 3-hour visit on a Saturday?"
- "Send GoldieCare an enquiry about Tuesday morning visits for my mum."
- "Where are my VidaKind enquiries up to?"

The assistant shows you the enquiry and asks before sending. An enquiry is a request, not a booking: only the business you choose can confirm times and prices.

## What it can't do

It can't book or confirm a visit, agree a price, take a payment or give medical advice. It never sees staff pay, internal notes or health records. For an emergency, call 000.

## Data

The plugin itself stores nothing and runs no code on your computer. Through the connector at vidakind.com, your assistant reads VidaKind's public Find Carers list and each business's published details and prices. When you agree to send an enquiry, it sends that business the details in the enquiry (your name, suburb, who the care is for, the services, your preferred days and times, optional phone and note) plus your VidaKind account email, exactly like an enquiry from the website; VidaKind keeps a record that the enquiry came from an assistant so you can check on it. It reads your own enquiries and linked visits when you ask. Nothing is sent anywhere else. Privacy policy: https://vidakind.com/privacy/

## Disconnect

Remove VidaKind in your assistant's connector settings. Access stops straight away.

## Help

Guide: https://vidakind.com/connect/. Questions: contact@vidakind.com. Terms: https://vidakind.com/terms/

## License

MIT
