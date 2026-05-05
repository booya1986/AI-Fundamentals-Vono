# Vono Project Lifecycle

Every Vono engagement has 5 phases. Each has explicit entry and exit criteria. Crossing a phase gate requires written client approval.

## Phase 1: Discovery (1-3 weeks)

**Goal**: Understand the real problem before solving anything.

**Entry criteria**:
- Signed engagement (one-pager + SOW)
- Sponsor identified
- Initial document access

**Activities**:
- Stakeholder interviews (5-15 people, 30-60 min each)
- Document review (existing systems, processes, prior projects)
- Process mapping (current state)
- Pain-point synthesis
- Constraint mapping (technical, regulatory, organizational, budget)

**Deliverable**: Discovery memo — 5-10 pages, structured as:
1. Problem statement (as stated by the client)
2. Problem statement (as we understand it after Discovery)
3. Stakeholder map
4. Current state
5. Constraints
6. Hypothesis for the right approach
7. Recommendation: which phase 2 design path

**Exit gate**: Client signs off on the Discovery memo. The "real problem" alignment is critical — if Discovery reveals a different problem than the original brief, this is when to renegotiate scope.

**Common mistake**: rushing through Discovery to get to "real work". Discovery IS real work. Skipping it costs 3x more in the Build phase.

---

## Phase 2: Design (2-6 weeks)

**Goal**: Decide what to build, how, and how it will succeed.

**Entry criteria**:
- Approved Discovery memo
- Decision authority confirmed for design choices
- Business owner assigned for each major decision

**Activities**:
- Solution architecture (high-level)
- Process design (target state)
- Vendor selection (if relevant)
- Risk register
- Change-management plan
- Success criteria definition (measurable)

**Deliverable**: Design document — 15-30 pages:
1. Executive summary
2. Solution architecture
3. Target-state process flows
4. Roles & responsibilities (RACI)
5. Phased implementation plan
6. Risk register with mitigation strategies
7. Success criteria + how they'll be measured
8. Cost estimate (refined from SOW)
9. Decisions log (what was decided, by whom, when, why)

**Exit gate**: Steering committee signs off on the Design document. This is where the budget either commits or gets renegotiated.

**Common mistake**: producing a Design document so abstract that no one knows what to actually build. The Design must include enough specificity that a fresh team member could pick it up and start.

---

## Phase 3: Build (varies — weeks to months)

**Goal**: Produce the thing.

**Entry criteria**:
- Approved Design document
- Build team assigned (Vono + client + vendors)
- Tooling and access ready

**Activities**:
- Iterative build (whether software, training program, process change, etc.)
- Weekly checkpoints with sponsor
- Bi-weekly steering reviews
- Continuous risk management
- Documentation as we go (not at end)

**Deliverable**: The actual built artifact + Build report:
- What was built (specific)
- How it differs from Design (and why)
- Quality evidence (test results, pilot feedback, etc.)
- Outstanding items (deferred to post-Deploy)

**Exit gate**: Sponsor + technical lead sign off. The artifact passes pre-deployment quality bar.

**Common mistake**: scope creep. Every "small addition" during Build extends the timeline by 2-3x its visible work. Maintain a change-request log; route every change through formal review.

---

## Phase 4: Deploy (1-4 weeks)

**Goal**: Roll out carefully, avoiding the obvious failures.

**Entry criteria**:
- Approved Build artifact
- Deployment plan written (sequencing, rollback, communication)
- Pilot group identified
- Support model in place

**Activities**:
- Pilot deployment (subset of users / single business unit)
- Pilot feedback loop (1-2 weeks)
- Course corrections
- Wider rollout (waved or big-bang based on plan)
- User training delivered
- Communication campaign executed

**Deliverable**: Deployment report:
- What was deployed, where, when
- Issues encountered + resolution
- User feedback summary
- Open items for Stabilize phase

**Exit gate**: Initial stabilization criteria met. Sponsor + business owner sign off.

**Common mistake**: declaring victory at Deploy. Deploy is when the real risk starts — users encounter the new thing, and most projects "die" at this phase from lack of adoption.

---

## Phase 5: Stabilize (1-3 months)

**Goal**: Hand over to BAU. Confirm the change actually sticks.

**Entry criteria**:
- Successful Deploy
- BAU support team identified
- Knowledge transfer plan in place

**Activities**:
- Monitoring against success criteria (defined in Design)
- Issue triage and fix (with shrinking response window — Vono presence reduces gradually)
- Documentation finalization
- Knowledge transfer to BAU team
- Lessons-learned workshop
- Final report

**Deliverable**: Final report — 8-15 pages:
1. What we set out to do (recap of Discovery problem statement)
2. What we did (recap of Build + Deploy)
3. What happened (results vs. success criteria)
4. What worked
5. What didn't
6. What we'd do differently
7. Outstanding recommendations for the client to pursue post-engagement

**Exit gate**: Client signs final acceptance. Vono team transitions out.

**Common mistake**: leaving without a real handover. The BAU team should be running the artifact independently for at least 2-4 weeks before Vono fully exits, with Vono available for questions.

---

## Cross-phase principles

### The phase gate is real

Don't proceed to the next phase without written approval. If the client says "let's just keep going, we'll formalize later" — push back. Phase gates exist to catch misalignment before it gets expensive.

### Documentation is the artifact

The deliverable at each phase is a written document. Verbal alignment doesn't count. If you can't write it down, you don't actually agree.

### Risk register is alive

Risks change between phases. A risk that was "monitor" in Discovery may be "active" in Build. Update the register at every phase gate.

### Lessons-learned every phase

Don't wait until the end to capture what went well/poorly. At every phase gate, capture:
- What worked (continue)
- What didn't (change)
- What surprised us (investigate)

This becomes the Final report's content. If you do it once at the end, you'll forget half of it.

## Skipping phases

You can compress phases. You can't skip them. The shortest reasonable engagement passes through all 5 in 4-6 weeks. Anything shorter is either a tiny scope (fine) or skipping critical work (not fine).

Compression patterns that work:
- Discovery + Design merged for clear-scope projects (1 week + 2 weeks)
- Build + Deploy parallel for waved rollouts
- Stabilize compressed when the artifact is small and well-tested

Compression patterns that fail:
- Skipping Discovery because "we already know the problem" (no, you don't)
- Skipping Design and going straight to Build (you'll rebuild 3 times)
- Skipping Stabilize because "the project is over" (it's not, until users adopt)
