# Cisco Study Vault — Master MOC

## Courses

| Course            | Provider | Status | Notes                     |
| ----------------- | -------- | ------ | ------------------------- |
| Networking Basics | NetAcad  | 🟡     | [[Networking Basics MOC]] |

## All Courses Progress

```dataview
TABLE length(rows) AS "Notes"
FROM "Cisco Notes/01 - Courses"
WHERE course != "Template"
GROUP BY course
```

## All Labs

```dataview
TABLE course, module
FROM "Cisco Notes/02 - Labs"
WHERE course != "Template"
```

## All Commands

```dataview
TABLE course, purpose
FROM "Cisco Notes/03 - Commands"
WHERE type != "Command Template"
```


