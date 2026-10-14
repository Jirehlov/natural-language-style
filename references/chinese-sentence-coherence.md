# Chinese sentence boundaries, subject continuity, and discourse coherence

This reference implements a deliberately strict house-style requirement for assistant-authored Chinese. It is more restrictive than ordinary Chinese syntax. Never present the one-subject preference as a universal grammatical fact. Preserve source quotations and faithful reproduction when fidelity takes priority.

## 1. Mandatory one-subject check

- Use one predicating subject per Chinese sentence as a hard stylistic constraint. A sentence is normally closed by a Chinese full stop, question mark, or exclamation mark. The explicit semicolon exception below is permitted by this house style.
- Count the subject of every asserted predicate, including subjects introduced by a temporal, causal, conditional, concessive, or reported-content clause. A conjunction by itself does not excuse a change of subject within a sentence.
- One grammatical subject may take several predicates; it may be omitted from later predicates only if it remains the same and recoverable. A genuinely coordinated noun phrase that acts as one syntactic subject also counts as one subject. Do not confuse a topic phrase, a time/place adjunct, or an object with a new subject.
- If related predicates share a subject, first try one well-formed sentence with serial actions and suitable modifiers. If two predicates require different subjects, consider an accurate single-subject rewrite or use separate complete sentences. Supply a clear intersentence relation when readers would otherwise have to guess how they connect. Never produce a staccato series of short sentences as the default repair.
- Alternatively recast the information under one truthful grammatical subject, using a nominal, temporal, prepositional, or agentless expression when the original facts permit it. Never erase an important agent or create a causal relation merely to meet the constraint.
- Use a semicolon between different subjects only if the semicolon independently passes the punctuation and semantic-relation test in section 2. A comma, colon, dash, or a newly added conjunction cannot replace this boundary merely to retain different subjects.
- If an accurate embedded quotation has two subjects, keep the quotation verbatim and apply the rule to the surrounding assistant-authored prose.
- One-subject compliance is insufficient if an abstract object covertly occupies the *semantic* role of willing or directing an action elsewhere in the sentence. After identifying grammatical subjects, audit implied agency across adverbials, noun phrases, passive forms, and causative structures.

### Subject audit procedure

1. Segment each sentence into actual predicates, including embedded asserted clauses.
2. Annotate the semantic and grammatical subject of each predicate. Distinguish a shared omitted subject from a newly introduced one.
3. If two genuinely different subjects appear in the same sentence, split at a full stop, or apply the narrow semicolon exception. Rephrasing with one subject is acceptable when meaning stays intact.
   Recheck implicit personification when reconstructing subjects: `在理论的引领下，研究者……` passes a superficial subject count but fails the semantic-agency rule.
4. Reread the resulting sentences for complete meaning, coherent references, preserved factual relations, and paragraph rhythm. Splitting a sentence can expose a missing premise or dangling connective and can create an unnatural run of short sentences.

## 2. Standards-compliant semicolon gate

Follow GB/T 15834-2011, sections 4.6.3.1-4.6.3.3 and annex B.1.3-B.1.4:

- A semicolon marks a pause between parallel clauses in a compound sentence, especially if a clause already contains commas.
- In a multi-layer nonparallel compound sentence, a semicolon can mark the boundary between first-level portions, principally when a higher-level choice or contrast is being expressed.
- Semicolons can also separate items in a structured enumeration. An enumeration may follow its own layout rules.
- A semicolon is technically a sentence-internal punctuation mark. This house style expressly accepts semicolon-delimited clauses as the limited exception to its one-subject-per-sentence preference.
- Different subjects alone NEVER justify a semicolon. Test for real parallelism or first-level structural layering, and for a reason a full stop would unnecessarily sever a tightly organized relationship. When in doubt, use full stops.
- Avoid a semicolon between unrelated independent statements, in a simple chronology better expressed in complete sentences, or where the punctuation would give an unsupported comparison or contrast.

Standard reference: https://www.shsmu.edu.cn/yywz/info/1026/1526.htm

## 3. Logical path between sentences and paragraphs

Before drafting more than one sentence, identify the paragraph's controlling question, assertion, or purpose. Each sentence must have a job and move that purpose forward.

Possible jobs: thesis; definition; qualification; evidence; example; explanation; cause; consequence; condition; chronology; comparison; exception; response to a grounded objection; implication; transition. These labels are for internal checking, not mandatory headings or formulaic composition.

For every adjacent pair, identify a defensible relation, such as:

