## CIDR Sheet (`cidr-sheet`)

**Online demo:** [cidrsheet.labs.digitalfruition.com](https://cidrsheet.labs.digitalfruition.com)
**Source code:** [https://github.com/hmblprogrammer/cidr-sheet](https://github.com/hmblprogrammer/cidr-sheet)
**License:** MIT

---

### Overview

CIDR Sheet is a lightweight, browser-based network management tool that replaces static spreadsheets for storing and editing network information. It leverages the [Tabulator](https://tabulator.info/) library to provide a fully editable, filterable, and sortable table of CIDR ranges, VLANs, physical locations, and metadata.

### Key Features

* **Editable columns**: Inline edit fields for Name, Region/Site, Location, CIDR Range, VLAN ID, Status, Description, and Tags.
* **Computed columns**:

  * **IP Range**: Automatically calculates and displays the first and last IP address of each CIDR block.
  * **# IPs**: Computes the total number of addresses in each CIDR range.
* **Row management**:

  * Add new networks with the **Add Network** button.
  * Delete rows via the **Actions** column.
* **Column controls**:

  * Hide any column via the header menu.
  * Reveal hidden columns with **Show All Columns**.
* **Data persistence**:

  * **Export JSON** to download current table data.
  * **Load JSON** to import and restore a previously saved dataset.

### Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/hmblprogrammer/cidr-sheet.git
   cd cidr-sheet
   ```
2. Open `index.html` in any modern browser (no build step required).
3. Use the controls at the top to add, remove, hide/show columns, and import/export JSON files.

### Development

* The main application code is in `index.html`, which sets up the Tabulator table on page load.
* Helper functions (`parseCidr`, `formatIpRange`, `countIps`) calculate IP ranges and counts.
* Prompts used during AI-assisted development are included in Git commit messages for transparency.

### Contributing

1. Fork the repository and create a new branch for your feature or bugfix.
2. Commit your changes with clear messages referencing the relevant prompt or issue.
3. Submit a pull request for review.

## Data Model

Each network row contains the following fields:

- **name** *(string)*: A human-friendly name for the network (e.g., `"Office LAN"`).
- **region** *(string)*: Physical site or region (e.g., `"Building A"` or `"AWS us-east-1"`).
- **location** *(string)*: Sub-location within the region (e.g., floor, room, or availability zone).
- **cidr** *(string)*: The network block in CIDR notation (e.g., `"10.0.1.0/24"`).
- **vlan** *(integer)*: VLAN ID associated with the network.
- **status** *(enum)*: One of `In use`, `Deprecated`, `Legacy`, `Decommissioned`, `Proposed`, or `Future State`.
- **description** *(string)*: Freeform text description of the network.
- **tags** *(string, comma-delimited)*: Arbitrary tags (e.g., `"core,prod"`).
- **ip\_range** *(string, computed)*: Calculated first and last IP in the CIDR block (e.g., `"10.0.1.0 - 10.0.1.255"`).
- **num\_ips** *(integer, computed)*: Number of IP addresses in the CIDR block.

### Example JSON File

```json
[
  {
    "name": "Office LAN",
    "region": "Building A",
    "location": "Floor 1",
    "cidr": "10.0.1.0/24",
    "vlan": 10,
    "status": "In use",
    "description": "Office network",
    "tags": "core,prod",
    "ip_range": "10.0.1.0 - 10.0.1.255",
    "num_ips": 256
  },
  {
    "name": "AWS Default VPC",
    "region": "AWS us-east-1",
    "location": "us-east-1a",
    "cidr": "172.31.0.0/16",
    "vlan": 0,
    "status": "In use",
    "description": "AWS default VPC",
    "tags": "aws,default",
    "ip_range": "172.31.0.0 - 172.31.255.255",
    "num_ips": 65536
  }
]
```


### Credits

* **Maintained by:** Josh Gitlin ([@hmblprogrammer](https://github.com/hmblprogrammer))
* **AI-assisted Development:** Prompts and code iterations powered by OpenAI ChatGPT.

---

Feel free to open issues or pull requests for enhancements and fixes. Happy IP management!
