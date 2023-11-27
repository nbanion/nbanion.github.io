---
layout: post
title: Routing with Road Conditions
---
- Google maps is useful
- Routing does not consider road condition
- Causes problems: unsafe conditions, wear on car
- Folks asking for solutions; none implemented yet


## Outcomes

- A **prototype.**
- Given a segment of road, predict quality.
- Incorporate quality metrics into weights for routing.


## Approach

- Score road segments based on observed quality.
- Where data are missing, interpolate from surroundings.
- Show road conditions to the user (e.g., color routes).
- Summarize conditions by route (e.g., x miles of bad road).
- Enable users to select "smoothest ride" among reasonable options.
- Need to understand basics of Google routing.
- Need to document existing requests and work.
- Could use street view images to count potholes.
- Could use satellite images to assess quality.
- Could analyze roads chosen / avoided by users.
- Could analyze deviations from routing directions.
- Could eventually consider seasonal variation.
- Ideally present a working routing algorithm.
- Also consider an illustrative example.
- Avoid the weeds of route optimization-- farm it out!


## Work Phases

- 