- Question -> answer; claim -> reason or evidence; general statement -> specific explanation or example.
- Event -> later event when chronology is supported; cause -> effect when causal evidence exists.
- Similar items -> comparison; differences -> bounded contrast; problem -> a grounded response.
- Premise -> inference; a series of points -> a synthesis that accurately depends on those points.

If no relevant link can be stated, reconsider the sentence's location, paragraph boundary, evidential basis, or necessity. Do not glue unrelated sentences together using arbitrary connectives. Do not infer time order, causation, concession, or contrast from adjacency alone.

Sentence order should follow the intended reasoning, rather than the order in which ideas occurred to the model. A paragraph can use chronological, explanatory, inferential, comparative, or problem-solving progression. Choose the progression the task actually requires. Avoid making every paragraph follow a fixed claim-explanation-summary rhythm.

An implicit connection is acceptable only if a reader can readily recover the actual relation from sequence, shared topic, and wording. When an omitted connective leaves a real ambiguity, add a precise supported connective, restate the relation, or rearrange sentences. Avoid unsupported rhetorical markers under the main skill's external-antecedent and counterexpectation gates.

## 4. Mandatory anti-fragmentation and sentence-rhythm gate

**Paragraph quality takes priority over a mechanical "one fact = one sentence" output pattern.** Keep the hard one-subject constraint and GB/T semicolon requirements while using naturally developed sentences. There is no fixed minimum or maximum length: a short sentence may be appropriate, but three or more consecutive very brief declarative sentences or repeated simple-subject openings demand a substantive rewrite attempt.

### Repair order (apply in this sequence)

1. **Plan the logical unit.** Identify the point of the paragraph and the actual relation between facts. Decide which facts form one statement and which deserve independent sentences.
2. **Unify shared-subject predicates.** If the same real actor performs several related actions, combine with natural verb-phrase coordination or modifiers: `研究人员整理资料、核对引文，并修订报告。` Distinguish shared-agent serial action from a hidden second subject in an embedded asserted clause.
3. **Rebuild a single-subject sentence where faithful.** Promote a relevant time, condition, object, evidential basis, or descriptive qualification into a modifier **only if doing so preserves the semantic roles and one-subject rule**. Do not hide a second finite subject in a `因为/虽然/当` subordinate clause, and do not let an abstract concept acquire implied intentional agency through a modifier.
4. **Handle genuine subject changes correctly.** A full stop is the default; a semicolon may compress genuine parallel responsibilities or other formally licensed structures. Do not join separate subjects with commas, connective words, colons, or dashes. Do not overuse semicolons merely to suppress short sentences.
5. **Improve the surrounding paragraph.** Remove repetition; adjust the order of statements, where grounded; expand a sentence with existing relevant detail; or use an additional paragraph when the topic really changes. A connector may express a real relation but cannot create one. Avoid a chain of sentence fragments that makes readers infer the argument unassisted.
6. **Read for cadence and fidelity.** Prefer a mixture of developed sentences and occasional necessary short ones. Reject excessive length, bloated `的` chains, invented chronology or causation, rhetorical padding, duplicated subjects, or unlicensed pronouns (`它` for an abstraction; superfluous `其`).

### Contrastive examples

**A. Repeated same-subject short sentences**

Choppy: `研究人员整理了资料。研究人员核对了引文。研究人员修订了报告。`

Prefer: `研究人员整理资料、核对引文，并修订了报告。`

The single subject supports all three predicates. The rewrite does not add an unsupported causal or temporal claim.

**B. True parallel roles, with semicolon justified independently**

Fragmented: `编辑核对事实。作者调整论证。`

Permitted if the parallel responsibilities are the point: `编辑核对事实；作者调整论证。`

The house style allows this semicolon because the roles form a genuinely parallel structure. If the context supplies only two unrelated events, keep separate sentences; do not invent a relationship.

**C. Repeated short judgments about one subject**

Choppy: `研究团队已完成初稿。研究团队还检查了引文。研究团队正在核对附录。`

Prefer: `研究团队已完成初稿并检查了引文，目前正在核对附录。`

Use the same recoverable subject. The rewrite preserves the separate completion and current-progress states without introducing a new actor.

**D. Short sentences retained for a real reason**

`证据不足。` can remain short when it directly answers whether a claim is established. For a longer explanation, add the actual grounds and uncertainty in coherent sentences without manufacturing extra facts.

### Mandatory preflight

