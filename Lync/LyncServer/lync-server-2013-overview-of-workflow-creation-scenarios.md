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
ms.openlocfilehash: 888c7f0e1d3d3659edbdca71b0386e043b0642a3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Lync Server 2013 中的工作流程建立案例概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-17_

當您建立工作流程時，有兩種可能的情況：

  - **系統管理員建立及設定工作流程** - CsResponseGroupAdministrator 角色成員 (或同等權限) 建立及啟動工作流程和工作流程中的所有元素，例如代理群組、佇列、假日和上班時間、等候音樂等。

  - **系統管理員建立工作流程，而一般管理員設定選項** - CsResponseGroupAdministrator 角色成員 (或同等權限) 定義主要 SIP URI、顯示名稱，指派一或多個 CsResponseGroupManager 角色成員，以及選取佇列並啟動工作流程。然後，CsResponseGroupManager 會登入並編輯工作流程設定，包括建立代理群組、將群組指派給佇列，以及設定電話號碼、假日和上班時間、等候音樂等。
    
    <div>
    

    > [!NOTE]  
    > 當您想建立受管理的工作流程時，您必須建立並啟動工作流程。儲存作用中的受管理工作流程之後，即可修改及停用工作流程。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

