# Custom tracker rule format

TrackMe AI can be extended with local rule definitions.

Example:

```text
NAME: pushups
WHEN: elbow_angle < 105
THEN: phase = DOWN
WHEN: phase == DOWN AND elbow_angle > 155
THEN: count += 1
```

Study example:

```text
NAME: study
WHEN: person_present AND seated_at_desk
THEN: focused_time += frame_delta
WHEN: NOT person_present
THEN: away_time += frame_delta
```

These rules operate on measurable camera signals. They should not claim to know a user's thoughts or intentions.
