# Instagram scheduled content verification

- Apply this correction alongside the base Instagram connector doc when a task schedules, checks, edits, or cancels Instagram content.

## Verify scheduled content before reporting it

- Treat a successful scheduling result from `instagram-cli` as unconfirmed until the item appears in the Instagram app or web scheduled list.

- Check the scheduled date and time and the media and the caption text for each item in that list before reporting the item as scheduled.

- Report an item as unverified when it does not appear in the scheduled list even when the connector returned success.

- Do not use a published post count or a `posts` result to confirm a scheduled item because scheduled items do not appear there until they publish.

- Correct caption text in scheduled content before its publish time when the caption in the list differs from the approved text, and recheck the list after the correction.

## Use the Instagram app for scheduled content

- Open the profile menu in the Instagram app and choose Professional Dashboard and then Scheduled Content to list scheduled items.

- Tap a scheduled item and choose Delete from its menu to cancel it because `instagram-cli` offers no cancel operation.

- Use the app path above to cancel a scheduled item when the web edit screen fails to open.

- Check for a second item at the same scheduled time before cancelling one because two items can share one scheduled time.

- Cancel only the exact item the user approved for cancellation and keep any other item at the same time.

## Do not book through a different account view

- Stop booking when an account view shows a different account from the requested destination and do not book into that account.

- Verify the active account inside Instagram itself before booking and switch to the requested account first when it differs.

- Do not use a Business Suite portfolio view as proof of the active Instagram account when it shows only a different account.

## Recover from a scheduling error

- Check the scheduled list and published posts before retrying a scheduling call that returned an HTTP 500 because the first attempt may have created the item.

- Do not schedule a replacement while the original item is still scheduled.

- Switch to immediate publication only when the user explicitly approves immediate publication for that item at that time.

## Re-verify scheduled items until they publish

- Check the scheduled list again for an item scheduled days ahead because an item that appeared there can later disappear without publishing.

- Check the scheduled list and the published grid after the scheduled time passes before reporting the item as published.

- Report an item as not published when it is absent from both the scheduled list and the published grid after its scheduled time.

- Do not treat a vanished item as delayed or as still scheduled, and do not schedule a replacement until the user approves the replacement.

## Related skills

- [Social Publishing](/opt/muse/skills/social-publishing/SKILL.md)

- Use `muse.skill_search` to find other skills and `muse.connector_search` to find other connectors.
