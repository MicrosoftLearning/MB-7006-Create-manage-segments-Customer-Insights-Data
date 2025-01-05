---
lab:
    title: 'Lab 1: Ingest datasets'
---

# Lab 1: Ingest datasets
In this lab, you will learn how to:
- Bring in multiple datasets using PowerQuery
- Transform datasets and change column types
- Monitor import status

In order to create segments, we first need to import the data we will use in our segments. In this lab, we will import a few datasets as a prerequisite to unify the data and build our segments.

## Exercise 1: Ingest data sources
For this guided project, you will need to import various data sources. These data sources will be used in creating your unified customer profiles.

### Task 1: Ingest customer data from eCommerce Platform
1. In **Customer Insights - Data**, expand **Data** on the left navigation menu and select **Data sources**.

1. Select **+Add a data source**. View the available methods of ingesting data. For this lab, choose **Microsoft Power Query** and name the source **eCommerce**, then select **Next**.

1. You will be presented with a view of **Power Query data sources** that **Customer Insights** is able to ingest. Take note of the connector types available. Select the **Text/CSV connector**.

1. Enter `https://aka.ms/CI-ILT/Contacts` for **File path or URL** and select **Next**. It may take a few moments for the data to upload.

1. You should now see the data from the source tabulated. Select **Transform data** to configure the datatypes and formats for the data you ingest.

1. You will notice that the column heading has appeared in the first row of the data. To correct this, either select **Transform > Use first row as headers** from the **Home** tab or select the **Transform** tab and then **Use first row as headers**.

1. Because we have ingested data from a **Text/CSV source**, all columns are defaulted to a 'Text' **Data Type**. To successfully ingest and model the data, we can set the data type for non-text columns.

1. To change the data type, select the **ABC** icon on each column heading. Update the data type for these columns:
    - **DateOfBirth**: Date
    - **CreatedOn**: Date
    - **Income**: Currency

1. Verify the **Name** field on the **Query settings** pane is set to **Contacts**. Select **Next**.

1. Select **Refresh manually**, then select **Save**.

Congratulations. You have now successfully created your first data source with a data set! We'll continue importing the next data set in the next task.

### Task 2: Ingest customer data from Loyalty Scheme
1. In **Customer Insights**, expand **Data** on the left menu and select **Data sources**.

1. Select **+Add a Data Source** and choose **Microsoft Power Query** as the import method. Name the source **Loyalty**, then select **Next**.

1. Select the **Text/CSV connector**.

1. Enter `https://aka.ms/CI-ILT/LoyaltySchemeCustomers` for **File path or URL**, select **Next** and then select **Transform data**.

1. As before, select **Transform**, then **Use first row as headers**.

1. Update the data type for these columns:
    - **DateOfBirth**: Date
    - **RewardPoints**: Whole number
    - **CreatedOn**: Date

1. Rename this query to **Customers** in the **Query settings** pane and select **Next**.

1. Select **Refresh manually**, then select **Save**.

### Task 3: Ingest customer data from Point of Sale Purchases
1. In **Customer Insights**, expand **Data** on the left navigation menu and select **Data sources**.

1. Select **+ Add a data source**, choose **Microsoft Power Query** and name the source **PoS**, then select **Next**.

1. Select the **Text/CSV connector**.

1. Enter `https://aka.ms/CI-ILT/POSPurchases` for **File path or URL**. Select **Next** and then select **Transform data**.

1. As before, select **Transform**, then **Use first row as headers**.

1. Update the data type for these columns:
    - **PurchasedOn**: Date
    - **TotalPrice**: Currency
    - **RewardPointsAdded**: Whole number

1. In the **Name** field on the **Query settings** pane, rename the query to **Purchases**.

1. Select **Next**.

1. Choose **Refresh manually** and select **Save**.

### Task 4: Ingest Online Purchase Data
1. In this task, we will ingest **Online Purchase** data, representing purchases made via the **Contoso Coffee** website.

1. In **Customer Insights**, expand **Data** on the left menu and select **Data sources**. (Make sure the status of the **eCommerce** data source says **Successful**.)

1. Select the **eCommerce** data set you created in the first task and select **Edit**. (If your data is still refreshing, you will need to wait for it to finish before editing.)

1. Select **Next**. 

1. You should be presented with the **Power Query** view of the **eCommerce Contacts** data that you ingested in Task 1. On the **Home** tab, select **Get data**.

1. You will be presented with a view of data source connectors that **Customer Insights** is able to ingest. Select **Text/CSV**.

1. Enter `https://aka.ms/CI-ILT/OnlinePurchases` for **File path or URL** and select **Next**. Select **Create**.

1. As before, select **Transform**, then **Use first row as headers**.

1. Update the data types for the following columns:
    - **PurchasedOn**: Date
    - **TotalPrice**: Currency

1. Name this query **Purchases** and select **Save**.

**Important:** You will have to wait for the status of all your data sources to be **Successful** before you can advance to the next exercise.
