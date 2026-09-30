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

<img src="/assets/img/research/research-vision.png" alt="계측으로 갱신되는 구조물 수명 예측기: (1) 확률적 구조 모델, (2) 모델 오차를 아는 대리모델, (3) 신뢰성 기반 수명 예측과 갱신" style="display: block; margin: 1.5rem auto 2rem auto; max-width: 100%; height: auto;">

#### Why a Life Forecast, and Why Now

The remaining life of a structure is not a number; it is a distribution. A single figure — "30 years left" — hides exactly what an owner needs in order to act: how wide the answer is, what would narrow it, and what would change it. Decisions about repair, replacement and continued use are decisions taken under uncertainty, and they are better taken from the distribution than from its mean.

Structures are measured more thoroughly every year — fixed sensors, drones, inspection robots, nondestructive testing — yet the estimated remaining life barely moves in response. The bottleneck is not the volume of data but the model that receives it. A model whose deterioration, response and own error are not represented probabilistically has nowhere to put a new measurement, so the measurement changes nothing. Weather forecasting solved a structurally similar problem by combining physics, continuous data assimilation and — decisively — the routine scoring of its own forecasts against what subsequently occurred. Structural engineering now has the mechanics, the measurements and the machine learning; what it does not yet have is the loop that closes them.

My work is to build that loop, and the three axes below are its three pieces.

#### Axis 1 — Probabilistic Models of Deteriorating Structures

계측 정보를 담을 수 있는 확률적 정밀 구조 모델(열화·응답) 구축

- **Question** — How much capacity has a corroded prestressed girder actually lost, and how uncertain is that answer?
- **Approach** — Deterioration and response models in which material properties, deterioration rates and model-form error are random variables rather than fixed assumptions, so that a measurement has somewhere to go.
- **Output** — Posterior distributions of structural state; partial safety factors calibrated for aged structures and for new low-carbon materials entering design practice.

#### Axis 2 — Surrogate Models That Know Their Own Error

자기 오차를 아는 확률적 인공지능 대리모델

- **Question** — When may a neural surrogate replace a structural analysis, and when must it admit that it cannot and call one?
- **Approach** — Physics priors combined with operator learning (e.g., FNO); predictive intervals that widen outside the training range instead of extrapolating confidently; active learning that spends additional structural analyses where the model is least certain.
- **Output** — Fast response prediction with honest intervals, and virtual sensing at locations no instrument reaches.

#### Axis 3 — Reliability-Based Life Prediction, Updated in Real Time

신뢰성 기반 구조물 수명 예측·실시간 갱신 및 예측 검증

- **Question** — Given everything measured so far, how much longer can this structure be used safely, and what should be measured next?
- **Approach** — Safety lifetime defined as $$T = \min\{\,t : \beta(t) \le \beta_\mathrm{target}\,\}$$, updated by Bayesian inference as data arrives; value of information to decide which measurement is worth taking; verification of the forecasts against what is subsequently observed.
- **Output** — A life distribution that narrows with each measurement and widens honestly after an earthquake or another surprise; inspection priorities; measurement plans.

#### From Probability to Decision

A probabilistic answer is only useful if it ends in a decision. Every result is therefore expressed in units an owner can act on — a reliability index against a target, a distribution of remaining life, a ranked inspection list, the value of a proposed measurement — rather than in a probability that leaves the judgement to someone else.

#### Verification

Sharpness is easy to claim and easy to fake; it only counts once calibration has been demonstrated. Across all three axes, the fraction of observations that actually fall inside the predicted intervals is treated as a standard reported quantity, not an afterthought. Each prediction is settled by the observations that arrive after it, so the record of how well the forecasts have held accumulates at the pace of the measurements rather than being asserted once.
