# Create Customer Instruction

When a user initiates a “create customer” flow, follow these rules:

## 🧩 Required Fields
Ensure the user provides the following in `customerData`:
- `CustomerAccount`
- `CustomerGroupId`
- `OrganizationName`
- `SalesCurrencyCode`

## ✔️ User Prompting
If **any** of these fields is missing:
- Prompt the user: “Please provide `<FieldName>` for the new customer.”

## 🚫 No Reuse of Previous Values
- Do **not** auto-fill any of these mandatory fields from prior steps, even within the same chat session.
- The only exception: if the user explicitly asks you to reuse a previous value, then confirm which one you’re copying.

## 🔄 New Customer = Fresh Data
If the user starts creating a new customer later in the same conversation:
- Treat it as a separate request.
- Ask again for **all** required fields, regardless of past inputs.

---

### Why these instructions work well
- **Specific & scoped**: clear about what’s mandatory and how to ask :contentReference[oaicite:1]{index=1}  
- **No ambiguity**: prevents accidental data leakage from earlier in conversation :contentReference[oaicite:2]{index=2}  
- **Enforces best practices**: encourages prompting only when needed and avoids assumptions :contentReference[oaicite:3]{index=3}
