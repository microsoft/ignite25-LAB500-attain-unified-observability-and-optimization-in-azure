# Lab Instructions

## Act 1: Detect & Troubleshoot (15 min)

### Scenario 1: Investigate & Find the Root Cause of Your App Failures

**Goal:** Resolve app request failures caused by Azure Blob Storage network restrictions.

**Steps:**

1. Open [Operations Center Lab](https://aka.ms/OperationsCenterLab).  
2. Click on **Monitor** under Observability.  
3. Scan the Azure Monitor Overview page. In the **Top Actions** section, notice a **critical alert** triggered for your application. Select **Investigate** to explore the root cause.  
4. In the **Issues** view, review AI-generated insights. The failure should be due to **denial of access to Azure Blob Storage because of misconfigured permissions (firewall blocked)**.  
5. Review the **Evidence Summary** by clicking **5 Application logs anomalies** to validate the AI-identified root cause.  
6. Expand example events to check traces in App Insights.  
7. Once validated, fix the issue by enabling **PublicNetworkAccess** on your Azure Storage.

**Success Criteria:**

- Used Top Actions to identify attention areas.  
- Uncovered root cause of app failure via AI findings.  
- Validated AI-based root cause using evidence.

---

### Scenario 2: Improve Monitoring Posture with Service Groups

**Goal:** Create a Service Group to receive tailored recommendations and improve workload monitoring.

**Steps:**

1. Open [Operations Center Lab](https://aka.ms/OperationsCenterLab).  
2. Click **Monitor** under Observability.  
3. From **Top Actions**, select **Create Service Group**.  
4. Fill in details:  
    - **Service Group Name:** Ensure it is unique (e.g., include lab instance ID).  
    - Click the blue button to select the Parent.  
5. Add members by selecting all resources.  
6. Click **Review and Create**, then **Create** to finalize the Service Group.  
7. Navigate to **Monitor** in your new Service Group.  
8. Click on **Coverage + Recommendations** tab. Wait a few minutes for recommendations to appear.  
9. Apply **Advisor Observability recommendations** to enable monitoring for VMs at scale.  
10. Select the VMs to enable monitoring on and click **View details and configure**.  
11. In the context panel, review what data is being collected and select an **Azure Monitor Workspace** and **Log Analytics Workspace** (or create new).  
12. Save selections and click **Enable**. Wait for the notification **"successfully enabled VM Insights"**.  
13. Click **View Monitoring details** to verify onboarding of all VMs to VM Insights.  
14. Explore OpenTelemetry metrics and performance counters to monitor and alert on your VM’s health.  
15. Review comprehensive monitoring capabilities in VM Insights:  
    - System-level metrics: CPU, memory, disk I/O, network  
    - Per-process visibility: uptime, memory usage, open file descriptors  
    - Application telemetry: MongoDB, Cassandra, Oracle  
    - Cross-platform consistency: unified schema for Linux and Windows

**Success Criteria:**

- Created a Service Group for resource management.  
- Strengthened monitoring posture by enabling infrastructure monitoring at scale.

---

## Act 2: Optimize Cost & Carbon (10 min)

### Scenario 3: Orient & Triage with Optimization Overview

**Goal:** Get a single-pane snapshot of cost, carbon, and optimization metrics across your subscriptions.

**Steps:**

1. Open [Operations Center Lab](https://aka.ms/OperationsCenterLab).  
2. Select **Optimization** in the left navigation pane.  
3. Scan KPI tiles under **Cost and Carbon Emissions Summary**, including:  
    - **Monthly Cost and Forecast:** Current month, Last month, Forecasted cost  
    - **Last Month Carbon Footprint:** Month-over-month % change  
    - **Top Contributors to Cost and Carbon:** Top subscriptions, cost trends, forecasted changes, emissions, alerts  
4. Review the **Optimization Recommendations** summary:  
    - Scroll down for usage optimization, reservations, savings plan recommendations  
    - Click **View usage optimization recommendations** for actionable opportunities  
5. Navigate back to overview and review **Top Actions**.  
6. Use **Optimize with Copilot** to act on any of these Top Actions (will be used more in Act 3).

**Success Criteria:**

- Understood cost and carbon posture.  
- Reviewed Top Actions for the subscription.

---

### Scenario 4: Deep Dive into Carbon Optimization

**Goal:** Understand sustainability impact and identify opportunities to reduce carbon emissions.

**Steps:**

1. In Optimization overview, locate the **Carbon Emissions** card and click **View Emissions Breakdown**.  
2. Complete the Teaching tour if prompted.  
3. Review emissions trends:  
    - Total carbon emissions for last 12 months  
    - Last month emissions and % change  
    - Potential monthly emissions reductions  
    - Monthly emissions chart for trend analysis  
4. Review breakdown charts:  
    - **Emissions by resource type**: Which Azure services contribute most  
    - **Emissions by location**: Regions with higher impact  
    - **Carbon intensity**: CO₂e per unit of compute over time  
5. Scroll to **Top Reduction Opportunities** and review each recommendation card.  
6. Review **Carbon Optimization Details** under the **Details** tab:  
    - Examine **Resources** contributing to emissions  
7. Review **Reductions** tab for potential monthly and carbon reductions, as well as cost savings.

**Success Criteria:**

- Recorded carbon emissions for your subscription.  
- Identified high-emission resources.  
- Determined actionable ways to reduce emissions.

---

## Act 3: Drive Efficiency with the Optimization Agent (20 min)

### Scenario 5: Optimize Underutilized VMs

**Goal:** Reduce unnecessary spend and carbon emissions by optimizing low-utilization VMs.

**Steps:**

1. Open **Optimization** in the left navigation pane.  
2. Click the **Copilot** icon to open the assistant.  
3. Enable **Agent Mode** in Copilot and enter full screen.  
4. Ask Copilot for **Top Cost-Saving Recommendations**:

    > Show me the top 5 cost saving recommendations for [subscription ID]  
6. Copilot returns a ranked list with cost savings, resource names/types, and links to explore each recommendation.  
7. Select a VMSS recommendation and ask Copilot to explain the data:

   > Explain the recommendation for ContosoDataPuller.
   
   Copilot will return:
    - Recommended action  
    - Potential cost and carbon savings  
    - Resource summary  
    - Current vs. recommended SKU  
    - Utilization charts  

8. Ask Copilot to generate execution scripts: 

   > Generate a PowerShell for the rightsize
  
   > Generate an Azure CLI for the rightsize

**Success Criteria:**

- Validated recommendation explanation.  
- Generated scripts to apply changes.

---

### Scenario 6: Optimize Using Top Actions

**Goal:** Execute Top Actions and explore alternative recommendations to improve efficiency and savings.

**Steps:**

1. Return to **Optimization** overview.  
2. Act on a Top Action using **Optimize with Copilot** (e.g., second top action for **contosodataprocessor**).  
3. Review Copilot’s recommendation explanation.  
4. Explore **Alternative Recommendations** for SKUs or types:  

   > What are my alternative recommendations?  
6. Copilot returns ranked alternatives with savings for each.  
7. Generate execution scripts for selected alternatives:  

   > Generate a PowerShell for option 1  

   > Generate an Azure CLI for option 2

**Success Criteria:**

- Validated Top Action recommendations.  
- Explored alternative optimization options.  
- Generated scripts to apply changes.
