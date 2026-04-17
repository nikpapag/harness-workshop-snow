# Artifact Validation
## SCS Lab - Generate SBOM and SLSA
1. Add the "SBOM Orchestration" step


| Input           | Value           | Notes |
| --------------- | --------------- | ----- |
| Name      |SBOM Orchestration|       |
| Provider  |Docker Registry |  Use **Third-Party**     |
|Image | nikpap/harness-workshop:<+variable.username>-1 |     |
| Private Key  |SBOM Private Key |      |
|Password | SBOM Password |     |


## SCS Lab - Sign Artifact
1. Add the "Artifact Signing" step
   
| Input           | Value           | Notes |
| --------------- | --------------- | ----- |
| Name      |SBOM Orchestration|       |
| Provider  |Docker Registry |  Use **Third-Party**     |
|Image | nikpap/harness-workshop:<+variable.username>-1 |     |
| Private Key  |SBOM Private Key |      |
|Password | SBOM Password |     |


## SCS Lab - Verify the signature

1. Navigate to the frontend stage
2. Add a step group before every other step

<img width="238" height="185" alt="image" src="https://github.com/user-attachments/assets/904ba67f-778a-4bf1-b763-e9d69be71244" />



3. Name **Artifact Validation**
4. **Enable container based execution**
5. Select the k8s cluster
6. Expand optional configuration

| Input           | Value           | Notes |
| --------------- | --------------- | ----- |
| Namespace      |{{lab id}}-ns| **Ask the instructor for more details** |
   
7. **Apply Changes**

8. Within the step group add step and select **Artifact Verification**
9. Configure accordingly 


| Input           | Value           | Notes |
| --------------- | --------------- | ----- |
| Name      |Artifact Verification|       |
| Provider  |Docker Registry |  Use **Third-Party**     |
|Image | nikpap/harness-workshop:<+variable.username>-1 |     |
| Public Key  |SBOM Public Key |      |



# Service Now

### Prerequisites

**1.** In the pipeline create a new variable **backend_version** and give it a value of v1

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
