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

### Credits

* **Maintained by:** Josh Gitlin ([@hmblprogrammer](https://github.com/hmblprogrammer))
* **AI-assisted Development:** Prompts and code iterations powered by OpenAI ChatGPT.

---

Feel free to open issues or pull requests for enhancements and fixes. Happy IP management!
