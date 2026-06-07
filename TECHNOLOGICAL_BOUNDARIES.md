# Technological Boundaries

This document defines the absolute limits on what the Infinites Research Organization will not develop. It is the standing answer to the **Technological Boundaries** item pending vote in the Constitution, and is intended as a working draft for the group to react to, amend, and ratify.

## Purpose

Nearly everything we build is dual-use. A tool that locates a hidden camera in your home is, mechanically, a tool that locates a camera in someone else's home. A model that fingerprints a device to detect a tracker is the same model that fingerprints a device to track its owner. The capability does not care which direction it is pointed.

Because our work is dual-use by nature, the line between defense and offense cannot live in good intentions or in a disclaimer. It has to be written down, applied to every project the same way, and enforced before a capability exists rather than apologized for after. This document is that line. It exists so that "we protect people, we do not surveil them" is a design constraint we can point to, not a value we merely hold.

## The Defensive-Only Principle

Every capability this organization develops must be **defensive and operator-bound**. Concretely, a tool must satisfy all four:

- **Passive by default.** It receives, observes, and analyzes. It does not transmit to deceive, jam, disrupt, or attack another system, except where active measurement is unavoidable, strictly scoped, and explicitly approved under the Dual-Use Review below. Passive is necessary but not sufficient: receiving a signal is not harmless when that signal belongs to a non-consenting third party (see *Third-party-minimizing*).
- **Operator-bound.** It protects the operator's own environment, devices, and data — the space they own or are responsible for. It is not built to reach into a third party's environment.
- **Third-party-minimizing.** Sensing across shared walls, common spectrum, or public airspace will receive signals from people and devices outside the operator's control. When it does, the capability must minimize by design: it does not retain third-party-attributable data, does not resolve it to identities, and discards it once the defensive inference that required it is complete. Incidental reception is tolerated; logging or profiling a third party is not.
- **Non-coercive.** It informs and defends. It does not act on, control, degrade, or harm another person or their property.

**Who counts as an "operator."** An operator is a person or group with clear, legitimate authority over the environment being observed — ownership, a lease, or explicit responsibility for securing it. Ownership of a space is not authority over the people in it: in shared or multi-occupant environments, operator status additionally requires notice to the other occupants, and a capability may not be operated by someone legally barred from contact with people likely to be present. *(Proposed definition, offered for the vote — the point is that "operator" cannot rest on self-attestation.)*

A tool that fails any of these criteria is neither automatically permitted nor automatically barred. It falls to the Dual-Use Review below, which may approve it with constraints, decline it, or — if it meets one of the hard limits in *What We Will Not Build* — confirm it cannot be built at all.

## The Boundary Test

Every proposed capability must pass a single question before work begins:

> **Could this capability, as designed, be pointed at a non-consenting third party to surveil, track, identify, or harm them — and if so, is that prevented by design rather than by policy?**

If the capability has no plausible offensive use, it proceeds — though because nearly everything we build is dual-use, this branch is expected to be rare, not the default escape hatch. If it has an offensive use that is genuinely prevented by how it is built, it proceeds with that constraint documented. Prevention must live in the artifact, not in how it is operated: receive-only hardware with no path to retain third-party data is a design control; "we won't point the model at others" is a policy promise. Because a general-purpose model is the same artifact whichever way it is pointed, such capabilities cannot satisfy the by-design branch on their own and default to Dual-Use Review. If offensive use is prevented only by asking nicely — a README warning, an honor system — it goes to Dual-Use Review or does not get built.

Which branch a capability falls into is not self-certified by its proposer. The determination and the evidence for it are recorded and confirmed by at least one other member before work begins.

The burden is on the capability to prove it is bounded, not on a critic to prove it is dangerous.

## What We Will Not Build

The following are hard limits. They are not subject to case-by-case exception and are not waived by claimed good intent, research framing, or the fact that similar tools exist elsewhere:

