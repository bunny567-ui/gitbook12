# Parallel Landscape Configuration

In system landscapes, in which several releases are processed at the same time, changes can be made in different development systems. New developments can be made in the development system, and error corrections/improvements can be made in a maintenance system for the production system landscape at the same time. You can register the two landscapes and enable retrofit between the maintenance and development landscapes so that changes made in the maintenance landscape can be ported to the development landscape.

<figure><img src="../../.gitbook/assets/image (1187).png" alt=""><figcaption></figcaption></figure>

When you need to perform a major piece of work in a development system, you should create a parallel landscape in which this piece of work can be done independently of the maintenance changes. This separates the project activities and the maintenance ones. As a result, you can minimize conflicts.\
Maintenance changes are deployed to Production during project development. If these changes get downgraded or removed when the project is finally deployed, they need to be merged into the project track so that it remains at the same state as that of the Production system. This process of merging is known as **retrofit**.

All transportable ABAP and customizing objects can be retrofitted. This includes fully automated retrofit resolution in case no conflict arises. However, in case the conflicts arise, you will have to manually identify and track the changes.\
The level of automation that retrofit allows is important to note as it makes your process quicker and more efficient.

**Retrofitting allows you to:**

* **Track and analyse:** Each transport request needs to be retrofitted. All released transport requests and included objects are automatically captured and analyzed for conflicts between the involved systems.
* **Execution:** The transfer of content and replication is easily and automatically done with the click of a button.
* **Post Processing:** The retrofitted content will be recorded in a transport request in the target system automatically.

By simply using retrofit instead of manually looking for and making changes, then testing to ensure no overwriting, the developer team can save up to **30 minutes on average for each transport**. It also reduces the risk of human error and maintains a much higher level of compliance and consistency.

You can enable the **retrofit option in ReleaseOwl** in the **Transport Domain Controller** screen.

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
