---
layout: post
title: Routing with Road Conditions
---

This project will prototype a routing service that incorporates road surface
quality into recommendations. The core feature will be a machine learning (ML)
model that classifies route segments as paved or unpaved using sensor data that
would plausibly be available in a production setting (e.g., crowdsourced mobile
phone accelerometer data, Google Street View imagery).


## Background

Google Maps is useful for driving directions. It integrates critical travel
information such as distance, drive times, and traffic. However, the application
does not present information about the quality of driving surfaces. These
details are important to plan safe trips for vehicles and passengers.

Although users have [requested][1] road surface information to inform trip
planning, the feature does not yet appear to be available. Google's subsidiary
trip planning company Waze does offer [surface-informed][2] routing, presumably
powered by crowd-sourced travel information. Road classification powered by
machine learning could extend or quality control these existing capabilities.


## Outcomes

This project **prototype a ML algorithm** that classifies road segments as paved
or unpaved. The model will train on labeled sensor data collected while
traveling on paved and unpaved roads.

The project will also **demonstrate model application**, showing how road
surface predictions could inform a user through a trip planning interface. This
part of the project will be intentionally simplistic; the goal is to clearly
prove a concept, not to reinvent a production routing algorithm.


## Approach

### ML Algorithm

The ML algorithm will classify road segment samples as either paved or unpaved.
Depending on literature insights and available data, these samples may be:

- Street-level images similar to those from [Google Street View][3].
- Satellite images of specific identified roads.
- Mobile phone accelerometer data gathered during driving.
- User deviations from routing instructions occuring on specific roads.

Each of these data sources should be available to tech companies like Google
that might productionize a prototype like this one, enabling those companies
both to maintain classification models and apply them to many of the roads that
users want to travel.

I will add details about specific data sources and algorithms during the
research phase for this project. Possible data sources include:

- [Road surface images][4]

### Application

The application will incorporate the ML algorithm into a simple routing user
interface. The interface will include a small, handmade network of nodes and
edges to represent a production road network. Powered [NetworkX][5] or similar,
the interface will enable users to select two points and see the shortest route.

The mock road network will include some paved and unpaved segments, each with
data points (e.g., road images) to be interpreted by the algorithm. Some
segments could also be missing data, presenting an opportunity to show how
interpolation of road surfaces could work. On the back end, the application will
classify each segment using avaiable data, caching results for quick use.

The application can incorporate surface conditions into routing instructions in
various ways:

- Weight road segments based on a combination of distance and quality.
- Present a "smoothest ride" option that minimizes unpaved distance.
- Show unpaved road segments in a different color.
- Summarize route conditions (e.g., x miles of unpaved road).

As previously mentioned, the goal of this application is to demonstrate the
value of the ML algorithm, not to optimize the routing experience for users.


## Work Phases

### Phase 1: Research (__ weeks)

Gather key information to gauge viability and outline approach.

- Review literature on road classification.
- Identify candidate datasets to inform models.
- Research appropriate machine learning methods.
- Research the technical stack to implement models.
- Research packages for a no-frills routing demonstration.

### Phase 2: Explore Data (__ weeks)

Familiarize with data to enable effective modeling.

- Divide data into training and testing sets.
- Identify key assumptions and questions about data.
- Explore data to address assumptions and questions.
- Develop infrastructure for data cleaning and enrichment.
- Document initial findings.

### Phase 3: Create Application (__ weeks)

Create a simple, end-to-end solution that can accept model results.

- Outline a minimum viable product (MVP) to demonstrate routing.
- Prototype the MVP, focusing on core challenges and model integration.
- Develop rough visuals to show how the application works.

### Phase 4: Create Model (__ weeks)

Iteratively develop a classification algorithm.

- Establish metrics for evaluating models.
- Identify features of interest, and brainstorm implementations.
- Extract features from training data.
- Create and evaluate a baseline heuristic.
- Iteratively train and evaluate models.

### Phase 5: Present Results (__ weeks)

Enable users and developers to engage with project results.

- Clean up project organization and documentation.
- Refine key visualiations for storytelling.
- Write a blog post summarizing results.


<!-- References -->

[1]: https://support.google.com/maps/thread/2292860/how-do-i-avoid-dirt-roads?hl=en
[2]: https://support.google.com/waze/answer/7666302?hl=en
[3]: https://www.google.com/streetview/
[4]: https://www.sciencedirect.com/science/article/pii/S2352340922002347
[5]: https://networkx.org/documentation/stable/index.html