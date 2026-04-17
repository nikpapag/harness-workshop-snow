### Approvals via ServiceNow Change Requests

**1.** Hover before the **frontend** stage and click on the **+** icon that appears to add a new stage.

**2.** Click **Use Template**

**3.** Select the **SNOW Approval** template and click on **Use Template** in the lower right corner.

**4.** Name it `ServiceNow Approval` and click **Set Up Stage**.

> **Note:** Make sure you name it `ServiceNow Approval` as we will add steps later that reference this stage.

**5.** This template has been preconfigured for us, so there are no inputs necessary

**6.** Click on the **Overview** toggle to see the steps in this template. 

**7.** Click on the **Create Ticket** or **Approval** steps to see how they are configured and notice how you, as a template user, cannot change the configuration for this enterprise-approved template — only the template administrator can make changes. Click the **X** or **Discard** once you're done reviewing.

> **Note:** Notice the use of Harness Expressions to dynamically populate our tickets and approvals.

**8.** Save the pipeline. No violations this time, hooray for compliance!

![ServiceNow Approval](images/lab5-add-approval.gif "ServiceNow Approval")

> **Bonus:** Add a step to close the ServiceNow ticket after the last step of the **backend** stage, indicating that we've successfully deployed to production. *Hint: there's a template already created.*

---
