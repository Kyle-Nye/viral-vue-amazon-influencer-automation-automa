# Viral Vue Amazon Influencer Automation

Automa browser automation workflows for managing Amazon Affiliate Program Creator Connections using the Viral Vue extension.

![Sample Workflow](Sample%20of%201%20workflow.jpg)
*Example: 2ID Collect 48h workflow in Automa editor*

## Prerequisites

- **[Automa Browser Extension](https://chromewebstore.google.com/detail/automa/infppggnoaenmfagbfknfkancpbljcca)** - Browser automation extension for Chrome
- **[Viral Vue Extension](https://viralvue.com/join?fpr=geektak)** - Amazon Influencer campaign management tool
- **Amazon Affiliate Account** - Active Amazon Associates/Influencer account with Creator Connections access

## Workflow Files

| File | Purpose | Store IDs | Schedule |
|------|---------|-----------|----------|
| `1ID Accept Campaigns V5.automa.json` | Accept campaigns | 1 | 6 AM & 9 PM daily |
| `2ID Collect 48h V5.automa.json` | Collect 48h earnings | 2 | Hourly (most hours) |
| `2IDs Accept Campaigns V5.automa.json` | Accept campaigns | 2 | 6 AM & 9 PM daily |
| `3IDs Collect 48h V5.automa.json` | Collect 48h earnings | 3 | Hourly (most hours) |

### Accept Campaigns Workflows

These workflows automate the campaign acceptance process:
- Navigate to Creator Connections page
- Select each store ID from the dropdown
- Click "Accept Related Campaigns"
- Accept tagged products and auto-linked items
- Use Viral Vue to submit campaign acceptances

### Collect 48h Workflows

These workflows automate earnings collection:
- Navigate to Amazon earnings report page
- Switch between store IDs
- Click "Collect Past 48h" via Viral Vue
- Navigate to Creator Connections
- Accept earnings commissions for the last 48 hours

## Installation

1. Install the [Automa browser extension](https://chromewebstore.google.com/detail/automa/infppggnoaenmfagbfknfkancpbljcca)
2. Install the [Viral Vue browser extension](https://viralvue.com/join?fpr=geektak)
3. Download the workflow JSON files you need
4. Open Automa and go to **Workflows**
5. Click the **Import** button (or use Ctrl+I)
6. Select the downloaded `.automa.json` file(s)
7. The workflow will appear in your workflow list

## Configuration

### Replace Creator ID

The workflows use a placeholder Creator ID that needs to be replaced with your own.

**Option 1: Edit in Automa (Recommended)**
1. Open the imported workflow in Automa
2. Click on each **switch-tab** block that navigates to Creator Connections
3. In the URL field, replace `creatorId=amzn1` with your actual Creator ID
4. Your Creator ID format: `creatorId=amzn1.creator.XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX`

**Option 2: Edit JSON Before Import**
1. Open the JSON file in a text editor
2. Find and replace all instances of `creatorId=amzn1` with your Creator ID
3. Save and import the modified file

**Finding Your Creator ID:**
1. Log into Amazon Associates
2. Go to Creator Connections
3. Copy your Creator ID from the URL in your browser

### Adjust Store IDs

If you have fewer store IDs than the workflow expects:
- Use a workflow that matches your number of store IDs
- Or modify the workflow to remove extra store ID selection steps

The workflows select store IDs by dropdown position:
- Store ID 0 = First store (index 0)
- Store ID 1 = Second store (index 1)
- Store ID 2 = Third store (index 2)

## Usage

### Manual Execution
1. Open Automa
2. Find the workflow in your list
3. Click the **Play** button to run

### Scheduled Execution
The workflows include built-in cron triggers:

**Accept Campaigns workflows:**
- `0 6 * * *` - Runs at 6:00 AM daily
- `0 21 * * *` - Runs at 9:00 PM daily

**Collect 48h workflows:**
- Runs most hours of the day (excluding certain hours to avoid conflicts)

To modify schedules:
1. Open the workflow in Automa
2. Click the **Trigger** block
3. Edit the cron expressions or add/remove triggers

## Troubleshooting

### Workflow Fails to Find Elements
- Ensure you're logged into Amazon Associates
- Check that Viral Vue extension is active and logged in
- Verify your Creator ID is correct in the workflow URLs

### Store ID Selection Fails
- The dropdown may take time to load - workflows include retry logic
- If issues persist, increase the delay times in the workflow

### Viral Vue Buttons Not Found
- Make sure Viral Vue is properly installed and active
- The extension must be loaded on the Amazon page before the workflow runs

### Cron Jobs Not Running
- Ensure Automa has permission to run in the background
- Check that the workflow is enabled (not paused)
- Browser must remain open for scheduled execution

## Important Notes

- **Keep browser open**: Automa requires the browser to be running for scheduled tasks
- **Stay logged in**: Ensure persistent login to Amazon Associates and Viral Vue
- **Rate limits**: Avoid running workflows too frequently to prevent Amazon throttling
- **Review changes**: Periodically verify the workflows are functioning correctly as Amazon may update their UI

## License

These workflows are provided as-is for personal use with your Amazon Affiliate account.
