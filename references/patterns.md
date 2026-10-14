# Cross-language pattern inventory

Use this file as a diagnostic reference for recurrent LLM prose habits. The strongest rules concern **assistant-invented corrective negation** and **assistant-invented discourse tension**. The core skill defaults corrective contrast, persistence, and concession to unmarked wording unless the source or task supplies the proposition, baseline, or counterexpectation that makes the marked relation informative.

## 1. Corrective negation: fail closed

### What counts as corrective negation

A corrective negative presents or implies an X, rejects it, and redirects attention to Y. Typical forms include:

- Chinese: `不是X，而是Y`, `并非X，而是Y`, `并不是X，而是Y`, `不只是X，更是Y`, `不是因为X，而是因为Y`, `问题不在X，而在Y`, `关键不在X，而在Y`, `与其说X，不如说Y`, `不能简单理解为X`, `这并不意味着X`, `并不代表X`.
- English: `not X but Y`, `not just X but Y`, `not merely X but Y`, `rather than X, Y`, `less X than Y`, `this does not mean X`, `far from X`, `by no means X` when used to set up a correction.
- Comparable constructions in other languages.

These forms are high-risk because they let the model invent a weak or mistaken X and then sound insightful by rejecting it.

### External provenance whitelist

Corrective negation is licensed only when X is explicitly present in:

- the user's message;
- an earlier user turn;
- quoted or supplied material;
- an attachment being discussed;
- retrieved evidence or tool output relevant to the task.

The assistant must be able to point to concrete source wording for X. A merely implied proposition is insufficient.

### Assistant provenance blacklist

The following never license corrective negation by themselves:

- a proposition the assistant introduced earlier in the same response;
- a proposition from an earlier assistant answer that the user has not explicitly adopted, quoted, challenged, or asked about;
- an imagined objection;
- a hypothetical misunderstanding;
- a stereotype or presumed misconception;
- an unstated alternative;
- a precautionary disclaimer;
- hidden reasoning;
- an imported claim that is irrelevant to the user's task.

Writing X one sentence earlier does not make X discourse-old. The assistant cannot self-authorize a denial.

### Positive-first generation

Start from the supported proposition Y. Write Y directly unless the task requires resolving an externally supplied X.

Bad:

`这不是效率问题，而是组织权限的问题。`

Prefer:

`主要问题出在组织权限的分配。`

Bad:

`这并不意味着方案不可行。`

Prefer the actual supported limitation, uncertainty, or result. If the evidence is `成本超出预算 18%`, write that fact rather than inventing `方案不可行` as a target.

Bad:

`This is not simply a technical problem; it is a governance problem.`

Prefer:

`The main issue is how decision rights are assigned.`

### Y-alone test

For every candidate `not X but Y` structure:

1. Delete the X half.
2. Read Y alone.
3. If Y communicates the intended information, output Y alone.
4. If both X and Y genuinely matter, state the real relation: weight, scope, chronology, cause, evidence, or category.

Example with a genuine comparison:

User: `这个结果主要是数据量不足还是标签质量差造成的？`

Prefer:

`标签质量的影响更大；数据量不足也有影响，但作用较小。`

This resolves both user-supplied alternatives without turning them into a polished denial/replacement slogan.

### Exact-anchor examples

Licensed:

User: `这是不是说明模型不可靠？`

Possible answer:

`现有结果不足以支持“模型不可靠”这个判断。样本量很小，所以置信区间较宽。`

The user supplied the proposition `模型不可靠`.

Unlicensed:

User: `解释一下这个实验结果。`

Bad answer:

`这并不意味着模型不可靠；真正的问题是样本量太小。`

The user never raised unreliability. Prefer:

`小样本会增加估计的不确定性。`

### Generated-alternative exception

When the user explicitly requests objections, hypotheses, counterarguments, alternative explanations, red-team cases, or debate positions, the assistant may generate candidate X propositions because generation of alternatives is part of the task. Label them as candidates before evaluating them. Do not use the exception for decorative contrast.

### Ordinary factual negatives

The fail-closed rule targets corrective or rhetorical negation, especially invented X -> deny X -> elevate Y structures. It does not require unnatural avoidance of necessary factual negatives.

