# Publish Authorization Is Separate From Content Choice

## Treat a content choice as a draft choice only

- Treat a choice between caption options, media options, or draft versions as a choice about content only, and never as permission to publish or schedule that content.

- Ask for publish permission in a separate explicit step after the content choice, and name the account, the destination, and whether the action is publish now or schedule.

- Wait for an explicit publish instruction before you call any publish or schedule command, and treat silence, a delayed reply, or an unanswered question about proceeding as no permission.

- Show the exact final text and media again at the publish step when the content changed after the earlier choice, and get fresh permission for that exact version.

## Stop and confirm when permission is unclear

- Stop before publishing when the user chose content but did not say to publish, when the user asked a question instead of giving permission, or when the instruction could mean either draft approval or publish approval.

- Ask one short question that names the action you are about to take, and publish only after the user answers that question with an explicit yes.

- Report a saved draft, a scheduled post, and a live post as different states, and never report a draft choice as a publication.

## Available connectors

- [Instagram](/opt/hatch/connectors/instagram/CONNECTOR.md) for feed posts, reels, carousels and stories, published now or scheduled.

- [Threads](/opt/hatch/connectors/threads/CONNECTOR.md) for text and media posts, carousels and replies.

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- Offer a draft preview and a separate publish confirmation as two distinct steps when a post is costly to undo.

- Keep the publish question short and action specific, so the user can answer it without rechecking the whole draft.
