# Who shops for what — short design

**Why:** Colleen and Dave split up in the store. They want to decide ahead of
time who grabs each item, then each see just their part while shopping.

## Approaches
- **A. Two sections per store** (Colleen / Dave). Clear, but doubles card height
  and moving an item = delete + re-add. Not picked.
- **B. One list per store, each item tagged (picked).** Tap the tag to cycle it;
  a filter at the top shows only your items. Existing data keeps working.

## Design
- Each item gets a `who` field: `colleen`, `dave`, or `both` ("we look together").
- Tag button on each row shows **C / D / Both**; tap cycles C → D → Both → C.
- Filter at the top: **Everything / Mine / Dave's** (labels flip for Dave).
  "Mine" = my items + Both items. Choice is remembered on that phone only.
- Store header counts and "x of y picked up" follow the current filter.
- Unchanged: live sync, photos, checkboxes, adding stores, sign-in.

## My calls (correct me)
- Items with no tag yet (everything on the list today) count as **Both**, so
  nothing disappears from anyone's view.
- New items default to **Both**; you tap once to give it to one person.
- "Mine" is worked out from the signed-in Google account, no setup needed.
- While in there: fix the quoting bug so a `"` or `\` in a name can't break the page.

## Non-goals
- No separate lists/stores per person, no notifications, no change to the
  Firebase security rule.
