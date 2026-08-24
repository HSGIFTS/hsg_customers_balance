# HSG Customer Balance

Reusable customer balance experience. First relationship: Office ↔ Denis.

## V1 rules
- Send = customer owes Office = red = negative balance effect when Done.
- Withdraw = Office owes customer = green = positive balance effect when Done.
- Pending is default and does not affect balance.
- Done affects balance.
- Full CRUD and Pending ↔ Done lifecycle.
- Balance, pending totals, projections, and running balances are readings calculated from transaction facts.

## Architecture
- Supabase Auth owns login credentials.
- `hgs_customers` owns people, relationships, memberships, transactions, and status history.
- Channels reuse shared HSG channel identities.
- RLS limits data to active relationship members.

## Deployment
Static PWA suitable for Netlify import. Development can continue in GitHub without requiring every commit to become a Netlify production release.