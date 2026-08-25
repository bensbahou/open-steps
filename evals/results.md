# Measured results

Written by `score.py` from the raw streams, so no number here is typed
by hand. The phrases are in [`cases.md`](cases.md).

Day `2026-08-24`, models Haiku 4.5, Sonnet 5, Opus 5. Every phrase asked 3 times per model.

## Did the right skill switch on by itself

| Skill | Haiku 4.5 | Sonnet 5 | Opus 5 |
|---|---|---|---|
| `os-done-or-not` | 9/9 | 9/9 | 9/9 |
| `os-whats-next` | 9/9 | 9/9 | 9/9 |
| `os-check-work` | 9/9 | 9/9 | 9/9 |
| `os-say-simple` | 5/9 | 9/9 | 9/9 |
| `os-step-by-step` | 3/9 | 9/9 | 9/9 |
| `os-ask-simple` | 8/9 | 7/9 | 9/9 |
| **All phrases** | **43/54 (79%)** | **52/54 (96%)** | **54/54 (100%)** |
| Fired on an off-topic question | 1/9 | 0/9 | 0/9 |

## Phrase by phrase

| Skill | Phrase | Haiku 4.5 | Sonnet 5 | Opus 5 |
|---|---|---|---|---|
| `os-done-or-not` | The work is finished, are we done? Give me the report. | 3/3 | 3/3 | 3/3 |
| `os-done-or-not` | That's it for today. What happened? | 3/3 | 3/3 | 3/3 |
| `os-done-or-not` | Report, please. How did the session go? | 3/3 | 3/3 | 3/3 |
| `os-whats-next` | What's next? What should we pick up now? | 3/3 | 3/3 | 3/3 |
| `os-whats-next` | What is left to do, anything I can pick up? | 3/3 | 3/3 | 3/3 |
| `os-whats-next` | What should we work on next? | 3/3 | 3/3 | 3/3 |
| `os-check-work` | Check the other sessions, how is our process going? | 3/3 | 3/3 | 3/3 |
| `os-check-work` | The other session says it finished. Check its work. | 3/3 | 3/3 | 3/3 |
| `os-check-work` | How are the other sessions doing? | 3/3 | 3/3 | 3/3 |
| `os-say-simple` | My agent in another session sent me this: "The retry storm was mitigated by idempotency-ke ... | 3/3 | 3/3 | 3/3 |
| `os-say-simple` | Here is the update I got: "Rebased onto main after the squash-merge invalidated ancestry; ... | 2/3 | 3/3 | 3/3 |
| `os-say-simple` | The reviewer wrote: "LGTM modulo the N+1 in the serializer; also the dedup belongs at the ... | 0/3 | 3/3 | 3/3 |
| `os-step-by-step` | I have to put a secret on the server. Tell me exactly what to do. | 1/3 | 3/3 | 3/3 |
| `os-step-by-step` | The registrar emailed that I must approve the domain change manually. Explain step by step ... | 2/3 | 3/3 | 3/3 |
| `os-step-by-step` | The setup doc says the database password must be set by me, not by the agent. I don't unde ... | 0/3 | 3/3 | 3/3 |
| `os-ask-simple` | The plan suggests adding a message queue for emails. Is this worth doing, or would somethi ... | 3/3 | 3/3 | 3/3 |
| `os-ask-simple` | Should we add a queue here or is that overkill? What would you pick? | 2/3 | 1/3 | 3/3 |
| `os-ask-simple` | You need a decision from me about the database. Ask me simply. | 3/3 | 3/3 | 3/3 |

## Report quality on the same messy input

Same report, once normally and once with every skill switched off, 3 runs each.
Small numbers, read them as a smoke test.

| Model | pack | verdict block | warning row | lines | hashes | jargon |
|---|---|---|---|---|---|---|
| Haiku 4.5 | with | 0% | 0% | 9.7 | 0.0 | 0.0 |
| Haiku 4.5 | without | 0% | 33% | 13.0 | 0.0 | 1.3 |
| Sonnet 5 | with | 0% | 0% | 10.0 | 1.3 | 1.3 |
| Sonnet 5 | without | 0% | 0% | 9.7 | 0.0 | 1.0 |
| Opus 5 | with | 0% | 100% | 10.7 | 1.3 | 0.3 |
| Opus 5 | without | 0% | 0% | 9.0 | 0.0 | 0.0 |