Keep direct negatives when accuracy requires them, for example:

- a file contains no matching rows;
- an API does not support a requested parameter;
- a law prohibits an action;
- the user's explicitly stated hypothesis is unsupported;
- a safety boundary requires saying that an action cannot be performed.

Prefer direct factual wording over staged contrast.

## 2. Unlicensed persistence, concession, and reversal

LLM prose often adds `still`, `yet`, `however`, `nevertheless`, `仍然`, `依然`, `却`, `但`, or `然而` to make a plain statement feel more dynamic. These markers carry presuppositions and discourse relations. Treat those relations as claims that need support.

### Persistence markers presuppose a baseline or challenge

`仍/仍然/依然/仍旧/still/remain/continue to` normally tell the reader that a property survives across time, change, challenge, doubt, or an expected cessation. If the only available fact is Y, write Y.

Unlicensed:

`这个结论仍然成立。`

when no earlier state, intervention, challenge, or prediction has been supplied.

Prefer:

`这个结论成立。`

Licensed:

`改版前留存率为 42%；改版后仍为 42%。`

Here the earlier value supplies the baseline and the later measurement makes persistence informative.

A user challenge can also license reaffirmation:

User: `去掉异常值以后结论还成立吗？`

Prefer a direct answer such as:

`成立。去掉异常值后，效应方向和置信区间变化很小。`

The challenge makes persistence relevant, but a marked `仍然成立` is optional rather than automatic.

### Adversatives presuppose a real counterexpectation

`却/但/但是/然而/不过/yet/however/nevertheless/nonetheless/even so` tell the reader that the next proposition conflicts with, qualifies, or defeats an expectation created by the prior discourse. The model must be able to name that expectation and its source.

Unlicensed:

`模型规模更大，却仍会出现这种错误。`

If the source never claims that scale should eliminate the error, the sentence manufactures both the expectation and its defeat. Prefer:

`更大的模型也会出现这种错误。`

Unlicensed:

`这个方法很简单，但很有效。`

when `simple -> ineffective` is only a rhetorical stereotype. Prefer:

`这个方法简单而有效。`

Unlicensed:

`数据有限，然而结论仍然清晰。`

when the response itself creates the idea that limited data should obscure the conclusion. State the data limitation and the evidential result separately.

Licensed:

A forecast in the source predicts a decline after an intervention, while the observed measurement remains flat. The forecast supplies the expectation and the observation defeats it. Marking that discrepancy can be useful when the task asks why prediction and observation differ.

### Concessive frames encode a hidden A -> not-B expectation

Frames such as `虽然 A，但是 B`, `尽管 A，仍 B`, `即使 A，也 B`, `although A, B`, `even though A, B`, and `despite A, B` assert more than A and B. They also tell the reader that A normally points away from B.

Keep the frame only when:

- A and B are both grounded;
- the A -> not-B expectation is explicit in the user/source, or is a concrete source-backed comparison, intervention, prediction, norm, or tradeoff central to the task;
- encoding the concession helps answer the task.

Do not rely on a generic stereotype or the assistant's intuition that B feels surprising.

### Affirmation and correction markers can carry the same problem

Words such as `确实`, `的确`, `诚然`, `当然`, contrastive `其实/事实上`, `indeed`, `in fact`, and `actually` often presuppose doubt, correction, or a competing view. When used for that function, require a live doubt or prior claim. If the sentence merely states a fact, omit the marker.

### Marker-deletion test

For each persistence, concession, reversal, or corrective affirmation marker:

1. Delete the marker.
2. Repair the grammar minimally.
3. Ask what semantic or discourse information disappeared.
4. If the answer is only `emphasis`, `flow`, `surprise`, or `sounds more nuanced`, keep the unmarked sentence.
5. Keep the marker only when a grounded baseline, challenge, contrast, or counterexpectation would otherwise be lost.

## 3. Manufactured objections and disclaimers

LLM prose often invents a possible objection and immediately answers it. This creates unnecessary negative material and can misattribute views to the user or source.

High-risk patterns:

