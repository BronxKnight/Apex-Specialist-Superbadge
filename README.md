# Apex-Specialist-Superbadge

## What You'll Be Doing to Earn This Superbadge
### 1. Automate record creation using Apex triggers
### 2. Synchronize Salesforce data with an external system using asynchronous REST callouts
### 3. Schedule synchronization using Apex code
### 4. Test automation logic to confirm Apex trigger side effects
### 5. Test integration logic using callout mocks
### 6. Test scheduling logic to confirm action gets queued

##Set Up Development Org
### 1. Create a new Trailhead Playground for this superbadge. Using this org for any other reason might create problems when validating the challenge. If you choose to use a development org, make sure you deploy My Domain to all the users. The package you will install has some custom lightning components that only show when My Domain is deployed.

### 2. Install this unlocked package (package ID: 04t6g000008av9iAAA). This package contains metadata you'll use to complete this challenge. If you have trouble installing this package, follow the steps in the Install a Package or App to Complete a Trailhead Challenge help article.

### 3. Add picklist values Repair and Routine Maintenance to the Type field on the Case object.

### 4. Update the Case page layout assignment to use the Case (HowWeRoll) Layout for your profile.

### 5. Rename the tab/label for the Case tab to Maintenance Request.

### 6. Update the Product page layout assignment to use the Product (HowWeRoll) Layout for your profile.

### 7. Rename the tab/label for the Product object to Equipment.

### 8. Use App Launcher to navigate to the Create Default Data tab of the How We Roll Maintenance app. Click Create Data to generate sample data for the application.


## Standard Objects

### Maintenance Request (renamed Case) — Service requests for broken vehicles, malfunctions, and routine maintenance.
### Equipment (renamed Product) — Parts and items in the warehouse used to fix or maintain RVs.
## Custom Objects
### Vehicle — Vehicles in HowWeRoll’s rental fleet.
### Equipment Maintenance Item — Joins an Equipment record with a Maintenance Request record, indicating the equipment needed for the maintenance request.
## Entity Diagram


![image](https://user-images.githubusercontent.com/46152393/126892218-0a9ad198-bb0f-45a9-852f-80b2dd4a93ff.png)


