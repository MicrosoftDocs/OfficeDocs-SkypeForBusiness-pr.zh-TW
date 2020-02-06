---
title: 啟動服務 (叫用)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployStartServicesInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 7992440b-8545-4af9-b3ac-ea200b9de084
ROBOTS: NOINDEX, NOFOLLOW
description: '[執行命令] 窗格上的 [摘要] 窗格會顯示所頒發之任務的狀態，以啟動您要部署之商務用 Skype Server 角色服務器的服務。'
ms.openlocfilehash: 50d161c024b7e85e995cdde407ec380125e5b318
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794622"
---
# <a name="start-services-invoke"></a><span data-ttu-id="8289d-103">啟動服務 (叫用)</span><span class="sxs-lookup"><span data-stu-id="8289d-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="8289d-104">[**執行命令**] 窗格上的 [摘要] 窗格會顯示所頒發之任務的狀態，以啟動您要部署之商務用 Skype server 角色服務器的服務。</span><span class="sxs-lookup"><span data-stu-id="8289d-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="8289d-105">工作窗格中的摘要並不代表服務會即時啟動。</span><span class="sxs-lookup"><span data-stu-id="8289d-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="8289d-106">某些商務用 Skype Server 服務可能需要較長的時間才能開始初始啟動程式。</span><span class="sxs-lookup"><span data-stu-id="8289d-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="8289d-107">工作會發出啟動命令，但不會等候以判斷服務是否成功啟動。</span><span class="sxs-lookup"><span data-stu-id="8289d-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="8289d-108">如果您必須監視服務啟動和服務狀態，則應該使用 Windows 服務 Microsoft Management Console (MMC)。</span><span class="sxs-lookup"><span data-stu-id="8289d-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="8289d-p102">工作窗格底下有一個顯示 [啟動服務] \*\*\*\* 記錄檔的下拉式清單。若要檢視記錄檔，請按一下 [檢視記錄檔]\*\*\*\*。按一下 [完成] \*\*\*\* 完成工作。</span><span class="sxs-lookup"><span data-stu-id="8289d-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

