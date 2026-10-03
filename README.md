# Weekly GitHub Summary Workflow

This n8n workflow automatically generates a weekly narrative summary of a GitHub repository's activity using the Claude API and delivers it via email.

## Features

- **Scheduled**: Runs every Friday at 5:00 PM (configurable)
- **Data Sources**: Fetches commits, closed issues, and merged pull requests from the past week via GitHub API
- **AI Summary**: Uses Claude 3.5 Sonnet to generate a concise, engaging narrative summary
- **Delivery**: Sends the summary via email (configurable to Discord/Slack webhook)
- **Configurable**: All variables are set as workflow parameters for easy customization

## Setup Instructions

1. **Import the Workflow**
   - In your n8n instance, go to Workflows → Import
   - Select the `workflow/weekly-summary.json` file

2. **Configure Credentials**
   - Create the following credentials in n8n:
     - **GitHub API**: Personal access token with `repo` scope (read-only is sufficient)
     - **Claude API**: API key from Anthropic (https://console.anthropic.com/)
     - **Email SMTP**: Your email service credentials (or configure for Discord/Slack webhook instead)

3. **Set Workflow Parameters**
   - Open the workflow and click on the "Settings" tab → "Workflow Parameters"
   - Set the following parameters:
     - `githubRepo`: The repository in format `owner/repo` (e.g., `claude-builders-bounty/claude-builders-bounty`)
     - `claudeApiKey`: Reference to your Claude API credential
     - `senderEmail`: Email address to send from
     - `recipientEmail`: Email address to send to
     - (Optional) Modify the cron trigger time/days if needed

4. **Activate the Workflow**
   - Toggle the workflow to "Active"
   - It will now run automatically every Friday at 5:00 PM

5. **Manual Test**
   - Click "Execute Workflow" to run it immediately and verify the output
   - Check your email for the generated summary

## Customization

- **Change Delivery Method**: Replace the "Send Email" node with a Discord, Slack, or other notification node
- **Adjust Time Period**: Modify the date calculations in the GitHub nodes (currently set to past 7 days)
- **Customize Prompt**: Edit the "Format Prompt" function node to change the summary style or instructions
- **Add More Data Sources**: Include GitHub releases, releases, or other events as needed

## Requirements

- n8n instance (self-hosted or n8n.cloud)
- GitHub account with access to the target repository
- Claude API account (Anthropic)
- Email service or alternative notification method

## License

MIT

## Acknowledgments

- Built for the Claude Builders Bounty: https://github.com/claude-builders-bounty/claude-builders-bounty/issues/5