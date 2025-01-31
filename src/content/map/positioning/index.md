---
title: User Positioning
eleventyNavigation:
  parent: map
  title: User Positioning
  key: map-positioning
  order: 60
---

### How User Positioning Works in MapsIndoors

In order to show a user's position ("Blue Dot") on an indoor map with MapsIndoors, a Position Provider must be implemented. You can integrate a 3rd party positioning provider (IPS) to create this experience. For you the developer, this means that the MapsIndoors SDK offers an interface for such a Position Provider, but no building blocks for acquiring positioning.

This guide will show you how to use a third party positioning provider and implement it into your MapsIndoors application. Here we will start from the finished Getting Started app. This code can be found here: [MapsIndoors Getting Started app](https://github.com/MapsPeople/MapsIndoors-Getting-Started-Android).

A full implementation of three different third party positioning providers can be found here [PositionProviders](https://github.com/MapsPeople/MapsIndoors-Getting-Started-Android/tree/feature/third_pary_position_providers/app/src/main/java/com/example/mapsindoorsgettingstarted/PositionProviders)

We recommend reading [Show the Blue Dot with MapsIndoors]({{ site.url }}/content/map/positioning/blue-dot/) guides to get a basic understanding of the MapsIndoors positioning provider interface.