- **Mass-surveillance systems** — any capability designed to monitor, identify, or track people at scale, or to be operated against a population rather than to defend a single operator's own environment. *("At scale / against a population" means people or devices the operator neither owns nor is responsible for — as distinct from a multi-sensor setup defending the operator's own environment.)*
- **Offensive cyber-weapons** — malware, exploits, intrusion tooling, or anything whose purpose is to gain unauthorized access to, disrupt, or damage systems we do not own.
- **Covert tracking of people** — tools whose purpose or effect is to locate, follow, or identify specific individuals without their consent, including persistent device-fingerprinting aimed at non-consenting third parties, or logging an identifiable third party's presence, movements, or device identity over time — at any scale, not only "at scale." Detecting and characterizing a device that is itself intruding on the operator's own space (an unknown tracker in your home, a drone over your property) is defensive and permitted; the line is intrusion-on-the-operator versus general tracking of others.
- **Active attack or disruption** — jamming, spoofing, denial-of-service, or signal interference intended to degrade or disable another party's systems, as opposed to detecting and characterizing them.
- **Deanonymization-as-a-service** — capabilities built to strip privacy from others rather than to preserve it for the operator.

These align with, and make concrete, the limits already named in the Constitution and our GitHub Acceptable Use commitments.

**One narrow exception.** An offensive proof-of-concept built solely to validate one of our own defenses — and never published, never operated against real third parties — may be approved through Dual-Use Review. This is the only path by which anything resembling the above may be built, and it exists so that defensive claims can be tested honestly rather than merely asserted.

## The Gray Zone: Dual-Use Review

Most hard cases are not on the list above; they sit in the middle, where a defensive capability has a real offensive shadow. These are decided, not assumed.

When a proposed project's offensive potential cannot be ruled out by design alone, it goes to a **Dual-Use Review** — a group vote, consistent with the Constitution's voting process — before significant work begins. ("Significant work" begins at any collection of real, non-synthetic signal data, or any code beyond a paper design.) The review answers three things and records them:

- **Threat model.** Who is this defending, against what, in whose environment.
- **Offensive shadow(s).** What this same capability does if pointed outward — each distinct offensive use — and what in the design prevents each.
- **Disposition.** Approved as-is, approved with binding constraints (e.g., receive-only, no third-party data retention), or declined.

This keeps the boundaries a living rule rather than a frozen wall: new capabilities can be admitted deliberately, with their constraints on the record, instead of being silently grandfathered in.

## Publication & Disclosure

How we publish is itself a boundary, because release decisions change who a capability empowers — and open release strips the operator-binding that makes a tool defensive in the first place. A capability whose defensive character depends on *who operates it* rather than on *how it is built* therefore defaults to review before any release, not to open publication.

Beyond that principle, release policy is set by the Constitution's separate **Publication Architecture** vote; this document does not pre-decide it.

## Amendment

These boundaries are part of the Constitution and change only through its amendment and voting process. The hard limits in *What We Will Not Build* are intended to be stable; the review procedures are expected to evolve as the organization does. Any change is recorded, so the reasoning behind a boundary survives the people who set it.

## Open Questions

Deliberately left open so this v1 stays to the basics. Each needs resolution by the group, and the first two must be settled before the Dual-Use Review can actually operate:

- **Review mechanics.** Who triggers a Dual-Use Review, who convenes it, and by when — and the fact that this depends on the Constitution's voting process being ratified first. Until it is, the hard limits apply but no gray-zone capability can be cleared.
- **Conflict of interest.** Recusal and quorum rules for the review vote, so that in a small group a proposer cannot be the sole approver of their own capability.
- **Existing work.** A transition rule that runs current and in-flight projects through the Boundary Test on ratification, so nothing is silently grandfathered in.
- **Violations and data hygiene.** What happens when a boundary is crossed — who flags it, who halts the work, what remedy applies — and a rule barring captured signal data and credentials from any open-sourced tool.
- **How fully to specify the review.** Whether to formalize the Dual-Use Review process in the Constitution or keep it the light pointer it is here.

---

*Draft v1 — submitted for group review and vote. The standing default flagged for the group's decision: the prohibitions in "What We Will Not Build" are treated as hard bright-lines, with everything ambiguous routed to Dual-Use Review rather than handled case-by-case. The Defensive-Only Principle's criteria, the operator definition, and the validation carve-out are proposed, not settled, and are open to revision. Publication policy is deferred to the separate Publication Architecture vote.*
