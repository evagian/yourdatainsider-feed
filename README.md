# yourdatainsider.ai public news feed

`feed.json` lists the news items our models take into account from the **last 24 hours (at most 50 items)**, **delayed 15 minutes**. It is rebuilt every 5 minutes and
published only when the items change; the repository always holds a single commit (no history). Fetch it from
`https://raw.githubusercontent.com/evagian/yourdatainsider-feed/main/feed.json` (GitHub caches it for about 5 minutes).

**Information only, not investment advice.**

## Schema

Top level: `generated_at` (UTC, when the items last changed), `delay_minutes` (15), `count`, `items` (newest first, last 24 hours, at most
50), `disclaimer`.

Per item:
- `id`: stable 16-hex id
- `seen_at`: UTC time we first saw the item
- `source`: display name (e.g. `CoinDesk`, `Wu Blockchain`, `X @handle`)
- `kind`: `news`, `telegram` or `x`
- `link`: the original item
- `title`: headline only (news and telegram; at most 200 characters, plain text)
- `x` (X items only): `post_id`, `author_id`, `embed_url`. X items carry no text; show them with X's official embed.

Headlines and posts belong to their publishers; follow the link for the full item. Written automatically by our news box.
