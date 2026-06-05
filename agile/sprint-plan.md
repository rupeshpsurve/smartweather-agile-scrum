# Sprint Plan — Sprint 1
### SmartWeather Analytics Platform | Agile Scrum Delivery

---

## 📌 Purpose

This document captures the Sprint 1 plan for the SmartWeather Analytics platform, 
including sprint goal, committed user stories, story point allocation, team capacity, 
and daily stand-up notes.

---

## 🎯 Sprint 1 Details

| Item | Detail |
|---|---|
| **Sprint Number** | Sprint 1 of 3 |
| **Sprint Goal** | Deliver core data ingestion capability and tourism analytics foundation |
| **Sprint Duration** | 2 weeks |
| **Start Date** | Week 1 |
| **End Date** | Week 2 |
| **Team Capacity** | 40 story points |
| **Committed Points** | 37 story points |

---

## 📋 Sprint 1 — Committed Stories

| Story ID | User Story | Epic | Points | Status |
|---|---|---|---|---|
| US-001 | Connect to multiple weather API sources | EP-01 Data Ingestion | 8 | ✅ Done |
| US-002 | Weather data refreshed at regular intervals | EP-01 Data Ingestion | 5 | ✅ Done |
| US-003 | Failed API connections trigger alert | EP-01 Data Ingestion | 3 | ✅ Done |
| US-004 | Seasonal weather forecasts for tourism destinations | EP-02 Tourism | 8 | ✅ Done |
| US-005 | Compare weather patterns across destinations | EP-02 Tourism | 5 | ✅ Done |
| US-010 | Central dashboard for weather analytics | EP-05 Platform | 5 | ✅ Done |
| US-011 | Export dashboard data to Excel | EP-05 Platform | 3 | ✅ Done |

**Total committed: 37 points | Completed: 37 points | Velocity: 37**

---

## 📅 Sprint Planning Notes

**Sprint Goal agreed by team:**
> "By the end of Sprint 1, users can connect to multiple weather data sources, 
> view refreshed data on a central dashboard, and access tourism seasonal 
> forecasts — with automated alerts for data source failures."

**Key decisions made during planning:**
- US-005 (destination comparison) included in Sprint 1 as team had capacity
- US-006 (healthcare risk indicators) deferred to Sprint 2 — dependency on data ingestion
- Story point estimates agreed using Planning Poker
- Definition of Done confirmed: developed, tested, reviewed, and demo-ready

**Definition of Done:**
- [ ] Acceptance criteria met and verified
- [ ] Unit tested by developer
- [ ] Reviewed by BA (Rupesh Surve)
- [ ] Demo-ready for sprint review
- [ ] Confluence documentation updated

---

## 📊 Daily Stand-up Log

| Day | Progress | Blockers | Actions |
|---|---|---|---|
| Day 1 | Team onboarded; Jira board configured; US-001 in progress | API credentials not yet received from vendor | Rupesh chased vendor — credentials received Day 2 |
| Day 2 | API credentials received; US-001 development started | None | — |
| Day 3 | US-001 50% complete; US-002 started | API rate limiting higher than documented | Raised with vendor; workaround agreed |
| Day 4 | US-001 complete; US-002 75% complete | None | — |
| Day 5 | US-001, US-002 done; US-003 started | None | — |
| Day 6 | US-003 complete; US-004 started | Weather forecast API returning inconsistent date formats | BA documented issue; dev applied normalisation logic |
| Day 7 | US-004 75% complete; US-010 started | None | — |
| Day 8 | US-004 complete; US-010, US-011 in progress | None | — |
| Day 9 | US-010, US-011 complete; US-005 started | None | — |
| Day 10 | All stories complete; sprint review prep | None | — |

---

## 📈 Sprint Burndown

| Day | Remaining Points |
|---|---|
| Day 0 (start) | 37 |
| Day 2 | 34 |
| Day 4 | 26 |
| Day 6 | 18 |
| Day 8 | 10 |
| Day 10 (end) | 0 |

**Result: Sprint completed on time — all 37 story points delivered ✅**

---

## 🔄 Sprint Review Summary

**Date:** End of Week 2
**Attendees:** Product Owner, BA (Rupesh Surve), Development Team, Stakeholders

**Demos completed:**
- ✅ Live weather data ingestion from 2 API sources demonstrated
- ✅ Automated alert triggered for simulated API failure
- ✅ Tourism seasonal forecast dashboard demonstrated for 3 destinations
- ✅ Destination comparison view demonstrated
- ✅ Central dashboard with Excel export demonstrated

**Stakeholder feedback:**
- Tourism forecast well received — stakeholders requested daily email digest (added to backlog)
- Dashboard load time acceptable — target < 5 seconds met
- Request to add healthcare risk indicators sooner — prioritised for Sprint 2

**Stories accepted by Product Owner:** 7 of 7 ✅

---

## 🔁 Sprint Retrospective Summary

**What went well:**
- All stories delivered on time — strong team collaboration
- Blocker (API credentials) resolved quickly through proactive stakeholder chasing
- Daily stand-ups kept team aligned and blockers surfaced early

**What could be improved:**
- API documentation from vendor should be reviewed earlier to catch issues before sprint start
- Story point estimates for API-related stories should include a buffer for vendor dependency risk

**Actions agreed:**
| Action | Owner | Due |
|---|---|---|
| Review all Sprint 2 API dependencies before sprint start | Rupesh Surve | Sprint 2 Day 1 |
| Add 20% buffer to story points for vendor-dependent stories | Scrum Master | Sprint 2 Planning |
| Chase vendor for Sprint 2 API documentation 1 week early | Rupesh Surve | Before Sprint 2 |

---

## 🗺️ Release Roadmap

| Sprint | Focus | Key Deliverables |
|---|---|---|
| Sprint 1 ✅ | Data Ingestion + Tourism | Weather APIs, central dashboard, tourism forecasts |
| Sprint 2 | Healthcare + Retail Foundation | Health risk indicators, retail demand forecasting |
| Sprint 3 | Retail Advanced + Platform | Promotion planning, advanced reporting, platform hardening |

---

## 📁 Related Documents

- [User Stories](./user-stories.md)
- [Retrospective Notes](./retrospective-notes.md)
- [KPI Definitions](../analytics/kpi-definitions.md)

---

*Produced by Rupesh Surve | Business Analyst | Part of SmartWeather Agile Scrum Portfolio*
