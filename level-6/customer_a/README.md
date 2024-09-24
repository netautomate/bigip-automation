## Customer flow

### Step 1. Go to NetOrca Service Catalog, find a Service you want to request and get the example YAML definition.

> Service Catalogue is the place where you can find details for all the Services offered via NetOrca.
> There are 3 tabs in the Service Catalogue:
> - **README** - information about the Service provided by the Service Owner
> - **Schema** - detailed JsonSchema definition of the Service - you can look up the details for each property
> - **Example** - generator of yaml/json code for the Service

![step-1](../images/level6_demo_step1.gif)

### Step 2. Copy example Load Balancer service definition and request it via your Customer A GitLab repository.

> - In this step you will create a new branch, modify the example, create a merge request and watch the pipeline to pass.
> - Your requests will be sent to NetOrca and validated against Service definition.


#### Step 2.1 Validation successful

> - Once the pipeline is green, that meants the request is valid and can be merged to main branch.

![step-2](../images/level6_demo_step2.gif)

#### Step 2.2. Validation failed

> - In case of validation failure, you will see the error message in the pipeline logs. Most likely you didn't add required properties or made a typo.
> - You will need to fix the request and update merge request.


![step-2-1](../images/level6_demo_step2_1.gif)

### Step 3. Merge MR (Merge Request) into the main branch and watch the CI/CD pipeline to run.

> - After MR is merged, the Submission job will be triggered and changes will be pushed to NetOrca.
> - NetOrca will determine the type of change (CREATE/DELETE/MODIFY) and create a corresponding Change Instance.

#### Step 3.1. CREATE Change Instance
![step-3](../images/level6_demo_step3.gif)

#### Step 3.2. MODIFY Change Instance
![step-3-2](../images/level6_demo_step3_2.gif)

#### Step 3.3. DELETE Change Instance
![step-3-3](../images/level6_demo_step3_3.gif)

### Step 4. Check status of your requests live in NetOrca GUI.

> - At this stage, the responsibility for processing the customer request shifts to the Service Owner.
> - By default, the Change Instance will be in a PENDING state, awaiting approval from the Service Owner.
> - The APPROVED status indicates that the Service Owner has validated and approved the request.
> - The REJECTED status means that the Service Owner has rejected the request due to an issue.
> - The COMPLETED status indicates that the request has been successfully deployed on the BIG-IP system.

![step-4](../images/level6_demo_step4.gif)

