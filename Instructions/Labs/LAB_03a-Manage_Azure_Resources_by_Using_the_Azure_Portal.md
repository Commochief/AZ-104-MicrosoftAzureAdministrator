# Lab 03a - Manage Azure resources by Using the Azure Portal
# Student lab manual

## Lab scenario

You need to explore the basic Azure administration capabilities associated with provisioning resources and organizing them based on resource groups, including moving resources between resource groups. You also want to explore options for protecting disk resources from being accidentally deleted, while still allowing for modifying their performance characteristics and size.

**Note:** An **[interactive lab simulation](https://mslabs.cloudguides.com/guides/AZ-104%20Exam%20Guide%20-%20Microsoft%20Azure%20Administrator%20Exercise%204)** is available that allows you to click through this lab at your own pace. You may find slight differences between the interactive simulation and the hosted lab, but the core concepts and ideas being demonstrated are the same. 

## Objectives

In this lab, we will:

+ Task 1: Deploy resources to resource groups
+ Task 2: Move resources between resource groups
+ Task 3: Implement and test resource locks

## Estimated timing: 20 minutes

## Architecture diagram

![image](../media/lab03a.png)

## Instructions

### Exercise 1

#### Task 1: Deploy resources to resource groups

In this task, you will use the Azure portal to create a disk in a resource group.

1. Sign in to the [**Azure portal**](http://portal.azure.us).

1. In the Azure portal, search for and select **Disks**, click **+ Create** and specify the following settings:

    |Setting|Value|
    |---|---|
    |Subscription| the name of the Azure subscription you are using in this lab |
    |Resource Group| the name of your existing RG _[ex: rg1-az104-jsocstudent01]_ |
    |Disk name| **az104-03a-disk1** |
    |Region| **(US) USGov Virginia** |
    |Availability zone| **None** |
    |Source type| **None** |

    >**Note**: When creating a resource, you have the option of creating a new resource group or using an existing one. If using instructor-provided account, you will not have permission to create a new resource group.

1. Change the disk type and size to **Standard HDD** and **32 GiB**, respectively.

1. Click **Review + Create** and then click **Create**.

    >**Note**: Wait until the disk is created. This should take less than a minute.

#### Task 2: Move resources between resource groups 

In this task, we will move the disk resource you created in the previous task to a new resource group. 

1. Search for and select **Resource groups**. 

1. On the **Resource groups** blade, click the entry representing the resource group you deployed the disk to in the previous task _[ex: rg1-az104-jsocstudent01]_.

1. From the **Overview** blade of the resource group, in the list of resource group resources, select the entry representing the newly created disk, click **Move** in the toolbar, and, in the drop-down list, select **Move to another resource group**.

    >**Note**: This method allows you to move multiple resources at the same time. 

1. In the target **Resource group** text box, select the remaining resource group _[ex: rg2-az104-jsocstudent01]_. On the Review tab, select the checkbox **I understand that tools and scripts associated with moved resources will not work until I update them to use new resource IDs**, and click **Move**.

    >**Note**: You need to wait for the move to complete before proceeding to the next task. The move might take about 10 minutes. Now is a good time to stretch your legs and take a short break while the migration completes. You can determine that the operation was completed by monitoring activity log entries of the source or target resource group. 

#### Task 3: Implement resource locks

In this task, you will apply a resource lock to an Azure resource group containing a disk resource.

1. In the Azure portal, search for and select **Disks**, click **+ Create** and specify the following settings:

    |Setting|Value|
    |---|---|
    |Subscription| the name of the subscription you are using in this lab |
    |Resource Group| select your second resource group _[ex: rg2-az104-jsocstudent01]_ |
    |Disk name| **az104-03a-disk2** |
    |Region| USGov Virginia |
    |Availability zone| **None** |
    |Source type| **None** |

1. Set the disk type and size to **Standard HDD** and **32 GiB**, respectively.

1. Click **Review + Create** and then click **Create**.

1. Click **Go to resource**.

1. On the Overview page of the Disk, click the name of the resource group _[ex: rg2-az104-jsocstudent01]_.

1. On the resource group blade, click **Locks** then **+ Add** and specify the following settings:

    |Setting|Value|
    |---|---|
    |Lock name| **az104-03a-delete-lock** |
    |Lock type| **Delete** |
    
1. Click **OK**    

1. On the resource group blade, click **Overview**, in the list of resource group resources, select the entry representing the disk you created earlier in this task, and click **Delete** in the toolbar. 

1. When prompted **Do you want to delete all the selected resources?**, in the **Confirm delete** text box, type **yes** and click **Delete**.

1. You should see an error message, notifying about the failed delete operation. 

    >**Note**: As the error message states, this is expected due to the delete lock applied on the resource group level.

1. Navigate back to the list of resources of the resource group and click the entry representing the **az104-03a-disk2** resource. 

1. On the **az104-03a-disk2** blade, in the **Settings** section, click **Size + performance**, set the disk type and size to **Premium SSD** and **64 GiB**, respectively, and click **Resize** to apply the change. Verify that the change was successful.

    >**Note**: This is expected, since the resource group-level lock applies to delete operations only. 

#### Clean up resources

   >**Note**: Do not delete resources you deployed in this lab. You will be using them in the next lab of this module. Remove only the resource lock you created in this lab.

1. Navigate to the resource group blade, display its **Locks** blade, and remove the lock **az104-03a-delete-lock** by clicking the **Delete** link on the right-hand side of the **Delete** lock entry.

#### Review

In this lab, you have:

- Created resource groups and deployed resources to resource groups
- Moved resources between resource groups
- Implemented and tested resource locks
