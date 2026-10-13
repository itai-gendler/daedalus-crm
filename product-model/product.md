---
{
  "id": "daedalus-crm",
  "summary": "Customer and sales work with human-confirmed AI writes, native maintenance and synchronization, and hosted service operations.",
  "category": "crm",
  "tags": [
    "crm",
    "sales"
  ],
  "authors": [
    {
      "name": "BeckY824",
      "url": "https://github.com/BeckY824"
    }
  ],
  "license": "AGPL-3.0-only",
  "languages": [
    "zh-CN",
    "en"
  ],
  "limitations": [
    "AI proposals require explicit human acceptance before CRM writes.",
    "AI runs only when a person asks; loading a page never calls the model.",
    "Imports recognize an existing customer by phone number and only skip it or fill its empty fields, never overwrite it.",
    "Referral attribution is fixed when a customer is entered; later upstream changes do not rewrite it.",
    "Subscription payment references are recorded for operations staff to activate; no payment is collected automatically."
  ]
}
---

# Daedalus CRM

Daedalus CRM keeps customer, lead, opportunity, communication, arrangement and financial work, including lightweight trade orders. Chinese web and native surfaces support CRM work. Native books add account-owned data, maintenance, reminders and team synchronization. Hosted services provide subscriptions and operations. Demo-request email supports Chinese and English.

## Intent

Keep sales work reviewable, including AI changes pending explicit human confirmation.
