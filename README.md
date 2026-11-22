# AGIAgent

**A generalist student distilled on-policy from vertical teachers.**

Vertical agents sample, fail and repair inside their own domains. AGIAgent learns from all of
them on its own trajectory (multi-teacher on-policy distillation, MOPD), so generalization is
trained rather than hoped for.

## Teachers

SearchAgent · RecAgent · AdAgent · SupportAgent · CodingAgent · DataAgent · TradingAgent ·
MedAgent · VideoAgent · EmbodiedAgent

## Mechanism

| Piece | Role |
|---|---|
| Shared backbone | holds common competence instead of ten disconnected specialists |
| Domain adapters | keep specialty without duplicating the whole model |
| On-policy sampling | the student acts first; teachers supervise what actually happened |
| MOPD | weighted multi-teacher distillation over the student's own tokens |
| Routing | at inference a request is routed to the adapter set that matches the task |
| Anti-forgetting | replay buffers and per-domain regression tests |
| Budget | teacher calls are the expensive part; each round has a token ceiling |

## Evaluation

- transfer to held-out domains with no teacher;
- per-domain regression against fixed eval slices;
- cost per solved task, with a ceiling that aborts a round.

## Status

This repository currently holds the design and its public project page. No benchmark numbers are
claimed yet.

Project page: <https://0x0addc001.github.io/AGIAgent/>
