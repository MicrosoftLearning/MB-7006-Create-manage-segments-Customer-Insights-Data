---
lab:
    title: 'Lab 4: Create segments'
---

# Lab 4: Create segments

In this lab, you will learn how to:
- Create a segment from a profile
- Create a segment using measures
- Create a segment from scratch

## Exercise 1: Create segments from multiple sources 
### Task 1: Create segment from a profile
In this first task we are going create a segment based on the customer profile. We are going to identify any customers who reside in the state of Texas. 

1. Expand **Insights** and select **Segments** from the left navigation menu.

1. Select **+ New > Create from Profiles**.

1. For **Field**, select **State** and for **Value**, choose **Texas**.

1. Select **Review**.

1. Name the segment **Customers from Texas** and verify the **Output table name** has been automatically populated with **CustomersFromTexas**.

1. Select **Save**.

### Task 2: Create a segment using measures 
Contoso Coffee Marketing wants to run a new promotion. Based on historical data, marketing has identified that they wish to target brew-at-home customers with a higher-than-average online purchase value to do so. This time we are going to create the segment using the **Create from Measures** option. 

1. Select **Insights > Segments** from the left navigation menu.

1. Select **+ New > Create from Measures**.

1. Select the **Average Store Purchase ($)** attribute.

1. Set the **Operator** to **greater than**.

1. Set the **Value** to **100**. The graph should populate with **Average Web Purchase ($)** by percentile.

1. Select **Review**.

1. Name the segment **Premiere Customers** and verify the **Output table name** has been automatically populated with **PremiereCustomers**.

1. Select **Save**.

### Task 3: Create a segment from scratch
Every season, Contoso Coffee runs different promotions. This year, they want to run a Fall Closeout Promotion that is designed on selling the remaining year end models. They are looking to target Gen Xers with a higher than average in-store purchase with their newly launched Cold Brew Coffee. Since there are multiple criteria needed for this segment, we are going to create it from scratch.

1. Select **Insights > Segments** from the left navigation menu. Select **+ New > Build your own**.

1. Next to the **Untitled segment** header text, select **Edit details** and change the **Name** to **Fall Closeout Promotion**.

1. Verify the **Output entity name** has been automatically populated with **FallCloseoutPromotion** and select **Done**.

1. Using the **Add to Rule 1** pane on the right side of the screen, expand the **Customer : CustomerInsights** and select **DateofBitrh**. 

1. Select **is** and, **on or after** and enter the date as **1/1/1965**.

1. Add another condition with an **and** qualifier.

1. Set this condition as **DateOfBirth** is **on or before 12/31/1979**.

1. Add another condition with an **and** qualifier. 

1. Expand **Customer_Measure : CustomerInsights**.

1. Select the **Average Web Purchase ($)** measure and add it to **Rule 1**. 

1. Select **is** and **greater than or equal to 125**.

1. Add another condition with an **and** qualifier. 

1. In the **Enter an attribute name or add from panel** field, enter **Gender**, and select it from the list that appears. 

1. Select **is** and, **equal to male**.

1. Select the **Ignore case** check box.

1. Under **Rule 1**, select **+ Add Rule**. 

1. Select the **Union** box and change it to **Except**.

1. In the **Add to Rule 2** pane, expand **Customer : CustomerInsights**, and select **State**. 

1. Select **is** and **equal to Florida**.

1. Select **Save**.

1. Select **Run**.