- `有人可能会认为……但……`
- `这可能看起来像……其实……`
- `不要误解为……`
- `这并不意味着……`
- `One might think ..., but ...`
- `This may seem ..., but ...`
- `This should not be understood as ...`

Use these only when the objection is externally grounded or explicitly requested. Otherwise state the actual evidence or conclusion.

## 4. Abstract-agent prose

Vague abstractions are made to behave like intentional agents: a change `invites us`, a framework `demands`, a tension `reveals`, a mechanism `reminds`, a moment `speaks to`.

Prefer the real actor or the literal relation when available. Keep abstract subjects when they express genuine causal, legal, scientific, mathematical, or technical relations more precisely. In Chinese, extend the audit beyond grammatical subjects: phrases such as `在理论的引领下`, `受证据提醒`, or `回应框架的要求` can attribute intention to an abstraction even with a human grammatical subject. Restore a real person/institution or express the true basis, condition, evidence, or causation. Reserve `它` for concrete entities, never abstractions; prefer noun repetition/omission and use `其` for abstract anaphora only if indispensable. See `references/chinese-translationese.md` for clause-rebuilding patterns.

## 5. Nominalization without need

Prefer ordinary verbs over abstract nouns plus light verbs when meaning stays intact.

AI-like:

`The team conducted an evaluation of the proposal and made a determination to proceed.`

Prefer:

`The team evaluated the proposal and decided to proceed.`

## 6. Significance inflation

Watch for automatic labels such as `crucial`, `profound`, `transformative`, `pivotal`, `groundbreaking`, `historic`, `fundamental`, and their equivalents. Ordinary observations do not need an importance sentence attached to them.

Prefer the concrete consequence or inference.

## 7. Superficial interpretation verbs

Phrases such as `this highlights`, `this underscores`, `this showcases`, `this reflects`, `this embodies`, `这说明`, `这体现`, `这凸显`, `这彰显`, `这折射` often add rhetorical lift without adding information.

Replace them with the actual relation or consequence when possible.

## 8. Rule of three and over-balanced rhetoric

Do not default to exactly three adjectives, reasons, examples, risks, or benefits. Avoid mirrored antithesis, slogan cadence, and repeated parallel frames when the reasoning does not require them.

AI-like:

`The change makes the workflow faster, simpler, and more intuitive.`

Prefer naming only the improvements actually supported, whether there are one, two, or four.

### Sentence rhythm and anti-fragmentation

Avoid a run of telegraphic sentences that expresses one small fact per period with no developed reasoning. Combine naturally related predicates when the same grammatical subject supports them, and vary sentence length according to purpose. This is especially important in Chinese when strict one-subject and discourse-marker rules tempt the model to split everything. A well-grounded connective may be necessary for a clear relation; its deletion should trigger syntactic rebuilding rather than automatic sentence splitting. Different subjects still require separate sentences or the narrowly licensed semicolon described in `chinese-sentence-coherence.md`. Do not create false causal links, covert abstract intentional agency, redundant pronouns, or bloated sentences just to appear smoother.

## 9. Stock metaphors and pseudo-concepts

Watch for decorative systems such as bridges, lenses, mirrors, journeys, landscapes, tapestries, engines, ecosystems, pillars, foundations, roadmaps, catalysts, and flywheels.

Also reduce newly coined labels such as unnecessary `X化 / X性 / X感 / X逻辑 / X叙事 / X范式` when they make an ordinary observation sound theoretical.

Use established terminology when the field actually requires it.

## 10. Discourse-ordering scaffolding

Verify the real semantic connection and purpose of each neighboring sentence before removing ordering words. A clear argument can be expressed without announcing each step, but unrelated facts must not be glued together by punctuation or generic connectives. After insertion or deletion, recheck the earlier and newly adjacent sentences and any dependent inferences. For Chinese, enforce the one-subject and semicolon constraints in `chinese-sentence-coherence.md`.

Generic markers often announce structure without adding meaning: `first`, `second`, `next`, `additionally`, `moreover`, `finally`, `overall`, `in conclusion`, and equivalents such as `首先`, `其次`, `此外`, `另外`, `最后`, `总之`, `综上`, `总体而言`.

Keep them when order itself matters: chronology, procedure, ranking, dependency, proof structure, or an explicitly requested sequence.

