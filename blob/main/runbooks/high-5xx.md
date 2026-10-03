# Runbook: High 5xx Error Rate

## Alert

- GoWebAppHigh5xxRate
- GoWebAppAvailabilitySLOBurnCritical
- GoWebAppPodsNotReady

## Impact

The Go web application is returning an elevated number of
HTTP 5xx responses.

This can indicate:

- application failure
- bad deployment
- container restart
- readiness/liveness failure
- insufficient resources
- dependency failure
- node-level issues

## Step 1 — Confirm the alert

Check the alert in Prometheus:

```promql
go_web_app:error_ratio_5m
