# Release Calendar

## **1. Release Process & Cadence**

The **Release Process** is a structured workflow followed to deploy new updates. It includes both the **Normal Release Process** and the **Hotfix Process**, governed by a clear **release cadence** to ensure efficient feature rollouts and system stability.

### **1.1 Release Cadence**

| **Type**           | **Purpose**                                            | **Frequency** |
| ------------------ | ------------------------------------------------------ | ------------- |
| **Major Releases** | New features, enhancements, significant changes.       | Quarterly     |
| **Minor Updates**  | Bug fixes, performance improvements, security patches. | Monthly       |
| **Hotfixes**       | Critical bug fixes & urgent security patches.          | As needed     |

***

### **1.2 Normal Release Process**

* **Schedule**:\
  Releases occur **monthly**, typically on **Sundays (IST)** to minimize business disruptions.
  * Some releases may be minor patches.
  * Others introduce significant features and improvements.
* **Communication**:

| **Communication Stage**      | **Details**                                                                                                                             |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| **Pre-Release Notification** | Email sent to all existing customers **one week before** the scheduled release with info about upcoming changes and potential downtime. |
| **Post-Release Update**      | Email sent **after successful deployment** with release notes detailing changes, enhancements, and known issues.                        |

* **Data Migration**:
  * Performed **automatically** during deployment.
  * If **manual intervention** is needed, affected customers will be **notified with detailed steps**.
* **Downtime**:
  * **2 to 5 hours**, depending on update complexity.
  * Efforts made to **minimize downtime** while ensuring successful rollout.

### **1.3 Hotfix Process**

* **Schedule**:\
  Deployed **same day or next day** to minimize customer impact.
* **Downtime**:
  * **30 mins to 1 hour**, depending on complexity.
* **Communication**:

| **Communication Stage**         | **Details**                                               |
| ------------------------------- | --------------------------------------------------------- |
| **Pre-Deployment Notification** | Sent **4 hours before deployment** to affected customers. |
| **Post-Deployment Update**      | Sent **after successful hotfix deployment**.              |

### **1.4 Incident & Downtime Management**

* **Incident Classification & Response Time**:

| **Incident Type** | **Impact**                                        | **Response Time** | **Resolution Target**         |
| ----------------- | ------------------------------------------------- | ----------------- | ----------------------------- |
| **Critical (P1)** | Complete system failure, affecting all users.     | Immediate         | Resolution within hours       |
| **High (P2)**     | Key functionality unavailable, workaround exists. | Within 1 hour     | Resolved within 24 hours      |
| **Medium (P3)**   | Non-critical issues with limited impact.          | Within 24 hours   | Fixed in next Monthly Release |
| **Low (P4)**      | Cosmetic or minor functional issues.              | Within 48 hours   | Scheduled in the roadmap      |

* **Downtime Handling & Communication**:

| **Action**                    | **Details**                                                                      |
| ----------------------------- | -------------------------------------------------------------------------------- |
| **Real-time Monitoring**      | Proactive monitoring to detect issues before they impact users.                  |
| **Pre-Downtime Notification** | Customers notified **in advance** of scheduled maintenance/downtime.             |
| **Incident Status Updates**   | Continuous communication via **email and a status page**.                        |
| **Post-Incident RCA**         | **Root Cause Analysis** with preventive measures shared with affected customers. |
