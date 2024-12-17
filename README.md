
# Multi-Region Disaster Recovery Setup

Implemented cross-region replication to maintain data availability during disasters.

## AWS Services
- S3
- Cross-Region Replication
## Key Achievements

- Enabled cross-region replication
- developed recovery strategies
- validated high-availability processes
## Steps

# **Step1: Create Two S3 Buckets**

1. **Primary Bucket**:
    - Go to the **AWS S3 Console**.
    - Click **Create Bucket** and name it (e.g., `my-primary-bucket`).
    - Select your **primary region** (e.g., `us-east-1`).
    - Enable **versioning** (this is required for replication).
2. **Secondary Bucket**:
    - Create another bucket in a different region (e.g., `us-west-1`).
    - Enable **versioning** for this bucket too.

# **Step2: Set Up Cross-Region Replication**

1. **Go to the Primary Bucket**:
    - Open your primary bucket in S3.
    - Go to the **Management tab** and click **Replication Rules**.
    - Click **Create Replication Rule**.
2. **Set Up the Rule**:
    - Name the rule (e.g., `replication-rule`).
    - Choose to replicate the **entire bucket** or specific folders.
    - Select your **secondary bucket** as the destination.
3. **Allow AWS to Create Permissions**:
    - AWS will ask to create an IAM role for replication.
    - Click **Create Role** and let AWS handle the permissions.
4. **Save and Enable the Rule**.

# **Step3: Test the Setup**

1. **Upload a File**:
    - Add a file to your primary bucket.
2. **Check the Secondary Bucket**:
    - Go to your secondary bucket in the other region.
    - Verify that the file was copied automatically.
## Image

![DR Implementation Architecture](https://i.ibb.co/H21yKTF/Figure-2-DR-implementation-architecture-on-multi-Region-active-passive-workloads.png)
