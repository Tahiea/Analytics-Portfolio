 ## Case Overview

This case study represents a common business scenario where a sales team is working with a limited budget during the pilot stage of a CRM implementation. Without access to advanced enterprise features, the team needed an efficient way to automate its sales processes.

The sales team already used Zoho extensively for lead generation but required the data to be transferred automatically into Monday.com CRM, which served as the central hub for managing leads and clients. The objective was to eliminate manual data entry while ensuring both systems remained up to date.

Power BI was used as the primary reporting and visualisation tool, so data from Monday.com CRM also needed to be made available for dashboards and business insights.

The solution required integrating Zoho, Monday.com Pro, and Power BI Pro to create a seamless, automated workflow between the three platforms.

I'd make it less of a technical workflow and more of a **business process**. Someone looking at a portfolio should understand the problem in under a minute, then appreciate the technical implementation afterwards.

---

## Workflow

### 1. Lead Generation (Zoho Forms & Zoho Campaigns)

Marketing campaigns collect new leads through Zoho Forms and Zoho Campaigns. New submissions are automatically stored within Zoho, where they become the source of truth for incoming prospects.

↓

### 2. Automated Data Extraction

A scheduled Google Apps Script retrieves newly created leads from Zoho using the Zoho API. The script extracts only the required fields and writes them into a structured Google Sheet, which acts as a lightweight staging area.

↓

### 3. Data Cleaning & Transformation

Within Google Sheets, the Apps Script:

* Validates required fields.
* Formats dates and phone numbers.
* Maps Zoho field names to the corresponding Monday.com CRM columns.
* Removes unnecessary formatting and prepares values for the Monday API.

↓

### 4. Monday.com CRM Synchronisation

The processed data is sent to Monday.com CRM using the GraphQL API.

The automation:

* Creates new lead records.
* Updates existing records when information changes.
* Prevents duplicate entries by checking unique identifiers before creating

