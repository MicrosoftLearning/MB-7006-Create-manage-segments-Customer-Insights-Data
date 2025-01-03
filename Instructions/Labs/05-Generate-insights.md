---
lab:
    title: 'Lab 5: Generate insights'
---

# Lab 5: Generate insights 

In this lab, you will learn how to:
- Generate insights about your segments 
- View differentiators and overlap between segments 
- Build suggested segments based on a segment 

## Exercise 1: Generate insights on your segments
### Task 1: Segment differentiators
Often, you will have customers that exist in multiple segments. It can be helpful to understand when you might have overlap between them. Let's try to find out common customers that belong to both **Customers from Texas** and **Fall close out Promotion** segments and also what differentiates both of these segments in terms of **Reward points** and **LifetimeSpend**.

1. Select **Insights > Segments** from the left navigation menu. Select the **Insights (preview)** tab and select **+ New** from the command bar, or select the **+ New insight** button.

1. You will now see two options. Let's create using **Differentiators** first to see what distinguishes both of these segments. Select **Differentiators**.

1. Choose **Fall Closeout Promotion** as the primary segment. Select **Next**.

1. Choose **Customers from Texas** as another segment, and then select **Next**.

1. Now choose **Reward points** under **Customer fields** and **LifetimeSpend** under **Measure fields** to see how the above segments differ from each other with respect to **Reward points** and **LifetimeSpend**. Clear all other customer and measure fields.

1. Select **Next** and name the insight **Fall Promotion vs Customers from Texas**.

1. Verify the **Output entity name** gets set to **FallPromotionvsCustomersfromTexas**. Select **Save**.

1. After the insight finishes refreshing, open the created insight. Select the **Attributes** or **Measures** tabs to see how the segments differ from each other with respect to the fields you selected. Observe the **Difference score**, which signifies the degree of difference. The higher the score, the more different they are.

1. Select each measure and attribute to see deeper insights.

### Task 2: Segment overlap
Now that we have successfully created a Segment insight using **Differentiators**, let's create an insight using **Overlap**.

1. Make sure you're still in the **Segments > Insights (preview)** tab and select **+ New** from the command bar. Choose **Overlap**.

1. Select both **Fall Closeout Promotion** and **Customers from Texas** segments to find out their shared customers.

1. Select **Next**.

1. Name the Segment **Fall Promotion Customers Overlapped with Texas Customers** and verify the **Output table name** is set to **FallPromotionCustomersOverlappedwithTexasCustomers**. Select **Save**.

1. After the insight finishes refreshing, open the created insight to see the venn diagram showing the total and percentage of shared customers between these two segments.

## Exercise 2: Segment expansion and suggested segments
### Task 1: Segment expansion
Segment Expansion can be used to find similar customers to your segment customer base using Artificial Intelligence. Earlier we created a segment called **Fall Promotion Customers**, which contains millennial customers with higher than average in-store purchase. Now, let's expand that segment and find customers that are similar to them for us to market our newly launched Cold Brew Coffee.

1. Select **Insights > Segments** from the left navigation menu and select the **All segments** tab.

1. Choose the **Fall Promotion Customers** segment. This will become our source segment.

1. Select **Find similar customers** from the command bar.

1. Name your segment **FallPromoExpansion**.

1. Select **Add fields** in the next step to select attributes and measures that are used to find similar customers. We'll target customers with similar location and average in-store purchase, so choose **PostCode** and **AverageStorePurchase**. Select **Apply**.

1. Next you must choose who to consider. For now, select **All customers except source segment**.

1. Now the maximum number of customers to include must be selected. Let's stick with **20%**.

1. If you would like to include members from the source segment as well then check the last option. Otherwise, leave it unchecked. For our purposes, we can leave it unchecked.

1. Select **Run**.

1. After the segment finishes refreshing, open the segment to find the **Similarity Scores** and explore the **Segment members preview**.

### Task 2: Get suggested segments 
Use Suggested Segments to discover interesting segments based on a customer attribute or measure of interest.

1. Select **Insights > Segments** from the left navigation menu, and select the **Suggestions (preview)** tab.

1. Select **Get suggestions** to begin the configuration experience.

1. Choose **Improve a measure/metric** and select **Start**.

1. Under **Measure fields**, select **LifetimeSpend** as the target attribute. Select **Next**.

1. Next, you will select the attributes that might influence the target attribute (**LifetimeSpend**) so the AI model can find interesting patterns between the influencing and target attribute. The model will suggest segments based on those patterns. Select **Email Subscriber**, **Income**, **Loyalty Tier**, **Occupation** and **State** as the influencing attributes.

1. Select **Run**. The AI model will start finding patterns between the selected influencing attributes and target attributes to surface segment suggestions. Please wait for a few minutes for the model to finish its analysis.

1. Once the model has finished running and if it is able to uncover patterns between the influencing attributes and the target attribute, segment suggestions will be displayed under the **Suggestions (preview)** tab.

1. To save the segment, select **Save as segment** in the **Suggested segment details** panel. Select **Save**.

1. The saved segment can then be viewed under the **All segments** tab and it can be used for downstream processes like any other dynamic segment. If you wish to look at the rules that the model learned after saving a segment, you can do so by selecting **Edit** in the **All segments** tab.
