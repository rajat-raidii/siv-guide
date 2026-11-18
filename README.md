# Siv for Agentforce — Post-Install Setup Guide

Welcome to **Siv**! Follow this 4-step quick-start guide to assign permissions, connect your Agentforce reasoning engine, and run your first AI Sales Brief.

> 🌐 **Interactive Web Guide (GitHub Pages):** [View the interactive guide with screenshots](https://rajat-raidii.github.io/siv-guide/)

---

## Step 1: Assign Siv Permission Sets (1 Minute)

Salesforce requires administrators to grant package permission sets to users before accessing custom objects, tabs, and analytics workspaces.

1. In Salesforce, navigate to **Setup** &rarr; **Users** &rarr; **Permission Sets**.
2. Assign the following permission sets:
   - **`raidii__Siv_Admin` (Siv Administrator):** Grants access to Siv Admin console, prompt template management, and agent publishing controls. Assign to Salesforce Admins.
   - **`raidii__Siv_User` (Siv User):** Grants access to the Siv Console, Siv Briefs workspace, story execution, and AI Assistant chat. Assign to Sales Reps and Managers.
3. Ensure your admin also has standard Agentforce permissions: `EinsteinGPTPromptTemplateUser` and `AgentPlatformBuilder`.

---

## Step 2: Open Siv Admin & Copy Agent Script (30 Seconds)

Siv packages a pre-configured Agentforce prompt script that instructs the Atlas reasoning engine how to dynamically route sales queries and synthesize briefs.

1. Open the **App Launcher** (9 dots icon) and search for **Siv**.
2. Select the **Siv Admin** tab (or navigate directly to `/lightning/n/raidii__Siv_Setup`).
3. Click on the **Agent Setup** tab.
4. Click the blue **"Copy Agent Script"** button. The complete customer-ready script is copied to your clipboard.

---

## Step 3: Create & Activate Agent in Agentforce Studio (2 Minutes)

Register your new AI agent inside Salesforce's native Agentforce Studio.

1. In Salesforce Setup, navigate to **Agentforce Agents** (`/lightning/setup/EinsteinCopilot/home`).
2. Click **"+ New Agent"** in the top right.
3. Select **Agentforce Employee Agent** and click **Create Agent**.
4. Set the basic agent details:
   - **Agent Name:** `Siv Agent`
   - **API Name:** `Siv_Agent`
   - **Role:** `Sales Intelligence & Revenue Strategy Assistant`
   - **Company:** Your company name
5. In the **Agent Instructions** text area, **Paste (Ctrl+V / Cmd+V)** the script copied in Step 2.
6. Click **Save**, then click **Activate** in the top header.

---

## Step 4: Verify Connection & Run Your First Brief (1 Minute)

1. Return to **Siv Admin &rarr; Agent Setup**. The setup card will automatically display an **Active (Green)** badge with your live Agent ID.
2. Click on the **Siv Briefs** tab in the navigation bar.
3. Siv automatically seeds 4 starting revenue briefs:
   - **Pipeline Velocity & Hydrodynamic Flow**
   - **Account 360 & Lifetime Value**
   - **Customer Retention & Dormancy Analysis**
   - **Rep 1-on-1 Coaching & Progression**
4. Select **Pipeline Velocity & Hydrodynamic Flow** and click **"Run"**.
5. Within **8–10 seconds**, Siv synthesizes active CRM opportunities, 14-day trailing velocity, and stalled risk factors into an executive summary report!
6. In the right-hand panel, ask Siv Assistant any pipeline question (e.g., *"What is our active pipeline by stage this quarter?"*) to see Agentforce Atlas reasoning in real time.

---

## Troubleshooting & FAQ

#### Q: Why did Salesforce display "This app is taking a long time to install"?
Siv contains comprehensive custom objects, LWC components, and packaged prompt templates. Salesforce compiles components asynchronously (~60–90 seconds). Click **"Done"**; Salesforce will finalize installation in the background.

#### Q: Why did Salesforce ask to approve Third-Party Access for `api.salesforce.com`?
Siv communicates natively with Salesforce's official Agentforce reasoning and Tooling APIs. All communication remains strictly within the Salesforce ecosystem using secure HTTPS (TLS 1.3). No data is sent to unauthorized external servers.

#### Q: How does Credit and Token Metering work?
Siv includes an integrated real-time credit meter visible in the top bar. Every Brief run and Chat turn logs prompt tokens, completion tokens, and calculated credit burn into `Siv_Log__c` with zero cost surprises.

#### Q: Need help?
Email the Siv engineering team at [hello@raidii.com](mailto:hello@raidii.com) or open an issue on GitHub.
