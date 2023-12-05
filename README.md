# Neighborhood Accessibility Computation

This study develops a proximity-based methodology to assess accessibility, building upon the work of Logan et al. (2022) with a focus on high resolution. The methodology employs two key accessibility statistics: 'Percentage of residents living within 20 min' (PR20) and 'Population-weighted average travel time' (PWT), aiming to represent the accessibility of Data Zones (DZs). 

- **PR20:** Directly evaluates the concept of a 20-minute neighborhood by indicating the percentage of residents with that level of access.
  
- **PWT:** Includes travel times beyond 20 minutes and uses population-weighted averages to determine the average travel time for people in the neighborhood. PWT is introduced to prevent bias that might arise from relying solely on PR20, which may neglect residents with no immediate access.

## Methodology Overview

To explore fine-resolution and city-wide accessibility, the initial intention was to compute travel time from every residential building to amenities. However, residential buildings were found to be clustered within Output Area (OA) boundaries. To optimize computation efficiency, centroids of residential building clusters were computed as the starting point for network analysis to the nearest amenities.

### Step 1: Cluster Residential Buildings

Using DBSCAN (Density-Based Spatial Clustering of Applications with Noise), residential buildings were grouped into clusters within each OA. A 100m distance threshold was chosen considering the width of residential buildings and the walking distance of 1 minute. Centroids of residential clusters were generated for further analysis.

### Step 2: Calculate Maximum Travel Time to Nearest Amenities

For each centroid within an OA, walking time to the nearest grocery store, primary school, GP (general practitioner), pharmacies, and park were computed. The maximum travel time to the nearest of these amenities was utilized to represent the accessibility of a single residential centroid.

### Step 3: Calculate OA's Average Travel Time

Centroids of residential building clusters provided a more accurate distribution of the population within each OA. Instead of relying on a single centroid for the entire OA, average travel time across all centroids was calculated, ensuring a more nuanced representation of accessibility, especially in OAs with dispersed or divided residential buildings.

Once the OAs’ average travel times were calculated, population data stored in OAs was applied to generate neighborhood-wide (DZ-wide) accessibility statistics.

This README provides a comprehensive overview of the methodology, featuring a detailed flowchart and step-by-step description for clarity.

