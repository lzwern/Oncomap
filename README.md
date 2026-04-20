# README: DKG Outreach 2026 · Resilience

## Overview
The **DKG Outreach 2026** tool is a specialized interactive data visualization and management application designed for oncology center outreach. It utilizes a geospatial interface powered by **Leaflet** to visualize the network of **Oncology Centres (OZ)**, **Organ Centres**, and their associated **Partners**.

The application aggregates data from **Oncomap direct APIs** and provides essential tools for assignment management, team synchronization, and CRM-ready exports.

---

## Key Features

* **Interactive Map Navigation**: Toggle layers for Oncology Centres (OZ), Organ Centres, Partners, and unassigned entities.
* **Network Visualization**: Selecting an OZ highlights its specific network, drawing lines to linked organ centres (blue) and dashed lines to partners (orange).
* **Proximity Logic**: To maintain map clarity, partner connections are only displayed if they are within **250km** of the parent OZ.
* **Standardized Metadata**: Every record supports unified fields for **Wave (1-4)**, **Outreach Status**, **Owner**, and **Notes**.
* **Certification Tracking**: The tool parses certification dates and flags records with a "⚠️" if they expire within **18 months**, prioritizing them for outreach.
* **CRM Integration**: Generates specialized CSV exports pre-formatted for **HubSpot**.
* **State Persistence**: Manage team progress by exporting/importing `state.json` files or loading shared states directly from a GitHub repository.

---

## Interface Tabs

| Tab | Purpose |
| :--- | :--- |
| **Explore** | Search and filter the full database of 1000+ entities. |
| **Focus** | View detailed metadata, connections, and set assignments for a specific centre. |
| **Outreach** | Manage your current selection and trigger CSV exports. |
| **Pipeline** | High-level overview of assignments across Wave 1 through Wave 4. |
| **Sync** | Handle state management to synchronize data across team members. |

---

## Technical Configuration

### Data Sources
The tool fetches data from the following **Oncomap** endpoints:
* Centers: `fulldb_centers`
* Oncology Centres: `fulldb_oncos`
* Visceral Centres: `fulldb_viszes`
* Urology Centres: `fulldb_uros`
* Partners: `fulldb_partners`

### Map Legend
* **ONKO (Blue)**: Oncology centres.
* **VISZ (Green)**: Visceral centres.
* **URO (Orange)**: Urology centres.
* **Organ Centre (Cyan)**: Specific medical centres.
* **Partner (Dark Orange)**: Registered partner organizations.

---

## Workflow Guide

1.  **Exploration**: Use the **Explore** tab to filter by organ type or region.
2.  **Mapping**: Click a marker on the map to enter **Focus** mode, revealing the associated network.
3.  **Assignment**: Set the target **Wave** and **Outreach Status** (New, Contacted, Replied, Meeting, Not interested).
4.  **Batching**: Use **"Add all to outreach"** to move filtered results into the export queue.
5.  **Syncing**: Share progress by exporting `state.json` and committing it to the `/data` folder in your repository.
