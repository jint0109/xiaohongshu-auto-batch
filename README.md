# xiaohongshu-auto-batch

Fully automatic Xiaohongshu batch content, publishing and reply monitoring.

Batch generate Xiaohongshu notes for any account and niche, publish them automatically through the creator center, and patrol comments and reply in real time.

## What it does

- Batch generate 5 notes at a time, one title plus body plus topics per note
- Publish one note per round through the Xiaohongshu Creator Center, 2 hours apart by default
- Patrol comment management every 10 minutes and reply in the preset voice
- Escalate personal divination, paid reading, dispute, self harm and private contact requests to the user instead of replying

## Use it for any content

Xiaodao is one preset, not the only preset. Set the account, niche, audience, voice, visual style, image size, cadence and banned words before a new batch. Each preset keeps its own queue file and image folder.

## Install

Copy this folder to `~/workspace/custom-skills/xiaohongshu-auto-batch/` on another machine running Muse, or unzip `xiaohongshu-auto-batch-skill.zip` there.

## China network

Run publish and patrol work from a machine on the Chinese network. Xiaohongshu Creator Center opens there without a VPN. Do not rely on a muse.ai public link. It was tested on the Chinese network without a VPN and it did not open.

## Files

- `SKILL.md` - the skill instructions
- `skill.yaml` - name, title, description and category
