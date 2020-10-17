---
title: Lync Server 2013：設定回應群組
description: Lync Server 2013：設定回應群組。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547929"
---
# <a name="configuring-response-group-in-lync-server-2013"></a>在 Lync Server 2013 中設定回應群組

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

回應群組是一種企業語音功能，可將來電路由及列隊給一組人 *（稱為「* 服務台」，例如「服務台」或「客戶服務台」）。

「回應群組」所需的元件，會在您部署企業語音時自動安裝於前端伺服器或 Standard Edition Server 上並啟用。 若要讓使用者能夠使用「回應群組」，您必須依序設定專員群組、佇列和工作流程。 此外，回應群組管理員可以將現有工作流程的設定委派給回應群組管理員，然後該管理員可以修改及重新設定工作流程及其相關聯的代理人群組和佇列。

本節會引導您完成 Lync Server 2013 回應群組的設定。 它假設您已閱讀與回應群組相關的規劃區段，並已部署 Enterprise Edition server 或 Standard Edition server 與 Enterprise Voice。

<div>


> [!TIP]  
> 如需使用 Lync Server 管理命令介面（包括範例腳本）建立回應群組的詳細資訊，請參閱「使用 Lync Server 管理命令介面建立第一個回應群組」 <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> 。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [Lync Server 2013 的回應群組設定許可權和必要條件](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Lync Server 2013 中回應群組的部署程式](lync-server-2013-deployment-process-for-response-group.md)

  - [Lync Server 2013 中的工作流程建立案例概述](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [建立回應群組代理群組 Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [在 Lync Server 2013 中建立回應群組佇列](lync-server-2013-create-response-group-queues.md)

  - [ (選用) 在 Lync Server 2013 中定義回應群組上班時間](lync-server-2013-optional-define-response-group-business-hours.md)

  - [ (選用) 在 Lync Server 2013 中定義回應群組假日集](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [在 Lync Server 2013 中建立回應群組工作流程](lync-server-2013-create-response-group-workflows.md)

  - [ 在 Lync Server 2013 中 (選用) 驗證回應群組部署](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃通話管理功能](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

