# Sourcing Analysis with AI — CloudWalk Technical Challenge

**Author:** Letícia Saraiva  
**Role:** Talent Acquisition Specialist  
**Context:** Sourcing Analysis with AI

---

## Overview

This project presents a Talent Acquisition and People Analytics analysis of a fictional sourcing and recruitment dataset containing **601 candidates**, covering the full hiring funnel from sourcing to hire.

The goal was to surface actionable insights for recruiters by answering key questions:

- Which sourcing strategies convert better?
- Which signals indicate a higher probability of moving forward in the process?
- When is it worth persisting with a candidate?
- When is the probability of conversion low?
- Are there relevant patterns across channels, recruiters, or candidate profiles?

AI was used as an analytical support tool throughout — to structure the problem, validate the analytical approach, explore funnel and conversion patterns, identify correlations between variables, summarize recruiter notes, and translate data findings into clear recommendations. All conclusions were grounded in the dataset itself, with attention to sample size, data quality, and limitations.

---

## Recruitment Funnel Analysis

| Stage | Candidates | Cumulative Conversion | Step-by-Step Conversion |
|---|---|---|---|
| Sourced | 601 | 100.0% | — |
| Responded | 408 | 67.9% | 67.9% |
| Passed Screening | 308 | 51.2% | 75.5% |
| Passed Interview | 234 | 38.9% | 76.0% |
| Test Taken | 201 | 33.4% | 85.9% |
| **Offer Sent** | **62** | **10.3%** | **30.8% ⚠️** |
| Hired | 49 | 8.2% | 79.0% |

**Main bottleneck:** The biggest efficiency issue happens after the technical test — 69.2% of candidates who completed it did not receive an offer. This may indicate misalignment between the test, hiring criteria, leadership expectations, or the quality of candidates reaching that stage.

---

## Conversion by Source Channel

| Channel | Candidates | Hire Rate |
|---|---|---|
| **Github** | 73 | **11.0%** ✅ |
| **Inbound** | 69 | **10.1%** ✅ |
| **Hunting** | 75 | **9.3%** ✅ |
| Talent Pool | 68 | 8.8% |
| LinkedIn | 81 | 8.6% |
| Community | 89 | 7.9% |
| Event | 82 | 4.9% ⚠️ |
| Referral | 64 | 4.7% ⚠️ |

**Recommendation:** Increase sourcing efforts on Github, Inbound, and Hunting. Review quality and entry criteria for Event and Referral candidates.

---

## Conversion by Seniority

| Level | Candidates | Hire Rate |
|---|---|---|
| Junior | 109 | 4.6% |
| Mid-level | 228 | 7.0% |
| Senior | 204 | 9.8% |
| Staff | 60 | 13.3% |

**Insight:** The higher the seniority, the higher the conversion. Staff and Senior candidates performed best; Junior candidates had relatively high volume but low conversion.

---

## Conversion by Work Mode

| Work Mode | Candidates | Hire Rate |
|---|---|---|
| Remote | 201 | 5.0% |
| **Hybrid** | 185 | **10.8%** ✅ |
| On-site | 215 | 8.8% |

**Insight:** Hybrid roles converted significantly better. Remote roles had high candidate volume but lower conversion, possibly due to higher competition, expectation misalignment, or stricter hiring criteria.

---

## Conversion by Recruiter

| Recruiter | Candidates | Hire Rate |
|---|---|---|
| **Bruno** | 98 | **15.3%** ✅ |
| **Ana** | 75 | **13.3%** ✅ |
| Carla | 101 | 8.9% |
| Gustavo | 121 | 5.0% |
| Diego | 103 | 4.9% |
| Fernanda | 103 | 3.9% |
| **Overall Average** | 601 | **8.2%** |

**Insight:** Bruno and Ana performed well above average. Ana maintained a more effective intermediate funnel — 66.7% of her candidates passed screening and 54.7% reached the interview stage. Diego and Fernanda had high candidate volumes but low offer and hire rates.

---

## Predictive Signals for Hiring

| Score | Best-performing Range | Insight |
|---|---|---|
| Technical Test | 80–100 | 80–89 range: 13.3% hire rate; 90–100: 13.6% |
| Manager Score | 90–100 | 17.3% hire rate (9 hires out of 52 candidates) |
| Behavior Score | 80–89 | 15.5% hire rate (22 hires out of 142 candidates) |

**Practical insight:** The strongest candidates tend to show balance across technical, behavioral, and manager evaluations.

---

## "Worth Persisting" vs. "Low Probability" Profiles

### ✅ Profile 1 — Worth Persisting

Common characteristics:
- Slower response, but strong later-stage scores
- Technical score above 75
- Behavior or manager score compensates for one weaker dimension
- Notes mention autonomy, good communication, role fit, or potential
- Senior or Staff level, especially in Tech
- Stronger source channels: Github, Inbound, and Hunting

