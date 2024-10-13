# Airtable Quicket Sync

This project provides a script to sync events from the Quicket API to an Airtable base. It utilizes the `pyairtable` library for interacting with Airtable and fetches event data from the Quicket platform, formats it, and uploads it to Airtable.

## Prerequisites

- **Python 3.7+**
- **Airtable Account**
- **Quicket API Access**

### Libraries/Dependencies:

- `pyairtable` - For Airtable integration
- `requests` - For making API requests
- `Geohash` - For encoding geolocation data
- `configparser` - For reading configuration settings

Install the required libraries using the following command:

```bash
pip install pyairtable requests geohash configparser
```

## Configuration

1. **config.cfg**:
   This file contains the necessary API keys and other configuration details. Here's an example configuration file (`config.cfg`):

   ```ini
   [AIRTABLE]
   BASE_ID = your_airtable_base_id
   TABLE_NAME = your_airtable_table_name
   API_KEY = your_airtable_api_key

   [QUICKET]
   BASE_URL = your_quicket_base_url
   API_KEY = your_quicket_api_key
   ```

2. **Airtable Setup**:
   - Create a table in your Airtable base to hold event data with relevant fields like Title, Description, Location, GeoHash, etc.

## How to Use

1. Clone the repository:

   ```bash
   git clone https://github.com/your-repo/airtable_quicket_sync.git
   cd airtable_quicket_sync
   ```

2. Ensure you have created a `config.cfg` file with your API keys as shown in the example above.

3. Run the script:

   ```bash
   python airtable_quicket_sync.py
   ```

## How it Works

- **Quicket API**: The script fetches event data using the Quicket API, with options to filter by date and location.
- **Data Processing**: The script processes the event data, formats it, and extracts key fields such as event name, description, venue, geolocation, etc.
- **Airtable**: The processed event data is uploaded to Airtable via the `pyairtable` library.

## Customization

You can modify the `get_events()` function to filter events based on different categories, dates, or any other criteria supported by the Quicket API.

### Quicket Categories

You can filter events by categories like:
- Music: `categories=1`
- Sports & Fitness: `categories=5`
- Travel & Outdoor: `categories=6`

## Example Output

When you run the script, it fetches event data from Quicket and uploads it to Airtable. Each event will include details like the event name, description, geohash for location, and other relevant information.

---

Feel free to contribute by submitting pull requests or opening issues.

