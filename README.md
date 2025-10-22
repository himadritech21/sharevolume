# SEC Company Stock Shares Outstanding Viewer

This is a single-page responsive HTML application built with Tailwind CSS and JavaScript to display the maximum and minimum common stock shares outstanding for a given company, based on data retrieved from the SEC XBRL API. The data is filtered for fiscal years greater than 2020.

## Features

-   **Dynamic Data Fetching**: Fetches company data from the SEC XBRL API.
-   **Responsive Design**: Utilizes Tailwind CSS for a mobile-first, responsive layout.
-   **Live Data Updates**: Displays the entity name, maximum, and minimum shares outstanding along with their respective fiscal years.
-   **CIK Parameter Support**: Allows viewing data for different companies by providing a CIK (Central Index Key) in the URL.
-   **Client-Side Rendering**: Updates content without a full page reload.

## How to Use

1.  **Open `index.html`**: Simply open the `index.html` file in your web browser.
    -   By default, it will display data for **Applied Materials (CIK 0000006951)**.

2.  **View Data for Other Companies**: To view data for a different company, append a `CIK` query parameter to the URL.
    -   **Example for Apple Inc.**: `index.html?CIK=0001018724`
    -   Replace `0001018724` with any valid 10-digit CIK.

## Technical Details

-   **HTML**: Structure of the application.
-   **Tailwind CSS**: Used for styling and ensuring responsiveness. The CSS is included via a CDN.
-   **JavaScript**: Handles data fetching from the SEC API, processing, and dynamic updates of the DOM.
    -   **Data Source**: `https://data.sec.gov/api/xbrl/companyconcept/CIK[YOUR_CIK]/dei/EntityCommonStockSharesOutstanding.json`
    -   **Proxy**: A public CORS proxy (`https://api.allorigins.win/raw?url=`) is used to mitigate potential browser CORS issues when fetching directly from the SEC API.
    -   **User-Agent**: A descriptive `User-Agent` header is sent with the API request, as per SEC guidance. Please ensure you replace `AppliedMaterials-CIK-App myemail@appliedmaterials.com` in `index.html` with your actual contact information.
    -   **Filtering**: Only `val` entries for fiscal years (`fy`) greater than 2020 are considered.

## Development

To run this application, no build tools are required. Just open `index.html` in a modern web browser.

## Provided Attachments

-   `uid.txt`: This file is provided as-is and is not directly used or rendered within the `index.html` application. Its purpose is external to the application's functionality.
