---
# required metadata

title: Troubleshoot Planning Optimization
description: This article describes how to fix issues that you might encounter while working with Planning Optimization.
author: t-benebo
ms.date: 01/30/2023
ms.topic: article
ms.prod: 
ms.technology: 

# optional metadata

ms.search.form: ReqCreatePlanWorkspace
# ROBOTS: 
audience: Application User
# ms.devlang: 
ms.reviewer: kamaybac
# ms.tgt_pltfrm: 
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9

---
# Troubleshoot Planning Optimization

[!include [banner](../../includes/banner.md)]

This article describes how to fix common issues that you might encounter while working with Planning Optimization.

## Installation of the Planning Optimization add-in doesn't complete

Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later. If you try to install the add-in on a OneBox environment, the installation won't complete.

**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).

## Installation of the Planning Optimization add-in fails due to user account issues

To install the add-in, you must sign in to your Microsoft Power Platform environment using an account with administrator privileges and an access mode of *Read-Write*. If you try to install the add-in using an account with insufficient permissions, you may see one of the following error messages:

> Current user does not have enough permission or missing licenses on Power platform environment to complete installation for Planning optimization. Consider changing user Access Mode to Read-write on Power platform admin center.

> Current user is not exist in Power platform environment. Please contact with your administrator to assign the user via Power platform admin center.

**Fix**: Set up your user account as described under *Prerequisites* in [Get started with master planning](get-started.md#prerequisites).

## Planning of batch jobs fails when Planning Optimization is enabled

When you enable Planning Optimization, the deprecated master planning engine is automatically disabled. Master planning batch jobs that were created for the deprecated master planning engine will fail if they are triggered while Planning Optimization is enabled. You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.

**Fix**: Cancel all master planning batch jobs that were created for the deprecated master planning engine.

## Planning Optimization results are different from earlier results

Planning Optimization differs from the deprecated master planning engine design in some areas. This can also be caused by pending features.

**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact. For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).

## Can't enable Planning Optimization

The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**. For more information, see [Get started with Planning Optimization](get-started.md).

**Fix**: Make sure that the Planning Optimization add-in was installed successfully.

## Error message is shown during CTP

If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.

This is related to a pending feature that is planned as part of the support for production orders.

**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.

## Additional resources

- [Get started with master planning](get-started.md)
- [Planning Optimization fit analysis](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
