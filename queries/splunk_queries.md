# Splunk Queries

## View All Events

```spl
index=main
```

---

## Windows Security Events

```spl
index=main sourcetype=WinEventLog:Security
```

---

## Authentication Events

```spl
index=main EventCode=4624
```

Purpose:
View successful logon events.

---

## Failed Login Events

```spl
index=main EventCode=4625
```

Purpose:
Identify failed authentication attempts.

---

## Account Lockout Events

```spl
index=main EventCode=4740
```

Purpose:
Detect locked user accounts.

---

## Logon Activity

```spl
index=main EventCode=4624 OR EventCode=4625
```

Purpose:
Review authentication activity.

---

## Search by Username

```spl
index=main user=<username>
```

Purpose:
Investigate activity related to a specific user.

---

## Event Count

```spl
index=main
| stats count by EventCode
```

Purpose:
Summarize event frequency.

---

## Top Event Sources

```spl
index=main
| top source
```

Purpose:
Identify major log sources.

---

## Time-based Analysis

```spl
index=main
| timechart span=1h count
```

Purpose:
Visualize event trends over time.
