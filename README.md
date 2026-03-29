# Profit Mix Optimizer

A Streamlit app for analyzing and optimizing mixes across Israeli savings and investment products, with Google Sheets-backed product data.

## Run locally

```bash
pip install -r requirements.txt
streamlit run streamlit_app.py
```

## Required setup

The app expects access to Google Sheets product data.

In Streamlit secrets, configure:
- `APP_PASSWORD`
- `[gcp_service_account]` (required for community voting / Google Sheets write access)

A template is included at `.streamlit/secrets.toml.example`.

## Notes

- Product sheet IDs were updated to the new sources.
- Institutional strategy analysis was removed from the packaged app.
- Product return fields are now loaded from the source sheets.
- The results table includes weighted 12M return.
- The selected alternative panel includes a weighted returns table for YTD / 12M / 36M / 60M.

## Startup checklist

Before deployment:
1. Confirm the Google Sheets are shared as Viewer for export access.
2. Add `APP_PASSWORD` in Streamlit secrets.
3. Add `[gcp_service_account]` in Streamlit secrets if voting is needed.
4. Launch once and verify product data loads for each product type.
5. Run one optimization and verify the weighted return fields render.
