# python-OKRs1-statistics
This repository contains python clients to generate statistics about the total CPU/h and the number of users of the EGI Federated Infrastructure. 
Specifically, the statistics generated by these clients are:
- **Cloud CPU/h** consumed by the production VOs of EGI
- **HTC CPU/h** consumed by the production VOs of EGI
- Num. of **'active'**, **'total'** and **'actual' users** registered in the EGI Operations Portal. 

The statistics generated by these clients will be pushed in a Google Worksheet using the <a href="https://docs.gspread.org/en/v5.10.0/">gspread</a> API.
