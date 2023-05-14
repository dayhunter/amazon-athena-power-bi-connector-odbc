# Config Microsoft Power BI to connect with Amazon Athena

## Prerequisite
1. [AWS account](https://aws.amazon.com/)
2. [Permissions to use Athena](https://docs.aws.amazon.com/athena/latest/ug/policy-actions.html)
3. [Power BI desktop](https://powerbi.microsoft.com/en-us/desktop/)
    
---
## Instruction

### 1. Amazon Athena ODBC driver


#### 1.1 Download and install Amazon Athena ODBC driver

Download on this [link](https://docs.aws.amazon.com/athena/latest/ug/connect-with-odbc.html)

<img src="./images/athena-driver.png" width=30%/>

Install Amazon Athena ODBC driver

<img src="./images/athena-driver-install.png" width=30%/>

#### 1.3 Setup ODBC Data Sources

Search for `ODBC Data Sources`

<img src="./images/odbc-search.png" width=20%/>

On `System DNS` tab then click `Add...`

<img src="./images/odbc-add.png" width=30%/>

Select Name `Simba Athena ODBC Driver` then click `Finish`

<img src="./images/odbc-add-finish.png" width=30%/>

On `Simba Athena ODBC Driver DSN Setup` Input following information

Data Source Name: `MyTestDataSource` (Your Data Source Name)

AWS Region: `us-east-1`

S3 Output Location: `s3://<S3-BUCKET>/`

then click `Authentication Options...`

<img src="./images/odbc-add-dsn-setup.png" width=30%/>

Authentication Type: `IAM Credentials`

User: `<AWS_ACCESS_KEY_ID>` (Your AWS Access Key ID)

Password: `<AWS_SECRET_ACCESS_KEY>` (Your AWS Secret Access Key)

Session Token: `<AWS_SESSION_TOKEN>` (Your AWS Session Token)

then click `OK`

Test connection by click `Test...`

<img src="./images/odbc-add-dsn-authen-test.png" width=30%/>

Message shows `SUCESS!` then click `OK`

<img src="./images/odbc-add-dsn-authen-success.png" width=30%/>

Click `OK` to finish setup ODBC Data Source

<img src="./images/odbc-add-dsn-authen-finish.png" width=30%/>

---

### 2. Power BI

#### 2.1 Get data

Open `Power BI`. In `Home` tab, click `Get data`

<img src="./images/powerbi-get-data.png" width=30%/>

Search for `Athena` and click `Connect`

<img src="./images/powerbi-get-data-search.png" width=30%/>

DSN: `MyTestDataSource` (Your Data Source Name)

Data Connectivity mode: `DirectQuery`

Click `OK`

<img src="./images/powerbi-get-data-athena.png" width=30%/>

Select `Use Data Source Configuration` then click `Connect`

<img src="./images/powerbi-get-data-athena-connect.png" width=30%/>

Navigator will show up then expand datasource, database, and select table then click `Load`

<img src="./images/powerbi-get-data-athena-table.png" width=50%/>

On `Visualizations` tab, select `Table`

On `Data` tab, select column that you want to show

You will notice that data is showing on dashboard.

<img src="./images/powerbi-get-data-athena-dashboard.png" width=70%/>

---