After all other edits, scan each Chinese paragraph for abrupt stops, repeated short clauses, and mechanical sentence openings. When such a pattern appears, perform the repair sequence above, then rerun the subject count, semicolon gate, abstract semantic-agency gate, pronoun restrictions, source fidelity, and neighboring-sentence coherence checks. Accept a short-sentence run only when no faithful, grammatical, and logically sound restructuring is available.

## 5. Mandatory ripple check after inserting, removing, replacing, or moving prose

Treat insertion and deletion as changes to the structure of the passage, not merely local edits.

**Insertion (A -> new X -> B):**

1. Record the old A -> B relationship.
2. Verify that A -> X and X -> B are both logical, supported, and appropriately ordered.
3. Check whether X redirects the topic, narrows the claim, changes chronology, or creates a new antecedent for words such as 'this', 'therefore', 'however', and 'the former'. In Chinese, resolve every `它` against a concrete entity; avoid pronouns for abstract antecedents, including overused `其` and bare `这`.
4. If X breaks the argument or merely interrupts its flow, move it to a more suitable position, make a paragraph break, reframe the following sentence, or omit it.

**Deletion (A -> [removed X] -> B):**

1. Verify that A -> B is coherent after X disappears.
2. Restore or remove any premise, evidence, definition, comparison target, transition, or pronoun antecedent supplied by X.
3. Delete or revise conclusion markers if the surviving premises no longer support the conclusion. Do not silently invent the missing evidence.

**Replacement or reordering:**

1. Verify both the incoming and outgoing edges for each changed sentence.
2. Recheck chronology, causal direction, list numbering, forward/backward references, and degree of certainty.
3. Reread the entire paragraph and its neighboring paragraphs. Revise topic sentences, transitions, repeated terms, paragraph breaks, and summaries as needed.
4. Rerun the one-subject test, semantic-agency gate, abstract-pronoun antecedent check, and semicolon gate on every sentence modified in this process.

## 6. Decision examples

### Example A: unrelated-subject comma splice

Bad: `甲完成了审核，乙签发了报告。`

Preferred: `甲完成了审核。乙签发了报告。`

The period gives each subject its own sentence. Add a relation only if evidence or context supports it. Do not add a fabricated 'therefore' or 'afterward'.

### Example B: true structural parallelism

Permitted semicolon: `甲负责抽样；乙负责复核。`

This marks a genuine contrast in parallel responsibilities. For ordinary adjacent facts or weak parallelism, choose separate sentences instead.

### Example C: shared subject

Permitted: `甲完成了审核，签发了报告。`

The subject is shared by both predicates, so the comma does not introduce a second subject.

### Example D: an insertion that disrupts reference

Original: S1 gives evidence E. S2 draws a conclusion from E.

A new sentence X about an unrelated approval is inserted between S1 and S2. The phrase 'on that basis' in S2 can now seem to refer to X. Reposition X outside this inference or name E explicitly in S2. Verify that E really supports S2.

### Example E: deletion of a logical premise

Original: S1 describes the question. S2 provides a relevant result. S3 says 'therefore' and draws a conclusion.

If S2 is deleted, reassess S3. Remove the inference if S1 alone does not support it. Replacing 'therefore' with a period is insufficient when the argument itself has lost its support.

## 7. Final preflight

Ask these questions silently for each authored Chinese paragraph:

1. Does any full-stop-bounded sentence assert predicates of two distinct subjects? If yes, rewrite or apply a licensed semicolon boundary.
2. Is every semicolon justified by genuine parallelism, first-layer structure, or enumerated items as defined in GB/T 15834-2011?
3. Can I name the role of each sentence in the paragraph and the relation of each adjacent sentence pair?
4. Did any insertion, deletion, or relocation strand a pronoun, qualifier, connective, premise, or conclusion?
5. Does the paragraph retain its central purpose and evidential integrity after edits? If not, restructure and check again.
6. Does any sentence imply that an abstraction commands, chooses, inspires, guides, or acts intentionally, even if grammatically subordinate? If yes, restore the actual actor or rewrite the relation.
7. Does every `它` refer to a concrete entity? If any abstract referent is pronominalized, can an explicit noun phrase or omission replace the pronoun? Use `其` sparingly only when indispensable.
8. Have I left a repetitive chain of three or more very brief sentences, repeated same-subject openings, or one-fact-per-period phrasing? Attempt natural same-subject consolidation without inventing factual relations, adding abstract agency, or misusing semicolons.
