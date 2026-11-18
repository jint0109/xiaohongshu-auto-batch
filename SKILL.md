# Fully Automatic Xiaohongshu Batch Content, Publishing and Reply Monitoring

## Run only in fully automatic mode when the user enabled it

- Run this skill only after the user said to run it fully automatically for one named Xiaohongshu account and one named batch direction.

- Treat that enablement as approval for the queue direction and the batch theme, not as approval to change the account, the nickname, the bio, the avatar or the homepage.

- Stop at once if the user pauses the schedule or says to stop, and do not restart until the user says to restart in plain words.

- Keep the default publishing rule outside this skill, and publish only the exact version the user saw, when fully automatic mode is off.

## Use it for any content, not only one niche

- Ask for the account, the niche, the audience, the voice, the visual style, the image size, the post cadence and the banned words before you start a new batch, when the user did not name them.

- Treat Xiaodao as one preset, not as the only preset, and use the same pipeline for any other preset the user names.

- Keep each preset in its own queue file and its own image folder, and never mix notes, images or reply rules from two presets.

- Copy the niche rules into the batch before you generate, and generate only inside the niche the user named for that run.

- Change only the preset fields when the user switches niche, and keep the publish check, the account check and the reply check unchanged.

## Confirm the account before any publish

- Confirm the logged in account matches the account the user named for this run before every publish round, and record its nickname and its Xiaohongshu number in the log.

- Stop at once if the session shows a different account, and publish nothing to the wrong account.

- Open the creator center first when you need to check the session, and treat the main site and the creator center as separate sessions.

- Wait about one minute and retry once inside the publishing surface if the login page appears, and ask the user for a text code only after the publishing surface itself shows a login prompt.

- Never send a login QR code through chat, and have the user scan it directly from the live browser view while you keep the session open.

## Batch generate the queue

- Generate five notes at a time in the direction the user named for this preset.

- Write each note as one title plus body text plus topics, and keep the body in plain spoken words with no preaching tone.

- Use the Xiaodao preset as the worked example, which is Daoist wisdom plus emotional healing for modern young people, with shared pain points for young and old people and with love and breakup examples.

- Put one ancient gua example on card two in the Xiaodao preset, in the style of the plum blossom observation story, and add one sentence about that example in the body text.

- Tell only the old story and its道理 in that preset, and give no divination to the reader, no result prediction, no consultation entry and no paid offer.

- For any other preset, replace the card two example with the example type that preset uses, and keep the same rule of story only with no divination and no paid offer unless the user names a different rule in plain words.

- Write the next batch before the queue runs out, and start a refill when only two unpublished notes remain in the queue.

- Record every note in the queue file with its number, title, source draft, image prefix and status, and update that status right after each publish.

## Make the images

- Make eight images per note at 1080 by 1440 in 3 to 4 ratio, with one cover plus seven inner cards, unless the preset names a different size or count.

- Use one single cover image with no split in the Xiaodao preset, with large brush calligraphy text and the blue robed round faced little Daoist figure, and keep that figure consistent across the batch.

- Use the visual style the preset names for any other preset, and keep the main figure or motif consistent across that batch in the same way.

- Generate the picture with the image model and add the words with PIL afterwards, and never let the model write the words directly.

- Break lines at commas, check every image for wrong characters and cropping, and rebuild any card that fails the check before publishing.

- Count the attached images against the approved set in the publish form, and publish only when the count matches and every card is present.

## Check compliance before publishing

- Check every title, body, image and topic against the banned list for this preset before publishing, and drop any note that contains a banned phrase.

- Never use the banned Xiaodao phrases in the Xiaodao preset, in text, images or topics, and never use the banned phrases the user named for any other preset.

- Never promise a result, never say a fixed fate, never give medical advice, never give a pregnancy or health diagnosis, and never sell xuanshu or fortune telling goods.

- Do not tick the AI declaration box, and do not attach an unrelated activity or topic that the publish form added by mistake.

- Keep the old 100 item dark language list as reference only, and follow the live platform rulings above it when the two disagree.

## Publish automatically through the creator center

- Publish one note per round, always the earliest unpublished note in the queue, and space rounds two hours apart unless the preset names a different cadence.

- Carry the exact title, body, topics and image files into the browser task, and have the browser publish only that version.

- Read the note back after publishing, record its note id, its public link, its publish time and its review state, and treat an accepted upload as unpublished until that read back confirms it.

- Never retry a publish blindly, and look up the note first when a result is uncertain, because the first attempt may already have gone out.

- Report a draft, a scheduled note and a live note as different states, and never call a blocked upload a successful publish.

## Monitor comments in real time and reply

- Patrol the creator center comment management every ten minutes while the schedule runs, and check every note published in the last 48 hours for new comments.

- Record each new comment with its note id, commenter, time and text, and mark it as replied or escalated after you handle it.

- Reply from the creator center comment management only, and read the reply back after posting to check that it sits nested under the right comment.

- Reply in the voice of the preset, acknowledge the feeling, share one plain idea from that preset, and invite the reader to share their own feeling in their own words.

- Give no divination to the commenter, no result prediction, no medical advice, no contact information and no paid offer in any reply.

- Escalate to the user and reply nothing when a comment asks for a personal divination, asks for a paid reading, reports a dispute, mentions self harm or asks for private contact, and record the escalation with its link.

- Batch replies into one browser session when several comments wait, and do not open the site once per reply.

## Deploy it where the Chinese network can reach it

- Treat this skill as a portable folder, and copy the whole folder with its SKILL.md and skill.yaml when you move it to another machine or another Muse.

- Run the publish and patrol work from a machine on the Chinese network, because Xiaohongshu itself is a domestic platform and its creator center opens there without a VPN.

- Do not rely on a muse.ai public link for the deployment, because the user tested that link on the Chinese network without a VPN and it did not open, and do not claim that link works without a VPN.

- Do not use Cloudflare free hosting as the China route, because it has no node in China and it runs slow there.

- Use a domestic host when a public link must open in China, such as Gitee Pages or an Alibaba Cloud OSS static host or a Tencent Cloud static host, and ask the user for the account that host needs before you start that deployment.

- Use a local file or a WeChat file transfer when the user only needs to use it on their own phone or computer, because that route needs no VPN and no public link.

- Keep the browser login, the queue file and the image scripts on the machine that runs the schedule, and do not assume a login saved on one machine works on another machine.

## Log every run and stop cleanly

- Write one log line per publish round and per patrol round with the time, the note id or comment id, the action taken and the result.

- Report the publish result to the user after each round with the title, the note id, the link when available and the review state.

- Report new comments and replies in the same message when a patrol finds them, and report nothing when a patrol finds no new comment.

- Keep the queue, the log and the image scripts under the workspace for that preset, and do not change the homepage, the nickname, the bio or the avatar as part of this skill.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Websites

- Xiaohongshu Creator Center for publishing notes and managing comments, and carry the exact approved topics, text and media into the task and confirm the note public state after publishing.
