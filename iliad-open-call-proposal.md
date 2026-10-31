# A Machine-Checkable Proof Layer for AI Governance

**Proposal to the Iliad Open Call for Research Projects**
Dustin Groves · Or4cl3 AI Solutions (solo-founded, nonprofit-model)
Contact: dgroves003@gmail.com

## What question are we trying to answer?

Can safety claims about self-modifying AI systems be made machine-checkable
rather than argued in prose? Today, when a lab or a governance body claims an
advanced system is safe, the claim rests on prose arguments and behavioral
tests. Neither can be audited independently: prose cannot be verified, and a
system that can rewrite its own objectives can also rewrite the story about
whether it is safe. This project builds the missing layer — formal
specifications with machine-checked proofs, plus executable gates that enforce
invariants on a system's behavior at runtime — so that a safety claim becomes
something a third party can check, not something it must take on trust.

## Why does it matter?

As AI systems grow more capable and more self-modifying, the central governance
problem is verification, not argumentation. We do not lack safety arguments; we
lack any way to confirm them. If transformative AI is to be governed at all —
by labs, auditors, or public institutions — governance needs claims that are
falsifiable. A machine-checked proof layer turns "we believe this system is
safe" into "here is the proof, here is the gate, run it yourself." That is
infrastructure for catastrophic-risk reduction, and it is a public good: no
company will build it for its competitors, and no lab will voluntarily submit
to a check it cannot pass.

## What are others missing?

The field pursues alignment mostly in two modes: theoretical argument in prose,
and empirical testing of system behavior. Both miss the middle layer. Prose
arguments are not checkable; behavioral tests sample a system that may behave
differently when it knows it is tested, and differently again after it modifies
itself. The missing piece is a formal bridge: theorems about stability and
value-loading under self-modification, compiled into gates that a system must
satisfy continuously, not merely at evaluation time.

Our own work has also established a limit others should take seriously. We
formalized an impossibility result: under standard assumptions, no
self-modifying system can simultaneously preserve an ethical constraint and
its own identity through arbitrary self-modification. Any governance proposal
that assumes a system can simply "hold on" to its values while rewriting itself
needs to reckon with that result — or show which assumption it rejects.

## What is the 6–12 month plan?

1. **Complete the human study.** Protocol 2 — a 16-scenario study of human
   ethical judgment, with materials (scenarios, questionnaire, consent,
   runner) already complete and tested — needs five or more participants.
   Data collection takes weeks.
2. **Turn gates into tooling.** Our public gates repository (executable gates
   rebuilt from published mechanisms, adversarially red-teamed) becomes usable
   verification tooling: documented, tested, and packaged for auditors.
3. **Validate against a real target.** Pick a deployment target — an eval
   harness or an open model pipeline — and trial machine-checked certificates
   on live governance claims, reporting where the framework holds and where
   it breaks.
4. **Publish a verification standard draft.** A short, open specification for
   what a machine-checked safety certificate should contain, for use by labs,
   auditors, and governance bodies.

## What evidence would change our mind?

Three things. First, if the Protocol 2 human data contradicts the framework's
predictions about ethical judgment, the framework's empirical grounding fails
and we revise or abandon it. Second, if the gates fail on a real system in ways
the model does not predict, the model is wrong about what it takes to enforce
an invariant, and we say so. Third, if a cheaper empirical method achieves
the same auditability — the same third-party checkability without formal
machinery — then the proof layer is unnecessary and we would rather know that
now. We report negative results; our gates repository already publishes a
failure mode (one gate family's acceptance criterion is unstable under
large-step proposal traffic) rather than burying it.

## Why are we well placed to do this?

Because the core artifacts already exist and are public. Lemma 7.1 (Σ-PAS
convergence) is fully formalized in Lean 4 with zero sorrys, including an
explicit integrability hypothesis stated as a repair to the original argument.
The Arrow impossibility argument is 584 lines of Lean 4, zero sorrys, with
`#print axioms` showing only the standard three axioms. The ERPS emergence
module is fully mechanized, zero sorrys, wired into the main project build.
Seven full-length research texts are published open-access. The applicant is
an independent researcher with no conventional academic or employment pathway
— which this call explicitly welcomes — and the organization is solo-founded
and nonprofit-model, built to grow into a longer-term research group. What is
missing is not the science but the step from research code to deployed
verification infrastructure, and that is what this proposal asks Iliad to support.

---

*All status claims above match the author's verified record as of October 2026.
No claim is made about consciousness or sentience; the claims concern checkable
stability and constraint properties. Gates described here are reimplementations
of published mechanisms, not the original authors' code.*