**Decision rules:**

| Criterion | Rule |
|---|---|
| Slow response | Persist if the candidate responded within 10–12 days and has Senior/Staff seniority or strong experience |
| One weaker score | Persist if only one score is below 70, but the other two are above 75 |
| High salary expectation | Persist if technical and manager scores are above 80 and the role has compensation flexibility |
| Neutral notes | Persist if there is mention of solid experience, autonomy, or fit with the role context |

**Simple rule:** Persist when the candidate has at least two strong signals among: high technical score, high manager score, seniority, strong source channel, or positive notes indicating role fit.

---

### ⚠️ Profile 2 — Low Probability of Conversion

Common characteristics:
- No response or very slow response without clear interest
- Low technical fit already at screening stage
- Technical score below 70
- Manager score below 70 without behavioral or technical compensation
- Lower-converting channels: Event and Referral
- Remote roles, which showed lower conversion in this dataset
- Frequent rejection reasons: No response, Failed technical test, Timing mismatch, Low technical fit

**Decision rules:**

| Criterion | Rule |
|---|---|
| No response | After a defined number of follow-ups, deprioritize and move to new candidates ("No response" appeared 210 times) |
| Technical score < 70 | Very low or no conversion below this threshold |
| Manager score < 70 | Very low conversion: 2 hires out of 132 candidates in the 60–69 range |
| Low-efficiency channel | Reduce effort on Event/Referral unless additional pre-qualification is added |

**Simple rule:** Deprioritize when the candidate combines low responsiveness + technical/manager score below 70 + no positive signal in recruiter notes.

---

## Prioritized Recommendations

| # | Context | Supporting Data | Recommended Action |
|---|---|---|---|
| 1 | Biggest bottleneck after the test | 201 took the test; only 62 received offers (69.2% drop-off) | Review test criteria and calibrate expectations with Hiring Managers before applying tests at scale |
| 2 | Github is the best-converting channel | 8 hires / 73 candidates — 11.0% | Increase active sourcing on Github, especially for Tech/Data roles |
| 3 | Inbound has the best response rate | 79.7% responded; 10.1% hire rate | Improve inbound screening and create a fast response SLA |
| 4 | Events generate volume but low output | 82 candidates, 4 hires — 4.9% | Use events for employer branding and long-term pipeline rather than immediate hiring goals |
| 5 | Referrals underperformed | 64 candidates, 3 hires — 4.7% | Define minimum referral qualification criteria before candidates enter the funnel |
| 6 | Staff and Senior candidates convert better | Staff 13.3%; Senior 9.8%; Junior 4.6% | Prioritize consultative sourcing for senior roles and recalibrate Junior role criteria |
| 7 | Hybrid roles convert better than remote | Hybrid 10.8% vs. Remote 5.0% | Investigate whether remote roles have higher competition, salary misalignment, or stricter hiring bars |
| 8 | Bruno and Ana show stronger performance | Bruno 15.3%; Ana 13.3% vs. 8.2% average | Map their sourcing and screening practices and turn them into a team playbook |
| 9 | Diego, Fernanda, Gustavo have high volume but lower conversion | Diego 4.9%, Fernanda 3.9%, Gustavo 5.0% | Review channel mix, role complexity, and criteria for advancing candidates |
| 10 | Technical score below 70 rarely converts | Very low or no conversion below this threshold | Use technical score as a strong prioritization criterion after the test stage |
| 11 | High manager score differentiates finalists | 90–100 range had 17.3% conversion | Strengthen calibration with managers on what defines high potential |
| 12 | Rejection reason data is incomplete | 226 records had no rejection reason | Make rejection reason mandatory to improve future funnel diagnostics |

---

## Final Conclusion

The overall end-to-end conversion rate was **8.2%**. The main bottleneck was the **Test Taken → Offer Sent** stage, indicating that the team should review the technical assessment process and hiring manager calibration.

The strongest sourcing channels were **Github, Inbound, and Hunting**, while Event and Referral generated weaker hiring outcomes. The profiles with the highest conversion were **Staff and Senior candidates**, especially for Tech roles and hybrid work models.

AI was used to accelerate and structure the analysis, helping transform raw recruitment data into funnel metrics, predictive signals, segmentation criteria, data quality checks, and actionable recommendations.

---

## Tools & Methods

- People Analytics & funnel analysis
- Conversion rate segmentation by channel, seniority, work mode, and recruiter
- Predictive signal identification (score thresholds)
- Candidate profile classification (persist vs. deprioritize)
- AI-assisted analysis (structuring, pattern recognition, summarization)
- Executive presentation design

---

*This analysis was developed as part of a technical challenge for a Talent Acquisition Specialist role.*
