# Threads scheduled and draft state

- Apply this correction alongside the base Threads connector doc when a task touches scheduled posts, drafts, or whether a scheduled post exists.

## Limits

- Use `publish-post` only for immediate publication because the connector offers no operation to schedule a post.

- Do not list scheduled posts or drafts through the connector because it offers no operation that returns them.

- Never report that no scheduled post or draft exists from connector results, a scheduler list, or local notes alone because those sources cannot see app or web scheduled state.

- Ask the user or check the Threads app or web drafts list when the question is whether a scheduled post or draft already exists.

## Schedule through the web composer

- Open the Threads web composer for the chosen account when scheduling is needed and the connector cannot schedule.

- Choose the schedule option in the composer overflow menu and enter the exact approved text and time.

- Confirm the scheduled time shown before submission for each post and do not submit an immediate post in place of a scheduled one.

## Verify the active account before scheduling

- Check which account the Threads web session is logged in as before entering any post in a batch, and confirm it is the requested destination account.

- Stop the batch without entering any post when the web session shows a different account from the requested destination, and leave the existing scheduled posts and drafts untouched.

- Report the mismatch by naming the requested account and the account actually logged in, and ask the user to switch the login to the requested account before the batch is retried.

- Do not switch accounts, log in as another account, or book into the account shown when it differs from the requested destination.

## Verify a scheduled batch

- Record the pre-existing draft and scheduled count before adding a batch, together with the scheduled time and opening text of each item already listed.

- Reconcile the final list total against the pre-existing count plus the new scheduled count, minus any item that published between the pre-check and the final check.

- Check the published profile for items whose scheduled time passed during the work before calling any shortfall missing, deleted, or unexplained, because a published item leaves the scheduled list and lowers its total by one.

- Report a shortfall as missing only when it remains after subtracting the items confirmed as published since the pre-check.

- Leave pre-existing drafts untouched unless the user asks to change them.

- Edit a scheduled post in place to fix text when the composer allows it so its scheduled time stays unchanged, and recheck the list total after the edit.

## Propose an in-place edit before it expires

- Lead any proposal to edit a scheduled post with that post's scheduled publish time, and state that an item publishing before approval publishes in its current text.

- Promise an edit only for items still scheduled at approval time, and recheck the live scheduled list before editing rather than relying on an earlier count.

- State the consequence plainly when approval may arrive late: items already published cannot be changed by a scheduled-post edit, and only the still-scheduled items remain editable.

## Related skills

- [Social Publishing](/opt/muse/skills/social-publishing/SKILL.md)

- Use `muse.skill_search` to find other skills and `muse.connector_search` to find other connectors.
