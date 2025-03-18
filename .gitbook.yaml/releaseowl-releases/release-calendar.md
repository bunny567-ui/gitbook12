# Release Calendar

## **1. Release Process & Cadence**

The Release Process is a structured workflow followed to deploy new updates. It includes both the **Normal Release Process** and the **Hotfix Process**, governed by a clear **release cadence** to ensure efficient feature rollouts and system stability.

### **1.1 Release Cadence**

| **Type**           | **Purpose**                                            | **Frequency** |
| ------------------ | ------------------------------------------------------ | ------------- |
| **Major Releases** | New features, enhancements, significant changes.       | **Quarterly** |
| **Minor Updates**  | Bug fixes, performance improvements, security patches. | **Monthly**   |
| **Hotfixes**       | Critical bug fixes & urgent security patches.          | **As needed** |

### **1.2 Normal Release Process**

**Schedule**

* Releases occur **monthly**, typically on **Sundays(IST)**, to minimize business disruptions.
* Some releases may be **minor patches**, while others introduce **significant features and improvements**.

**Communication**

| **Communication Stage**      | **Details**                                                                                                                                                                                                    |
| ---------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Pre-Release Notification** | An email is sent to all existing customers **one week before** the scheduled release, informing them about upcoming changes and potential downtime.                                                            |
| **Post-Release Update**      | Once the release is successfully deployed, another email is sent with the **release notes**, detailing changes, enhancements, and any known issues.                                                            |
| **Data Migration**           | If required, data migration will be performed **automatically** during deployment. If **manual intervention** is necessary, affected customers will be notified with detailed steps for manual data migration. |

#### **Downtime**

* The deployment process results in **downtime ranging from 2 to 5 hours**, depending on the complexity of the update.
* Efforts are made to **minimize downtime** while ensuring a successful rollout.

### **1.3 Hotfix Process**

#### **Schedule**

* **Hotfixes** are deployed on the **same day or the next day** to minimize customer impact.

#### **Downtime**

* The deployment process results in **downtime ranging from 30 mins to 1 hour**, depending on the complexity of the update.

#### **Communication**

| **Communication Stage**         | **Details**                                               |
| ------------------------------- | --------------------------------------------------------- |
| **Pre-Deployment Notification** | Sent 4 **hours before deployment** to affected customers. |
| **Post-Deployment Update**      | Sent once the hotfix is successfully deployed.            |

***

### **1.4 Incident & Downtime Management**

#### **Incident Classification & Response Time**

| **Incident Type**                                 | **Impact**                                              | **Response Time**   | **Resolution Target**         |
| ------------------------------------------------- | ------------------------------------------------------- | ------------------- | ----------------------------- |
| **Critical (P1 - Service Outage, Major Issue)**   | Complete system failure, affecting all users.           | Immediate           | Resolution within **hours**   |
| **High (P2 - Partial Functionality Impacted)**    | Key functionality is unavailable but workaround exists. | Within **1 hour**   | Resolved within **24 hours**  |
| **Medium (P3 - Minor Bug, Workaround Available)** | Non-critical issues with limited impact.                | Within **24 hours** | Fixed in next Monthly Release |
| **Low (P4 - UI Fix, Minor Enhancements)**         | Cosmetic or minor functional issues.                    | Within **48 hours** | Scheduled in the roadmap      |

#### **Downtime Handling & Communication**

| **Action**                                  | **Details**                                                                   |
| ------------------------------------------- | ----------------------------------------------------------------------------- |
| **Real-time Monitoring**                    | Proactive monitoring to detect issues before they impact users.               |
| **Pre-Downtime Notification**               | Customers are notified in advance of scheduled maintenance and downtime.      |
| **Incident Status Updates**                 | Continuous communication via email and a status page.                         |
| **Post-Incident RCA (Root Cause Analysis)** | Detailed analysis and preventive measures are shared with affected customers. |

&#x20;
