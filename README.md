Project Title: Smart Car Dealership 🚗

This project is a straightforward automation workflow designed to streamline the process of logging car sales and notifying stakeholders in real time. It uses a webhook to listen for new sales data and then automatically sends an email notification and records the details in a Google Sheet.

How It Works 🤖
The workflow is built with three main steps:

Webhook Trigger: The process starts with a Webhook node. This node acts as a dedicated listener, waiting for an HTTP POST request from an external source (like Postman or an internal system). When a new sale is recorded and the request is received, it triggers the rest of the workflow.

Email Notification: The data from the incoming webhook is passed to a Send a message node (like a Gmail node). This node uses the received information—specifically the car type, price, and buyer's name—to compose and send an automated email. This is perfect for instantly notifying a sales manager or a team about a completed transaction.

Data Logging: Simultaneously, the same sales data is also sent to an Append row in sheet node (a Google Sheets node). This node takes the car type, price, and buyer's name and adds them as a new row in a specified Google Sheet. This creates a permanent, organized sales log for tracking and analysis.

Key Features ✨
Real-time Automation: Logs and notifies instantly when a new sale occurs.

Dual Functionality: Automatically sends emails and logs data from a single trigger.

Simple & Efficient: Focuses on capturing the essential details of a sale without unnecessary complexity.

No-Code/Low-Code: Built on a visual platform, making it easy to set up and manage without writing custom code.

Requirements 🛠️
Postman: Or any other tool to send HTTP POST requests to the webhook URL.

Email Account: An account with a service like Gmail to send the automated notifications.

Google Sheets: A Google account to create and access the spreadsheet for sales data.

Setup ⚙️
Configure the Webhook: Copy the unique URL provided by the webhook node. This is the endpoint you'll send your POST requests to.

Set up the Email Node: Connect your email account and configure the email's content (subject and body) using data fields from the webhook's payload.

Set up the Google Sheets Node: Connect your Google account, select the desired spreadsheet and sheet, and map the incoming data fields to the correct columns (car_type, price, and buyer) in your sheet.

Send a Request: Use Postman to send a POST request to your webhook URL with a JSON body containing the sales data. For example:



{
  "car_type": "SUV",
  "price": "$32,500",
  "buyer": "Jane Doe"
}


After sending the request, the workflow will automatically send a notification email and add a new row with "SUV," "$32,500," and "Jane Doe" to your Google Sheet.
