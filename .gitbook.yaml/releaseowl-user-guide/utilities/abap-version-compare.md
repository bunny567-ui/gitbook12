# ABAP Version Compare

ABAP Compare is used to compare any differences between objects under different systems which might help the developer to see if there is any missing part in objects of ReleaseOwl Project.

### To compare objects in ReleaseOwl:&#x20;

1\. Expand Utilities in project view and click on ABAP Compare section

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2\. Select the **Compare System** from which objects needs to be compared.\


<figure><img src="../../.gitbook/assets/image (1202).png" alt=""><figcaption></figcaption></figure>

3\. Add systems against which the above selected system needs be compared.

<figure><img src="../../.gitbook/assets/image (1204).png" alt=""><figcaption></figcaption></figure>

4\. There are three options provided on what to be included while comparing the objects

* Include Non-Versioning Objects -> if Non version object also needs to be included while comparison, check this option.
* Include DOCU Objects -> If DOCU/Internationalization (i18n) of the objects needs to be included while comparison, then check this option
* Include Object only in compare system -> Check this option when objects which present in compare system are available.\


<figure><img src="../../.gitbook/assets/image (1205).png" alt=""><figcaption></figcaption></figure>

5\. In Compare section, select what object needs to be compared. Here three options have been provided

* All Customer Objects -> Select this if you want to compare all non-SAP objects
* All Modified SAP Object -> Select this if only modified SAP Object needs to be compared
* Objects from Package -> Select this if specific package needs to be compared\


<figure><img src="../../.gitbook/assets/image (1206).png" alt=""><figcaption></figcaption></figure>

* If Object from Package is selected, provide a package in package input.\


<figure><img src="../../.gitbook/assets/image (1207).png" alt=""><figcaption></figcaption></figure>

* After providing all the required details, the screen will be as shown below:\


<figure><img src="../../.gitbook/assets/image (1208).png" alt=""><figcaption></figcaption></figure>

6\. Once all the required selections are made, click compare button to get the comparison data.

7\. Once the comparison is done, data can be seen as follows:\


<figure><img src="../../.gitbook/assets/image (1209).png" alt=""><figcaption></figcaption></figure>

8\. Expand to the object to view the comparison. \


<figure><img src="../../.gitbook/assets/image (1213).png" alt=""><figcaption></figcaption></figure>

9\. The objects with green check icon are identical, means there is no difference in between the objects.

<figure><img src="../../.gitbook/assets/image (1215).png" alt=""><figcaption></figcaption></figure>

10\. The objects with red cross icons have no version in either of the compared systems\


<figure><img src="../../.gitbook/assets/image (1216).png" alt=""><figcaption></figcaption></figure>

11\. The object with yellow exclamation icon is not identical and have differences between the compared systems.

<figure><img src="../../.gitbook/assets/image (1217).png" alt=""><figcaption></figcaption></figure>

12\. To see the difference, click on the icon and the difference between the objects will be shown in a dialog.\


<figure><img src="../../.gitbook/assets/image (1218).png" alt=""><figcaption></figcaption></figure>

In a similar manner, you can compare different objects and see the difference side by side in the browser itself.
