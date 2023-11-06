# OKRs

This repository contains python clients to produce statistics that can be
used by EGI Foundation team to identify trends and monitor progress following
the **Objectives and Key Results (OKRs)** goal-setting framework.

* **Cloud CPU/h** consumed by the production VOs of EGI
* **HTC CPU/h** consumed by the production VOs of EGI
* Num. of **'Registered'**, **'Total'** and **'Active'** users of the production
  - Registered users = Number of users registered into the registries (VOMS, COManage, Perun) not necessarily active.
  - Total users = Number of users registered in the DB since the 1st. capture for a given VO.
* VOs registered in the [EGI Operations Portal](https://operations-portal.egi.eu/)
* Num. of VOs registered in the [EGI Operations Portal](https://operations-portal.egi.eu/) (in progress)
* Num. of **Service Orders (SOs)** received from the [EOSC Marketplace](https://marketplace.eosc-portal.eu/)

The statistics generated by these python clients will be pushed in a [Google Worksheet](https://docs.google.com/spreadsheets/d/1B1Sqf1UiN9pY_fGbWe5G1zKA2UzsekOVbLCtiiMFAXk) using the [gspread](https://docs.gspread.org/en/v5.10.0/) APIs

## Pre-requisites

* `Python 3.10.12+` installed on your local computer
* Install pip3: `apt-get install -y python3-pip`
* Install gspread API: `sudo pip3 install gspread`
* Install venv: `sudo apt install -y python3-venv`

## Creating a Google Service Account

In order to read from and write data to Google Sheets in Python,
we will have to create a **Google Service Account**.

**Instructions** to create a Google Service Account are the following:

* Head over to [Google developer console](https://console.developers.google.com/) and click on **Create Project**
* Fill in the required fields and click on **Create**
* Click on **Enable API and Services**
* Search for Google Drive API and click on **Enable**
* Search for the Google Sheets API and click on **Enable**
* Click on **Create Credentials**
* Select **Google Drive API** as the API and Web server
* Name the service account, then grant it a **Project** role with **Editor** access
* Click on **Continue**
* The credentials will be created and downloaded as a JSON file
* Copy the JSON file to your code directory and rename it to `credentials.json`

## Configuring the environment

Use virtualenv to configure the working environment:

```shell
]$ virtualenv -p /usr/bin/python3.10 venv
created virtual environment CPython3.10.12.final.0-64 in 1748ms
[..]

]$ source venv/bin/activate
```

Install the library `gspread` with pip3:

```shell
]$ pip3 install gspread
[..]
```

## Avaliable clients

This GitHub repository includes clients to generate:

* [The HTC and Cloud CPU/h of the production VOs of the EGI Federation](pyOKR_VOs_CPUs_Accounting)
* [The number of users in the production VOs of the EGI Federation](pyOKR_VOs_Users_Accounting)
* [The number of Services Orders (SOs) received throught the EOSC Marketplace](pyOKR_ServiceOrders_Accounting)
* [Report of the VOs created/leaving the EGI Operations Portal](pyOKR_VOs_Report)

## References

* [gspread APIs documentation](https://docs.gspread.org/en/v5.10.0/)
* [How to connect Python to GoogleSheets](https://blog.coupler.io/python-to-google-sheets/)
* [Google Developer Console](https://console.cloud.google.com/apis/dashboard)
* [Generate an API Token for the EGI Operations Portal](https://operations-portal.egi.eu/api-documentation)
* [Generate an API Token for the EGI Jira Portal](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)

## EGI services

* [EGI Operations Portal](https://operations-portal.egi.eu/)
* [EGI Accounting Portal](https://accounting.egi.eu/)
* [EGI Jira Portal](https://jira.egi.eu/)
