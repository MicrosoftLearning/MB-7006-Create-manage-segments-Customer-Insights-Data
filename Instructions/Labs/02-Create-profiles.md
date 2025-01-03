In this unit, you will learn how to:
- Merge data from your raw data sources into a customer profile
- Select a primary key 
- Create match rules
- Define search and filter indexes and activities

Your objective is to find out how many unique customer profiles **Contoso Retail** has across various data sources.

## Map contacts into common data types
1. Sign into **Customer Insights - Data**.

1. On the left navigation menu, expand **Data**, select **Unify**. Select **Get started**.

1. Choose **Select tables and columns**.

1. Select the tables that represent the customer profile - **Contacts (eCommerce)** and **Customers (Loyalty)**. Select **Apply**.

1. You will now be presented with the mappings of your source table against standard model types. You can review the types in the table.

1. You must choose a **'Primary Key'** for each entity you have ingested. The primary key must be a unique reference. For **eCommerce Contacts**, select **ContactId** as the primary key.

1. The **eCommerce Contacts** data contains a column named **Email Subscriber** which will be mapped to an incorrect type, **Identity.Service.Email**, because of the name. Open the drop-down for this column and select the empty option (nothing/blank). If we do not do this then the default system behavior is to merge this field with the **EMail** field which we do not want.

1. Select **Loyalty Customers** under **Tables** and set **LoyaltyId** as the primary key.

1. Select **Save source columns** in the top left-hand corner.

1. Select **Next** and **Next** again, to skip the duplicate checking and move on to the **Matching rules** step.

## Specify match order
1. For the next stage, we must select the order in which to merge the profiles. You will be able to merge attributes to ensure that the unified profiles are complete as well as the priority of which sources to use for those attributes.

1. You should select the most complete or accurate profile source as the **Primary (first) source**. Verify **Contacts : eCommerce** is the primary (first) source.

1. Verify that **Customers : Loyalty** is the second source in the list. 

1. Verify that **Include all records** is checked for both data sources.

## Create a match rule
1. There is a warning indicator on the **Customers : Loyalty** line. Select **+ Add rule**.

1. Add the first condition using **FullName**:
    - For the **Contacts : eCommerce** table, select the **FullName** field.
    - For the **Customers : Loyalty** table, select the **FullName** field.
    - Leave the **Normalize** drop-down blank.
    - Set the **Precision Level** to **Basic**.
    - Set the **Precision Value** to **Exact** using the slider.
    - Enter the name **FullName, Email** for the **Rule Name**.

1. Add a second condition for email address by selecting **+ Add** and selecting **Add condition**.
    - For the **Contacts : eCommerce** table, select the **EMail** field.
    - For the **Customers : Loyalty** table, select the **EMail** field.
    - Leave the **Normalize** drop-down blank.
    - Set the **Precision Level** to **Basic**.
    - Set the **Precision Value** to **Exact**.

1. Select **Done**.

1. Select **Next**.

1. On the **Unified data view** screen, we will not be making any changes. Select **Next** to move to the review screen.

1. On the **Review** screen, select **Create customer profiles**. Customer Insights is now matching customer data from all your sources of customer information to identify how many unique customer profiles you would have based on your rules. It can take some time to create the profiles.

Congratulations! You have successfully unified data from multiple sources within **Customer Insights** to create a **Unified Customer Profile** that can be used to gain insights into your whole customer base.

## Configure search columns and filter index 
In this task, we will set up **search and filter** criteria to enable Customer Insights users to search for unified customer profiles.

1. In **Customer Insights**, select **Customers** from the left navigation menu.

1. Select **Search & filter index**. Some fields are already added by default. Select **+Add** from the toolbar.

1. Select **CustomerId, FirstName, LastName, FullName, DateOfBirth, EMail, PostCode, ContactId (eCommerce_Contacts), and LoyaltyId** (if they are not already selected). Deselect any other fields that are checked. Select **Apply**.

1. Select **Save**.

1. Select **Run**.

1. In **Customer Insights**, select **Customers** from the left navigation menu. You should be presented with a set of customer cards, representing the **Unified Profiles**. You can expand cards to see more about the customer or sort the cards by various fields. Try this by selecting **Expand cards** and **Sort by** on the toolbar.

1. You can use **Search customers** to search for text attributes relating to unified customer profiles. (E.g. Searching '1' will search against all text attributes and return matches and partial matches.)

## Create activities
1. In **Customer Insights**, expand **Data > Activities** on the left navigation menu and select **+ Configure activities**.

1. Click **Select tables**.

1. Select the **Purchases : eCommerce** and **Purchases : PoS** tables and select **Add**.

1. For **Purchases : eCommerce**, configure as follows:
    - Set the **Activity type** to **SalesOrder**.
    - Set the **Primary key** to **PurchaseId**.

1. For **Purchases : PoS**, configure as follows:
    - Set the **Activity type** to **SalesOrder.**
    - Set the **Primary key** to **PurchaseId.**

1. Select **Next.**
    -
1. Configure **eCommerce : Purchases** as follows:
    - Enter **OnlinePurchase** for **Activity name**.
    - Fill out the following fields (for any fields not mentioned, leave blank):
        - **Timestamp**: PurchasedOn
        - **Event activity**: ActivityTypeDisplay
        - **Additional detail**: Subject
        - **Show this activity in the timeline on your customer profile?** Yes
        - **Icon**: Select the shopping bag.
        - **Set Map field types for your activity’s attributes?** Yes, and configure as follows:
            - **Sales order ID**: PurchaseID
            - **Order date**: PurchasedOn
            - **Sales amount**: TotalPrice

1. Configure **PoS : Purchases** as follows:
    - Enter **PoSPurchase** for **Activity name**.
    - Fill out the following fields (for any fields not mentioned, leave blank):
        - **Timestamp**: PurchasedOn
        - **Event activity**: ActivityTypeDisplay
        - **Additional detail**: Subject
        - **Show this activity in the timeline on your customer profile?** Yes
        - **Icon**: Select the shopping bag.
        - **Set Map field types for your activity’s attributes?** Yes, and configure as follows:
            - **Sales order ID**: PurchaseID
            - **Order date**: PurchasedOn
            - **Sales amount**: TotalPrice

1. Select **Next**.

1. On the **Configure activity relationships** screen, with **eCommerce : Purchases** selected, select **+ Add relationship**.

1. In the **Add relationship path** pane, set the following values:
    - **Foreign key**: ContactId
    - **To table name**: Contacts : eCommerce
    - **Relationship name**: eCommPurchasesToContacts
    - Select **Apply.**

1. Select **PoS : Purchases.** Select **+ Add relationship**.

1. In the **Add relationship path** pane, set the following values:
    - **Foreign key**: LoyaltyId
    - **To table name**: Customers : Loyalty
    - **Relationship name**: PoSPurchasesToLoyalty
    - Select **Apply**.

1. Select **Next.**

1. Select **Create activities.**

1. Wait while the **Activities** refresh and unify.



