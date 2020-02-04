---
title: Lync Server 2013：建立工作流程的案例概觀
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
ms.openlocfilehash: 08ecb210ea937184039587d289c5c9c57cb4fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>在 Lync Server 2013 中建立工作流程的案例概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

當您建立工作流程時，有兩種可能的案例：

  - **系統管理員會建立並設定工作流程**— CsResponseGroupAdministrator 角色成員（或對等）會建立並啟用工作流程及工作流程中的所有元素，例如 [代理群組]、[佇列]、[假日與上班時間]、[等候音樂] 等等。

  - **系統管理員會建立工作流程，且**管理員會設定選項，例如，CsResponseGroupAdministrator 角色成員（或對等）會定義主要 SIP URI、顯示名稱、指派 CsResponseGroupManager 角色的成員或成員，並選取佇列並啟用工作流程。 CsResponseGroupManager 可接著建立代理群組，並將該群組指派給該佇列，然後將該群組指派給該隊，然後設定電話號碼、假日與上班時間、暫停音樂等。
    
    <div>
    

    > [!NOTE]  
    > 當您想要建立受管理的工作流程時，您必須建立作用中的工作流程。 儲存使用中的受管理工作流程之後，您就可以修改及停用工作流程。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

