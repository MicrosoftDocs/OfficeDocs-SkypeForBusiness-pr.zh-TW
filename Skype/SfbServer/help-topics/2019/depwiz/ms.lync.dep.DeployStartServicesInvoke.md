---
title: 啟動服務 (叫用)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '[執行命令] 窗格上的 [摘要] 窗格會顯示所發佈之工作的狀態，以啟動您要部署之商務用 Skype Server 角色服務器的服務。'
ms.openlocfilehash: 34e128fd5c879c80e3e3eb242cd654b19c5f6dd3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808773"
---
# <a name="start-services-invoke"></a><span data-ttu-id="9483f-103">啟動服務 (叫用)</span><span class="sxs-lookup"><span data-stu-id="9483f-103">Start Services (Invoke)</span></span>
 
<span data-ttu-id="9483f-104">[ **執行命令** ] 窗格上的 [摘要] 窗格會顯示所發佈之工作的狀態，以啟動您要部署之商務用 Skype server 角色服務器的服務。</span><span class="sxs-lookup"><span data-stu-id="9483f-104">The summary pane on the **Executing Commands** pane displays the status of the tasks issued to start the services for the Skype for Business Server role server that you are deploying.</span></span> <span data-ttu-id="9483f-105">工作窗格中的摘要並不代表服務會即時啟動。</span><span class="sxs-lookup"><span data-stu-id="9483f-105">The summary in the task pane does not represent a real-time indication of service startup.</span></span> <span data-ttu-id="9483f-106">部分商務用 Skype Server 服務可能要花很長的時間來開始初始啟動程式。</span><span class="sxs-lookup"><span data-stu-id="9483f-106">Some of the Skype for Business Server services may take an extended time to begin the initial startup process.</span></span> <span data-ttu-id="9483f-107">工作會發出啟動命令，但不會等著去看服務是否成功啟動。</span><span class="sxs-lookup"><span data-stu-id="9483f-107">The tasks are issuing the command to start, but do not wait to determine if the service is successfully started.</span></span> <span data-ttu-id="9483f-108">如果您必須監視服務啟動和服務狀態，則應該使用 Windows 的服務 Microsoft Management Console (MMC)。</span><span class="sxs-lookup"><span data-stu-id="9483f-108">If you must monitor the service startup and service status, you should use the Windows Services Microsoft Management Console (MMC).</span></span>
  
<span data-ttu-id="9483f-p102">工作窗格底下有一個顯示 [啟動服務] 記錄檔的下拉式清單。若要檢視記錄檔，請按一下 [檢視記錄檔]。按一下 [完成] 完成工作。</span><span class="sxs-lookup"><span data-stu-id="9483f-p102">Under the task pane is a drop-down list that displays the **Start Services** log file. To view the log file, click **View Log**. Click **Finish** to complete the task.</span></span>
  

