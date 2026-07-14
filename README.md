# When Local Monitors Miss Compositional Harm
### Diagnosing Distributed Backdoors in Multi-Agent Systems

Yibo Hu, Ren Wang · Illinois Institute of Technology

📄 Paper: [arXiv:2607.11751](https://arxiv.org/abs/2607.11751)

## What this paper is about

A distributed backdoor splits a harmful payload across the agents of a multi-agent
LLM system, so that every local (per-step) check looks benign while the *assembled*
trajectory is the attack. We frame runtime detection as an **observability boundary**:
a local monitor can catch only what its view can still tell apart from benign traffic.
We prove that once fragments are locally indistinguishable from benign traffic, no local
detector on that view can separate them — however strong it is — and detection returns
only when the monitor observes the *assembled* object.

## Key findings

- **It is lost evidence, not splitting, that blinds a local monitor.** Along a controlled
  locality sweep, taint and per-step detectors fall to chance as per-fragment evidence is
  removed, while a composition view stays strong.
- **The attack reappears once the fragments are assembled.** A marker-free monitor trained
  only on benign traffic recovers the assembled code structure across held-out encoding
  families (**mean AUROC 0.874**); a marker-grep baseline collapses to chance (**0.500**),
  and a supervised monitor reaches **1.000**.
- **Seeing more is not enough — the representation must be right.** A codec-blind monitor
  never fires on the fully locally-benign attack (**detection 0.000**); only reaching the
  decoded representation recovers it (**1.000**). Finding that representation is the open problem.

## Code and data

The reproduction package — the CPU-only core that regenerates the headline detector numbers,
the controlled testbed, the end-to-end ASR driver, and the result tables — **will be released
here upon publication. In the meantime, it is available from the authors on request.**
