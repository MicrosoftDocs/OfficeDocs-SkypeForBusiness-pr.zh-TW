---
title: Lync Server 2013： 工作流程建立案例概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27383db13176150078bf4855dee4df57cb1615af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="c1a16-102">Lync Server 2013 中的工作流程建立案例概觀</span><span class="sxs-lookup"><span data-stu-id="c1a16-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1a16-103">_**主題上次修改日期：** 2012年-10-17_</span><span class="sxs-lookup"><span data-stu-id="c1a16-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="c1a16-104">當您建立工作流程時，有兩種可能的情況：</span><span class="sxs-lookup"><span data-stu-id="c1a16-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="c1a16-105">**系統管理員建立及設定工作流程** - CsResponseGroupAdministrator 角色成員 (或同等權限) 建立及啟動工作流程和工作流程中的所有元素，例如代理群組、佇列、假日和上班時間、等候音樂等。</span><span class="sxs-lookup"><span data-stu-id="c1a16-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="c1a16-p101">**系統管理員建立工作流程，而一般管理員設定選項** - CsResponseGroupAdministrator 角色成員 (或同等權限) 定義主要 SIP URI、顯示名稱，指派一或多個 CsResponseGroupManager 角色成員，以及選取佇列並啟動工作流程。然後，CsResponseGroupManager 會登入並編輯工作流程設定，包括建立代理群組、將群組指派給佇列，以及設定電話號碼、假日和上班時間、等候音樂等。</span><span class="sxs-lookup"><span data-stu-id="c1a16-p101">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow. The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1a16-p102">當您想建立受管理的工作流程時，您必須建立並啟動工作流程。儲存作用中的受管理工作流程之後，即可修改及停用工作流程。</span><span class="sxs-lookup"><span data-stu-id="c1a16-p102">When you want to create a managed workflow, you need to create the workflow as active. After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

