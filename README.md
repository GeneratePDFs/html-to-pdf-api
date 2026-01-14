# HTML to PDF API Guide

This repository is a resource for developers who want to convert HTML into PDF through an API.  
It explains the typical workflows, the tools involved and how to use a hosted service to generate PDFs at scale.

If you are looking for a simple way to send HTML or a URL and receive a PDF in response, this guide will help you get started.

## Why Use an API for HTML to PDF?

An API gives you a consistent rendering environment without the need to install local binaries or maintain server level tools.  
This is ideal for applications that need reliable PDF generation in production.

Developers use HTML to PDF APIs for:

- invoices and billing documents  
- reports and summaries  
- dynamic user generated PDFs  
- scheduled exports  
- documents created through automation pipelines  

## A Hosted Solution That Handles Everything

### GeneratePDFs.com HTML to PDF via a simple API

A hosted API created for developers who want fast and predictable PDF rendering.  
You can:

- send HTML directly  
- send a public URL  
- include assets, fonts and styles  
- receive a PDF in seconds  
- start on a free plan  
- avoid maintaining rendering engines or browser based tools  

👉 **Learn more:** https://generatepdfs.com  
👉 **Start on a free plan**

---

## API Workflows

Typical usage involves making a request to the API and downloading the PDF from the response.

### Generate PDF from HTML and CSS

```bash
HTML_B64=$(base64 -i /path/to/file.html | tr -d '\n')
CSS_B64=$(base64 -i /path/to/file.css | tr -d '\n')

curl -X POST https://api.generatepdfs.com/pdfs/generate \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d "{
    \"html\": \"$HTML_B64\",
    \"css\": \"$CSS_B64\"
  }"
```

### Generate PDF from a URL

```bash
curl -X POST https://api.generatepdfs.com/pdfs/generate \
  -H "Authorization: Bearer YOUR_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com"}'
```

### Get a PDF by ID

```bash
curl -X GET https://api.generatepdfs.com/pdfs/123 \
  -H "Authorization: Bearer YOUR_TOKEN"
```

You can also include images in base64 form, along with their names and mime types, when your HTML references embedded assets.

---

## Official SDKs

GeneratePDFs.com provides SDKs to make the API integration easier.

Available SDKs:

- [PHP SDK](https://github.com/generatepdfs/php-sdk)
- [Laravel SDK](https://github.com/generatepdfs/laravel-sdk) which extends the PHP SDK
- [Node SDK](https://github.com/generatepdfs/node-sdk)
- [Ruby SDK](https://github.com/generatepdfs/ruby-sdk)
- [Python SDK](https://github.com/generatepdfs/python-sdk)

Each SDK includes helper methods for sending HTML, checking responses and saving the resulting PDF.

---

## Example Use Cases

Developers often use the API to:

- generate invoices automatically when an order completes  
- convert reports into PDF for internal teams  
- allow users to save content as PDF  
- create scheduled exports for data rich dashboards  
- produce certificates or tickets through automation  

The companion repository named `html-to-pdf` covers general HTML to PDF concepts if you are exploring non API based approaches as well.

---

## About This Repository

This repo exists to guide developers who search for:

- html to pdf api  
- convert html to pdf with api  
- pdf generation service  
- best html to pdf api  
- api for rendering html as pdf  

It also directs developers to a hosted platform that removes the need to manage PDF tooling yourself.

If you have questions or suggestions, feel free to open an issue.

---

## License

MIT License
