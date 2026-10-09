---
layout: page
permalink: /research-interest/
title: research vision
description: "관심 연구 주제: 계측 정보 축적으로 정밀화되는 구조물 수명 예측기 개발"
nav: true
nav_order: 2
---

<div class="vision">
  <p class="vision-ko">계측할수록 정밀해지고, 예상을 벗어난 사건이 발생하면 불확실성이 커지며, 지난 예측이 다음 계측으로 자가 검증되는 확률적 수명 예측.</p>
  <p class="vision-en">A probabilistic life prediction that grows more precise with every measurement, widens its uncertainty when an unforeseen event occurs, and checks each prediction against the measurements that follow.</p>
</div>

<img src="/assets/img/research/research-vision.png" alt="계측으로 갱신되는 구조물 수명 예측기: (1) 불확실성을 고려한 디지털 트윈, (2) 실측-구조해석 불일치를 학습하는 확률적 대리모델, (3) 신뢰성 기반 수명 예측·갱신·검증, (4) 정보가치 기반 추가 계측 의사결정" style="display: block; margin: 1.5rem auto 2rem auto; max-width: 100%; height: auto;">

#### A Translator from Measurements to Remaining Life

Sensors are becoming cheap and continuous, and the state of a structure now arrives as thousands of values a day. What has not kept pace is the machinery that turns those values into a judgement: whether the structure may continue in service, and for how long. That judgement is still made the way it was made before the data existed — periodically, from a single representative number, by inspection.

What is missing is a translator. It takes measured state — crack widths, corrosion rates, displacements, accelerations — and converts it into performance, meaning capacity and probability of failure; then it converts the trajectory of that performance into remaining life. The translator has three places where it can be wrong, and each carries its own uncertainty: the measurement that enters it, the model that transforms it, and the judgement that leaves it. The four axes below each take responsibility for one of those, and the fourth closes the loop by deciding what to measure next.

The honest statement of the goal is not that the remaining life of a structure can be predicted. It is that the distribution of remaining life can be narrowed by measurement, and that the narrowing can be checked.

#### Axis 1 — Uncertainty-Aware Digital Twins of Structures

불확실성을 고려한 디지털 트윈 구축 기술 개발

- **Question** — A sensor returns a distribution, not a number. If capacity is computed anew thousands of times a day, which value is the structure's capacity — the lowest, the mean, the most recent?
- **Approach** — A digital twin in which material properties, deterioration rates, model-form error and the measurement uncertainty of each instrument are all random variables, so that a reading has somewhere to go. Conformity is then assessed the way metrology assesses it: not by comparing a representative value against a criterion, but by tracking the probability of falling short of it over time.
- **Output** — Structural state and capacity as posterior distributions, each reported together with the size of the uncertainty behind it.

#### Axis 2 — Probabilistic AI Surrogates Built on the Measurement–Analysis Discrepancy

실측−구조해석 불일치 정보 기반 확률적 인공지능 구조해석 대리모델 구축 기술 개발

- **Question** — When a measurement and a structural analysis disagree, which one is wrong, and by how much? Model updating adjusts parameters inside a model assumed to be structurally correct; it cannot represent a mechanism the model does not contain.
- **Approach** — A surrogate that learns the discrepancy itself rather than only reproducing the analysis: physics priors combined with operator learning, predictive intervals that widen beyond the measured range instead of extrapolating confidently, and a network structure whose learned kernels can be read as transfer functions, so that the discrepancy is a physical quantity rather than a black-box correction.
- **Output** — Fast response prediction with honest intervals, virtual sensing where no instrument reaches, and a model bias that is quantified and propagated into the probability of failure instead of being absorbed silently.

#### Axis 3 — Reliability-Based Prediction, Updating and Verification of Structural Life

신뢰성 기반의 구조물 수명 예측·갱신·검증 기술 개발

- **Question** — Given everything measured so far, when is a decision forced? The useful question is not when a structure will collapse but when its reliability falls below target, so that inspection or repair can no longer be deferred.
- **Approach** — Safety lifetime defined as $$T = \min\{\,t : \beta(t) \le \beta_\mathrm{target}\,\}$$, with deterioration treated as a stochastic process whose parameters are updated by Bayesian inference as data arrives, and with every forecast later scored against what was actually observed.
- **Output** — A life distribution that narrows with each measurement and widens honestly after an earthquake or another surprise; and, from it, inspection intervals set by the measurements rather than by a fixed calendar.

#### Axis 4 — Value-of-Information Decisions for Autonomous Measurement

피지컬 AI 자율 계측을 위한 정보가치 기반 의사결정 기술 개발

- **Question** — When the remaining uncertainty is too large to decide, what should be measured next, and where? A robot is sent out for two reasons: because the judgement is too uncertain, or because an alarm has been raised and must be confirmed.
- **Approach** — Value of information: how much a candidate measurement would reduce the uncertainty that actually changes the decision, weighed against what it costs. This requires separating the uncertainty a measurement can reduce from the model uncertainty it cannot — which is what Axis 2 supplies. Continuous low-cost sensing screens; a robot's high-precision nondestructive testing confirms.
- **Output** — An instruction naming what to measure and where, an updated judgement, and a diagnosis of each false alarm that feeds back into the model so the next one is less likely.

#### From Probability to Decision

A probabilistic answer is only useful if it ends in a decision. Every result is therefore expressed in units an owner can act on — a reliability index against a target, a distribution of remaining life, a ranked inspection list, the value of a proposed measurement — rather than in a probability that leaves the judgement to someone else.

#### Verification

A probability of failure of 10⁻⁴ to 10⁻⁶ cannot be checked against observed failures; the events are too rare. So the claim is not that the failure probability is correct. It is that each link in the chain leading to it is verified by evidence appropriate to that link, and that the point at which the chain begins to extrapolate is stated rather than hidden.

Sensor uncertainty is checked against reference instruments. Predicted capacity distributions are checked against specimens tested to failure. A learned discrepancy is checked on structures whose damage is known because it was introduced deliberately, and then again outside the range it was trained on. The computation itself is checked against Monte Carlo. What is reported is coverage of the predicted intervals, continuous ranked probability score, and the flatness of the probability integral transform — and verification, meaning the mathematics was solved correctly, is kept distinct from validation, meaning the result agrees with the world.
