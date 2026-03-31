# Mawarid Finance — Document Generator

A browser-based tool for generating auto finance documents (LPO, Murabaha Sale Contract, Offer Letter, Downpayment Requisition) by fetching lead data from LeadSquared CRM.

## Setup

### 1. GitHub Pages Hosting

1. Push this repository to your GitHub account
2. Go to **Settings → Pages**
3. Under **Source**, select `main` branch, root `/`
4. Click **Save**
5. Your portal will be live at `https://<username>.github.io/<repo-name>/`

### 2. Share with your team

Share the GitHub Pages URL with your team. They just need a browser — no installation required.

## How to Use

1. Open the portal URL in any browser
2. Enter your LeadSquared **Access Key** and **Secret Key**
3. Enter the **Lead ID** for the order
4. Select one or more documents to generate (LPO, Murabaha, Offer Letter, Downpayment)
5. Click **Generate Documents**
6. Each selected document downloads as a filled `.docx` file to your local machine

## Updating Templates

To update a template:
1. Edit the `.docx` file in the `templates/` folder
2. Keep placeholders in `{{ field_name }}` format
3. Push the updated file to GitHub
4. The portal will use the updated template immediately (after GitHub Pages deploys)

## File Structure

```
├── index.html          # The portal (single-page app)
├── templates/
│   ├── LPO.docx
│   ├── Murabaha.docx
│   ├── Offer_Letter.docx
│   └── Downpayment.docx
└── README.md
```

## Supported Placeholders

Placeholders are pulled from LeadSquared lead fields. Date fields are formatted as `DD-Mon-YYYY`, amount fields as `1,234.56`. A computed field `total_receivable_out_of_selling_price` (Finance Amount + Profit Amount) is also available.

## Security Note

- API keys are entered at runtime and never stored
- All processing happens in the browser — no data is sent to any server other than LeadSquared
- The portal is a static site with no backend
