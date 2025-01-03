---
lab:
    title: 'Lab 3: Create measures'
---

# Lab 3: Create measures

In this lab, you will learn how to:
- Define business measures to track business performance and health
- Define customer measures to gain insights about individual customers

## Exercise 1: Define business measures
### Task 1: Average value of in-store purchases
In this first task, we will create a measure to define the average value of all in-store purchases made at **Contoso Coffee**.

1. Expand **Insights** and select **Measures** from the left navigation menu.

1. Select **+ New** from the toolbar, then select **Build your own**.

1. Next to the **Untitled measure** header text, select **Edit details**.

1. Set the **Name** to **Average Store Purchase Value ($)** and select **Done**.

1. Toggle **Measure type** from **Customer** to **Business.**

1. Next to **Calculation 1**, select **Edit name**.

1. Set the **Name** to **Average Store Purchase Value ($)**.

1. Verify the **Output attribute name** is set to **AverageStorePurchaseValue**.

1. Select **Done**.

1. Under the **Average Store Purchase Value ($)** calculation, choose **Average** from the **Select function** drop-down.

1. Select **+ Add attribute**, expand **Purchases : PoS**, and select **TotalPrice**.

1. Select **Add**.

1. Select the **Run** button to complete your measure.

In this next task, we will create a measure to define the Average value of all web purchases made at **Contoso Coffee**.

1. Select **Insights > Measures** from the left navigation menu.

1. Select **+ New > Build your own** from the toolbar.

1. Next to the **Untitled measure** header text, select **Edit details**.

1. Set the **Name** to **Average Web Purchase Value ($)** and select **Done**.

1. Toggle **Measure type** from **Customer** to **Business**.

1. Next to **Calculation 1**, select **Edit name**.

1. Set the **Name** to **Average Web Purchase Value ($)**.

1. Verify the **Output attribute name** is set to **AverageWebPurchaseValue**.

1. Select **Done**.

1. Under the **Average Web Purchase Value ($)** calculation, choose **Average** from the **Select function** drop-down.

1. Select **+ Add attribute**, expand **Purchases : eCommerce**, and select **TotalPrice**.

1. Select **Add**.

1. Select the **Run** button to complete your measure.

## Task 2: Define customer measures
We will need two customer measures that can be used to calculate a customer attribute. We will create one measure to determine the customers' total spend on **Online Purchases** and one measure to determine their total spend on **In-Store purchases**. Once we create these, we can then create a customer attribute to add those two together.

In this task, we will create a measure to define the total of all purchases made in-store.

1. Select **Insights > Measures** from the left navigation menu.

1. Select **+ New > Build your own** from the toolbar.

1. Next to the **Untitled measure** header text, select **Edit details**.

1. Set the **Name** to **Total In Store Spend** and select **Done**.

1. Under the **Total In Store Spend** calculation, choose **Sum** from the **Select function** drop-down.

1. Select **+ Add attribute**, expand **Purchases : PoS**, select **TotalPrice**, and select **Add**.

1. To set up the measure calculation, select **Dimensions (1)**.

1. Select **Edit Dimensions**.

1. Expand **Purchases : PoS**, select **LoyaltyId**, and select **Done**.

1. Select **Apply**.

1. Select the **Run** button to complete your measure. If you encounter an error and need to choose the **Relationship path**, select **PoS_Purchases > Customer** and select the **Run** button to complete.

Next, we will create a measure to define the total of all purchases made online.

1. Select **Insights > Measures** from the left navigation menu.

1. Select **+ New > Build your own** from the toolbar.

1. Next to the **Untitled measure** header text, select **Edit details**.

1. Set the **Name** to **Total Online Spend**, select **Done**.

1. Under the **Total Online Spend** calculation, choose **Sum** from the **Select function** drop-down.

1. Select **+ Add attribute**, expand **Purchases : eCommerce**, select **TotalPrice** and click **Add**.

1. Under **Set up your measure calculations**, select **Dimensions (1)**.

1. Select **Edit dimensions**.

1. Expand **Purchases : eCommerce**, select **ContactId**, and select **Done**.

1. Select **Apply**.

1. Select the **Run** button to complete your measure.

### Task 3: Define customer attributes 
First, we will define **Total Loyalty Points** earned by each customer.

1. If necessary, select **Insights > Measures** from the left navigation menu.

1. Select **+ New > Build your own** from the toolbar.

1. Next to the **Untitled measure** header text, select **Edit details**.

1. Set the **Name** to **Total Club Points** and select **Done**.

1. Under the **Total Club Points** calculation, choose **Sum** from the **Function Type** drop-down.

1. Select **+ Add attribute**, expand **Purchases : PoS**, select **RewardPointsAdded** and select **Add**.

1. Select the **Run** button to complete your measure.

Next, we will define the total value of all purchases made for each customer.

1. Select **Insights > Measures** from the left navigation menu.

1. Select **+ New > Build your own** from the toolbar.

1. Next to the **Untitled measure** header text, select **Edit details**.

1. Set the **Name** to **Lifetime Spend ($)** and select **Done**.

1. Under the **Lifetime Spend ($)** calculation, choose **Sum** from the **Function type** drop-down.

1. Select **+ Add attribute**.

1. Select the **Measures** tab, expand **TotalInStoreSpend : CustomerInsights**, select **Calculation 1**, and select **Add**.

1. Select the **+ (Plus sign)** to add a plus sign after the attribute you just added. The plus sign should appear in the calculation formula.

1. Select **+ Add attribute**.

1. Select the **Measures** tab, expand **TotalOnlineSpend : CustomerInsights**, select **Calculation 1**, and select **Add**.

1. Your completed measure will resemble the image below:

1. Select the **Run** button to complete your measure.

Next, we will define the average value of all store purchases made for each customer.

1. Select **Insights > Measures** from the left navigation menu.

1. Select **+ New > Build your own** from the toolbar.

1. Next to the **Untitled measure** header text, select **Edit details**.

1. Set the name to **Average Store Purchase ($)** and select **Done**.

1. Under the **Average Store Purchase ($)** calculation, choose **Average** from the **Select function** drop-down.

1. Select **+ Add attribute**, expand **Purchases : PoS**, select **Total Price**, and select **Add**.

1. Select the **Run** button to complete the measure.

### Task 4: Average value of web purchases
Next, we will define the average value of all web purchases made for each customer.

1. If necessary, select **Measures** from the left navigation menu.

1. Select **+ New > Build your own** from the toolbar.

1. Next to the **Untitled measure** header text, select **Edit details**.

1. Set the name to **Average Web Purchase ($)** and select **Done**.

1. Under the **Average Web Purchase ($)** calculation, choose **Average** from the **Select function** drop-down.

1. Select **+ Add attribute**, expand **Purchases : eCommerce**, select **Total Price** and select **Add**.

1. Select the **Run** button to complete your measure.
