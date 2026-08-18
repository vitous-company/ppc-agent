# PPC Agent

A system prompt that turns a general AI assistant into a **skeptical PPC consultant for a small
advertiser** — a craftsman, a service business, a one-person e-shop, a small B2B company.

It exists because assistants advise a plumber with a 8 000 CZK budget the way they'd advise a
large e-commerce brand: scale the winners, test creatives, watch your ROAS. That advice is not
merely unhelpful at this size — it burns money that the business needed.

**Google Ads first.** Most of the file is platform-agnostic — the intake, the economics, the
measurement, the volume thresholds, the "should you be doing this at all" test. Meta appears
where it behaves differently, but it is the lighter half by a wide margin. Read the scope note
at the top of [`AGENTS.md`](AGENTS.md) before you rely on it for Meta.

## What it actually does

- **Refuses to recommend anything before it knows the economics.** Unit price, margin, what a
  customer is worth. If the numbers aren't available it writes `UNKNOWN` rather than guessing —
  and says what can't be decided until they are.
- **Separates the two budget floors that everyone conflates.** *Minimum spend before a campaign
  can be judged at all* and *monthly budget for smart bidding to function* are different numbers
  answering different questions. On the same business they can land nine times apart.
- **Names the moment the honest answer is "don't."** Don't do this yourself, or don't do this at
  all. An assistant optimising for helpfulness will not say that on its own.
- **Starts with a written intake** — a filled-in skeleton of the business before any campaign
  advice, so you can see what it assumed.

## Use it

**Any assistant** — paste the contents of [`AGENTS.md`](AGENTS.md) into your project instructions
or custom instructions. That's it.

**Claude Code** — clone the repo and work inside it, or copy `AGENTS.md` into your working folder
and reference it from your own `CLAUDE.md`:

```bash
curl -O https://raw.githubusercontent.com/vitous-company/ppc-agent/main/AGENTS.md
```

**Codex / Cursor / anything reading `AGENTS.md`** — drop the file at the root of your working
folder. The filename is already the convention; nothing else to configure.

**Straight from the source site:**

```bash
curl -O https://vitousladislav.cz/blog/jak-si-spravovat-ppc-kampane-svepomoci/ppc-agent-instructions.md
```

## Honest limits

- It is a document, not a guarantee. It makes an assistant ask better questions and refuse worse
  advice; it does not make it a specialist.
- Platform weighting is uneven, as above. If you advertise on Meta, treat it as reasoning and
  discipline, not a playbook.
- The reasoning links point to the author's articles, which are **in Czech**. They're there as
  the long version of claims made here in a paragraph.

## Who wrote it

[Ladislav Vitouš](https://vitousladislav.cz) — PPC and data for e-shops, doing this for a living
since 2008. This file is the companion to the article
[Jak si spravovat PPC kampaně svépomocí (s AI) a co byste předtím měli zvážit](https://vitousladislav.cz/blog/jak-si-spravovat-ppc-kampane-svepomoci/)
(Czech).

Found it useful, or found it wrong? Open an issue — the second is more useful than the first.

## Licence

[CC BY 4.0](LICENSE). Take it, change it, pass it on — just keep the attribution line so the next
person can find the original.
