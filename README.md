# P1 Pilot Tracker: real-time raw material availability (PPG Shildon)

A simple tool for running the **P1 pilot** described in the *Raw Material Visibility Proposal*.
It is one HTML file. There is nothing to install and no server. Open `p1-pilot-tracker.html` in Edge or Chrome on the cell PC or tablet.

## The problem it supports
Material is pre-charged into a batch, but production admin only down-dates it in Oracle 2–4 days later.
Until then Oracle still shows that material as available, so new batches are planned against stock that has already been used.

**Pilot fix:** at pre-charge, the operator RF-transfers the material from `SEAL PROD` to a `P1` locator that is excluded from planning.
Admin later down-dates from P1 with the batch/lot reference.
This tracker is the paper trail and scoreboard for that process.

## Tabs
| Tab | Who | What |
|---|---|---|
| 1. Pre-charge | Operator | Log each charge: item, lot, qty (kg/drum), batch, and whether the RF transfer to P1 was done. Answering "No" to the RF question logs an exception automatically. |
| 2. Awaiting admin issue | Production admin | Everything in P1 that still needs down-dating, oldest first and colour-coded by age (green <24h, amber 24–48h, red >48h). Click **Down-dated**, **Partial** or **Reverse**. Also shows the P1 balance per item. |
| 3. Daily reconciliation | Cell leader / admin | Enter what Oracle shows in P1 for each item. Variances are calculated and logged as exceptions automatically. |
| 4. Exceptions | Anyone | Missed RF transfers, wrong qty or lot, cancellations, "stock not found" and batch delays, with minutes lost. |
| 5. KPIs | Sponsor | Avg charge → down-date time, % down-dated within 24h, RF compliance, exceptions, delays, operator time study and a weekly summary, compared with your baseline. These map to the five measures on slide 6. |
| 6. Pilot gates | Sponsor | Checklist of every gate in the proposal: Prepare → Validate → Approve (Oracle, supply chain, production admin, Quality) → 4-week pilot → Decide. Each tick records who confirmed it and when. |
| Data / backup | Owner | CSV exports for Excel, plus full JSON backup and restore. |

## Important
- **Data stays in the browser on the device you use.** Use one agreed PC for the pilot and download a JSON backup to the shared drive every day.
- Click **Load demo data** to try it out, then **Clear all data** before you go live.
- The tracker does not connect to Oracle. It is a parallel log to prove (or disprove) the process during the pilot.
- No live change to the process until the decision gate on the *Pilot gates* tab is signed off.

## Suggested daily routine (draft SOP)
1. **Operator, at pre-charge:** RF transfer SEAL PROD → P1 (item, lot, qty), then log it on tab 1.
2. **Admin, when the batch is processed:** down-date from P1 in Oracle with the batch/lot reference, then click **Down-dated** on tab 2.
3. **End of shift:** check tab 2 for red (>48h) lines and chase them.
4. **Once a day:** run the P1 on-hand query in Oracle and complete tab 3.
5. **Weekly:** review tab 5 with the sponsor, export the CSVs and tick the week's review on tab 6.

---

# ATHX Lite Plan tracker

`athx-tracker.html` is a phone-first app for logging the 16-week ATHX beginner (Lite) plan from start to race day.
Open it in a browser, or use the published Claude artifact version, which saves your log to your claude.ai account.

- **Today**: week and day picker, weekly summary (sessions, time, kg lifted, PRs, run and ski/row km) and the day's workout. Open it to log sets (kg, reps, tick), times, distances and notes, start a session timer and finish with an RPE.
- **Progress**: sessions done, top set per week for squat, press and deadlift, benchmarks (3RMs, 3km time trial, best zone ski) and the full plan grid.
- **Profile**: start date, 12-week option (skips weeks 2-3 and 6-7), week 8 3RMs that drive the % targets from week 9, adjustment rules and a copy/paste backup.
