---
title: Lync Server 2013：建立工作流程的案例概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc785392c50ea0ea1babe79ca5d30b455844ecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="d94a4-102">在 Lync Server 2013 中建立工作流程的案例概觀</span><span class="sxs-lookup"><span data-stu-id="d94a4-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d94a4-103">_**主題上次修改日期：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="d94a4-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="d94a4-104">當您建立工作流程時，有兩種可能的案例：</span><span class="sxs-lookup"><span data-stu-id="d94a4-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="d94a4-105">**系統管理員會建立並設定工作流程**— CsResponseGroupAdministrator 角色成員（或對等）會建立並啟用工作流程及工作流程中的所有元素，例如 [代理群組]、[佇列]、[假日與上班時間]、[等候音樂] 等等。</span><span class="sxs-lookup"><span data-stu-id="d94a4-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="d94a4-106">**系統管理員會建立工作流程，且**管理員會設定選項，例如，CsResponseGroupAdministrator 角色成員（或對等）會定義主要 SIP URI、顯示名稱、指派 CsResponseGroupManager 角色的成員或成員，並選取佇列並啟用工作流程。</span><span class="sxs-lookup"><span data-stu-id="d94a4-106">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow.</span></span> <span data-ttu-id="d94a4-107">CsResponseGroupManager 可接著建立代理群組，並將該群組指派給該佇列，然後將該群組指派給該隊，然後設定電話號碼、假日與上班時間、暫停音樂等。</span><span class="sxs-lookup"><span data-stu-id="d94a4-107">The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d94a4-108">當您想要建立受管理的工作流程時，您必須建立作用中的工作流程。</span><span class="sxs-lookup"><span data-stu-id="d94a4-108">When you want to create a managed workflow, you need to create the workflow as active.</span></span> <span data-ttu-id="d94a4-109">儲存使用中的受管理工作流程之後，您就可以修改及停用工作流程。</span><span class="sxs-lookup"><span data-stu-id="d94a4-109">After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

