# Risk Flags Catalog

Patterns that indicate hidden risk in a vendor response. Use these when assigning red/yellow/green flags during analysis.

## 🔴 Red flags (recommend rejection or major concern)

### 1. Underbid pattern
**Symptom**: Bid is < 30% below the engineer's estimate or < 30% below the median bid.
**Risk**: Vendor cannot deliver at the proposed price. Will demand change orders or cut quality mid-project.
**What to do**: Demand a written cost breakdown. If unconvincing - recommend rejection.

### 2. Missing or expired certifications
**Symptom**: ISO 27001 expired, accessibility audit missing, regulator certification not provided.
**Risk**: Vendor cannot legally operate in regulated environment. Project will be blocked at go-live.
**What to do**: Demand current certificates within 5 days. If not provided - automatic disqualification.

### 3. References that don't validate
**Symptom**: Vendor lists 5 reference projects but you can only verify 2. Or reference customers refuse to comment.
**Risk**: Vendor inflates its track record. Real experience is below the claimed.
**What to do**: Reduce experience score to verified projects only. Flag as red.

### 4. Key personnel not committed
**Symptom**: CV of "lead architect" is included, but no exclusivity clause. Vendor reserves the right to substitute.
**Risk**: The senior person you saw in CVs will not actually do the work. A junior will be assigned.
**What to do**: Demand an exclusivity clause as condition for award. If refused - red flag.

### 5. Architecture mismatch with NFR
**Symptom**: NFR requires data residency in Israel; proposed architecture uses AWS US-East with "backup option in Frankfurt".
**Risk**: Direct violation of mandatory requirement. Vendor either misunderstands or hides it.
**What to do**: Demand written confirmation that all data and processing remain in Israel. If can't commit - reject.

### 6. Vendor is in financial distress
**Symptom**: Mentions of "restructuring", recent layoffs, declining revenue, news of acquisition or merger.
**Risk**: Vendor may not survive the contract term. Mid-project bankruptcy = catastrophic.
**What to do**: Demand recent financials, audit reports. If concerns - require backup vendor or escrow.

### 7. Conflict of interest not disclosed
**Symptom**: Vendor's senior staff has prior relationship with someone on the procuring committee, undisclosed.
**Risk**: Legal risk for the buyer. Procurement may be invalidated.
**What to do**: Investigate and disclose to legal. Likely disqualification.

## 🟡 Yellow flags (require clarification before recommendation)

### 8. Vague requirement coverage
**Symptom**: Requirement says "support full Hebrew including RTL". Vendor responds "supports Hebrew". Doesn't address RTL specifically.
**Risk**: Vendor will later claim they didn't commit to the specific behavior.
**What to do**: Demand written confirmation in the next round.

### 9. Methodology gaps
**Symptom**: Vendor proposes Discovery → Build → Deploy. Missing: organizational change management, user training, post-go-live support.
**Risk**: Implementation will succeed technically but fail organizationally. Adoption will be poor.
**What to do**: Ask for a complete methodology including the missing phases. If declined - score lower but don't reject.

### 10. SLA defined too loosely
**Symptom**: SLA says "best effort response within 24 hours". No specific time-to-resolve, no penalty structure.
**Risk**: When something breaks, there's no contractual lever to force timely response.
**What to do**: Demand specific time-to-resolve metrics by severity (P1/P2/P3) and clear penalty structure.

### 11. Subcontractor reliance not disclosed
**Symptom**: Vendor's response sounds like they'll do everything in-house. Detailed inspection reveals 40% of work outsourced.
**Risk**: Quality control degrades. Communication channels multiply. Vendor may not own subcontractor commitments.
**What to do**: Demand transparency about subcontractor identity, scope, and quality controls. If subcontractor is a competitor or unknown party - escalate.

### 12. Pricing model is unclear
**Symptom**: One-time fee + annual service. But the annual fee includes "platform updates" - undefined scope.
**Risk**: Vendor will later interpret "platform updates" as anything they want, charging for change requests separately.
**What to do**: Demand explicit definition of what's included in the annual fee. If declined - lower price score.

### 13. Inconsistencies across sections
**Symptom**: Section 4.2 says "5 years experience". Section 7.1 says "8 years". Section 12 references 3 projects. Math doesn't add up.
**Risk**: Vendor copy-pasted from prior bids without updating. Or inflated some claim.
**What to do**: Choose the lower number for scoring. Flag the inconsistency in the analysis.

### 14. No transition / exit plan
**Symptom**: Vendor describes how they enter the engagement, but not how they leave or transfer to another vendor.
**Risk**: Lock-in. Switching vendors at end of contract becomes costly or impossible.
**What to do**: Demand explicit transition assistance clause - 60-90 days, knowledge transfer, source/configuration access.

### 15. Borderline threshold compliance
**Symptom**: Vendor meets threshold conditions on a technicality (e.g., "3 projects" but two were tiny pilots, one was an upgrade not a full project).
**Risk**: Vendor lacks real depth, but technically passes.
**What to do**: Note the borderline pass. Score experience criterion lower. Recommend committee discussion.

## 🟢 Green flags (positive indicators worth noting)

### 16. Detailed methodology
Specific phases with exit criteria, deliverables, and decision gates. Shows the vendor has done this before successfully.

### 17. Strong references in same domain
Multiple reference projects in the exact same industry and similar scale. Customer references that respond positively to validation calls.

### 18. Senior personnel committed
CVs of senior personnel + exclusivity clause + named in contract terms.

### 19. Risk awareness
Vendor explicitly mentions known risks of the project type and how they mitigate them. Shows experience and honesty.

### 20. Realistic timeline
Vendor proposes a timeline that allows for proper Discovery, learning, and iteration. Not "we'll deliver in 4 months" when industry standard is 9.

### 21. Transparent pricing
Itemized pricing with clear definitions. Specific allocations for change requests. NPV calculations for multi-year deals.

## Pattern recognition tips

### Watch the consistency of voice
A response written by 5 different people sounds different from one written by a single owner. Check whether sections seem to come from different sources - if yes, it may indicate the vendor cobbled together pieces from different past bids without coordination.

### Compare similar sections
If 3 vendors all claim "industry-leading SLA of 99.9%", look at the small print. Two of them define availability conservatively (excluding maintenance windows, force majeure, etc.) while one doesn't. The honest one may look worse on paper but be safer in reality.

### Read the appendices
Vendors put inconvenient details in appendices. Check the small print: subcontractor lists, exclusions, force majeure definitions, IP ownership.

### Look at past customers
Public sector vendor lists are usually disclosed. If a vendor claims expertise in banking but has no banking customers in their public list - red flag.

## Anti-pattern: don't over-flag

Don't flag everything as red. The signal is in distinguishing real risks from minor issues. Use this rough heuristic:

- **Red**: this issue alone justifies rejection. Or even after fixing, the contract is at significant risk.
- **Yellow**: this issue is fixable in 1-2 weeks of clarification. After fix, the vendor is acceptable.
- **Green**: positive signal, build confidence in this vendor.

If 60%+ of vendors get red flags, the analysis is overly punitive. Re-calibrate.
