1. Purpose & Business Value
Streamlines the sales process from lead generation to order fulfillment.


2. Key DocTypes

| DocType       | Main Fields                    | Linked To     |
| ------------- | ------------------------------ | ------------- |
| Quotation     | Customer, Items, Validity      | Opportunity   |
| Sales Order   | Customer, Items, Delivery Date | Quotation     |
| Delivery Note | Customer, Items, Posting Date  | Sales Order   |
| Sales Invoice | Customer, Items, Due Date      | Delivery Note |

3. Standard Workflow

graph TD
A[Create Quotation] --> B[Submit Quotation]
B --> C[Create Sales Order]
C --> D[Create Delivery Note]
D --> E[Create Sales Invoice]

4. Roles & Permissions

| Role          | Read | Write | Submit |
| ------------- | ---- | ----- | ------ |
| Sales User    | ✅   ✅     | ✅     |
| Sales Manager | ✅   | ✅   |✅      |

5. Typical Customizations

Custom print formats for quotations

Automated email notifications on order submission

6. API Endpoints & Sample cURL

curl -X POST https://yourdomain/api/resource/Sales Order \
-H "Authorization: token your_api_key:your_api_secret" \
-H "Content-Type: application/json" \
-d '{"customer":"Customer Name","items":[{"item_code":"ITEM001","qty":1}]}'

7. Troubleshooting & FAQs

Issue: Unable to submit Sales Order
Solution: Ensure stock availability and customer credit limit.