If an opener promises a sequence or pair, complete the genuine structure or remove the opener. A lone `首先` or `on the one hand` is a warning sign.

## 11. Editorial scaffolding and vague authority

Reduce phrases that manage the reader instead of advancing the content: `it is important to note`, `it is worth mentioning`, `interestingly`, `in other words`, `at its core`, `值得注意的是`, `需要说明的是`.

Avoid unsupported vague authority such as `experts say`, `research shows`, `many believe`, or `observers note` when traceable support matters.

## 12. Canned openings, conclusions, and assistant filler

Avoid routine prompt restatement, obvious previews, generic recap paragraphs, and automatic service phrases such as `Certainly`, `Absolutely`, `Here's a comprehensive breakdown`, `Feel free to ask`, or `Hope this helps` when they add nothing.

## Language-specific notes

### Chinese

Run an especially strict scan for:

`不是……而是……`
`并非……而是……`
`并不是……而是……`
`不只是……更是……`
`不单是……更是……`
`不是因为……而是因为……`
`问题不在……而在……`
`关键不在……而在……`
`与其说……不如说……`
`不能简单理解为……`
`这并不意味着……`
`并不代表……`

Default repair: remove the invented X and write the supported Y directly. Require an external exact anchor before retaining the correction.

Also scan strictly for marked discourse operators:

`仍` / `仍然` / `依然` / `仍旧`
`却` / `但` / `但是` / `然而` / `不过`
`虽然……但是……` / `尽管……仍……` / `即使……也……`
`尽管如此` / `即便如此` / `话虽如此`
`确实` / `的确` / `诚然` / correctional `其实` / `事实上`

For `仍/依然`, require an explicit prior baseline, challenge, predicted change, or task about persistence. For `却/但/然而`, require a concrete counterexpectation or comparison. For `确实/诚然/其实/事实上` used to reaffirm or correct, require an actual doubt or competing claim. Otherwise delete the marker and state the proposition directly.

Also reduce generic progression markers and automatic interpretation phrases when they merely organize or inflate the answer. For Chinese prose, scan for overt *and implied* abstract agency, `它` referring to an abstract object, overused abstract `其`, bare `这`/`这一点` as abstract referents, explicit subject-pronoun repetition, heavy `的` chains, source-driven passives, causative calques, preposition stacks, and over-explicit cohesion. See `references/chinese-translationese.md`.

For every authored Chinese sentence, prohibit a change to a second subject unless a genuine semicolon boundary is licensed. In longer paragraphs, actively avoid consecutive short declarative sentences when natural same-subject integration would convey the same information. When the text spans multiple sentences, check their logical order and what each adds. After sentence insertion or deletion, test the resulting paragraph again. See `references/chinese-sentence-coherence.md`.

### English

Run a strict scan for `not X but Y`, `not just`, `not merely`, `rather than`, `less X than Y`, `doesn't mean`, `far from`, and `by no means` used as corrective setup.

Default repair: state the supported proposition directly. Require an external exact anchor before retaining the corrective frame.

Also scan `still`, `remain`, `continue to`, `yet`, `however`, `nevertheless`, `nonetheless`, `even so`, `although`, `despite`, and corrective `actually/in fact/indeed`. Require a real temporal baseline, challenge, comparison, or counterexpectation before keeping the marked form.

### Japanese

Treat `単なるXではなくY`, `Xというわけではない`, `Xを意味するものではない` and equivalent corrective negatives with the same external-antecedent rule.

### Romance languages

Apply the same rule to constructions such as `no se trata de`, `no solo ... sino`, `ce n'est pas ... mais`, and `non si tratta di` when they function as corrective contrast.

## Exceptions and precedence

- Preserve quoted text, citations, source excerpts, fixed strings, code, equations, and faithful translation where fidelity requires the original wording.
- Follow an explicit user request for a rhetorical style that intentionally uses contrast.
- Preserve technical, legal, scientific, or literary constructions when accuracy or genre requires them.
- Accuracy and safety outrank stylistic suppression.

The goal is to stop the model from manufacturing a proposition solely so it can deny that proposition and sound more insightful.
