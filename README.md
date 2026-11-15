# Purchasing Answers — Search Pages Site

Plain static HTML/CSS. No build step. No dependencies.

Six pages answer common purchasing questions and point readers to the free
Supplier Overpay Check and the matching paid tool:

| File | Question | Paid tool in the funnel block |
| --- | --- | --- |
| `index.html` | Home / index of the five questions | Procurement Template Pack ($49) |
| `safety-stock-calculator.html` | How much safety stock? | Inventory Min/Max & Reorder Calculator ($29) |
| `reorder-point-calculator.html` | When do I reorder? What are min/max? | Inventory Min/Max & Reorder Calculator ($29) |
| `landed-cost-calculator.html` | What is the true cost at my door? | Incoterms Calculator ($19) |
| `supplier-scorecard-template.html` | How do I grade a supplier? | Procurement Template Pack ($49) |
| `price-creep.html` | Why do prices rise with no notice? | Procurement Template Pack ($49) |

Every page also links the free Supplier Overpay Check on Gumroad.

Files:

- `index.html` plus the five topic pages above
- `style.css` — one shared stylesheet, linked by every page
- `README.md` — this file

## Deploy on GitHub Pages

1. Create a new **public** repository on GitHub (for example `search-pages`).
   Do not add a README, .gitignore, or license in the GitHub form — this
   folder already has the files.
2. From this folder, push the files:

   ```bash
   cd ~/workspace/search-pages-site
   git init
   git add .
   git commit -m "Search pages site v1"
   git branch -M main
   git remote add origin https://github.com/<your-username>/search-pages.git
   git push -u origin main
   ```

3. In the repository on GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
5. Set the branch to **main** and the folder to **/ (root)**. Click **Save**.
6. Wait one to two minutes. GitHub shows the live URL at the top of the
   Pages settings screen. The form is:

   `https://<your-username>.github.io/search-pages/`

7. Open the URL. Check the home page and each of the five topic pages.
   Check one page on a phone or a narrow browser window.

## Custom domain (CNAME) — only if a domain is chosen later

1. Add a file named `CNAME` (no extension) in the repository root. The file
   holds one line: the domain only, for example `answers.example.com`.
2. Commit and push the `CNAME` file.
3. At the DNS provider for the domain, add the DNS record:
   - For a subdomain (for example `answers.example.com`): a **CNAME** record
     that points the subdomain to `<your-username>.github.io`.
   - For an apex domain (for example `example.com`): **A** records that point
     to GitHub Pages IPs `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, and `185.199.111.153`.
4. In **Settings → Pages**, enter the domain in the **Custom domain** field
   and save. Wait for the DNS check to pass.
5. Turn on **Enforce HTTPS** in the same screen after the certificate is
   issued (this can take some minutes).

## Notes

- Edit text in the `.html` files directly. No build is needed. Push the
  change and GitHub Pages updates the site in about a minute.
- Keep one funnel block per page: the free check first, the paid tool second.
- Author line on every page: "By Michael Olson, Senior Strategic Buyer,
  15+ years in manufacturing purchasing."
