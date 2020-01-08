---
title: Lync Server 2013：管理回應群組
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39c0d8ac0fbfa8464fd0cd078fc90784eb9fdd3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a>在 Lync Server 2013 中管理回應群組

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2018-02-01_

[回應群組] 是通話管理功能，可讓您將對特定區域所做的通話排隊（例如問訊台），然後將呼叫傳送給指定的人員群組（稱為 [*代理*]）。

若要管理回應群組，您需要設定代理群組、佇列和工作流程，以定義從所設定的時間開始，直到工程師回答它。

<div>


> [!NOTE]  
> 如果您在回應群組部署的單一池中有超過300個工作流程，最好是使用 Lync Server 管理命令介面 Cmdlet 來建立工作流程。 如果您使用 [回應群組設定] 工具來為擁有超過300個工作流程的池子建立工作流程，則會花費很長的時間來載入網頁。 透過佇列間接與工作流程相關聯的代理程式數量在頁面載入上也會有成比例的效果。



</div>

本節中的主題提供可執行檔工作逐步程式，以在您的部署中自訂及維護回應群組應用程式

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中管理回應群組代理群組](lync-server-2013-managing-response-group-agent-groups.md)

  - [在 Lync Server 2013 中管理回應群組佇列](lync-server-2013-managing-response-group-queues.md)

  - [在 Lync Server 2013 中管理回應群組工作流程](lync-server-2013-managing-response-group-workflows.md)

  - [管理 Lync Server 2013 中的應用層級回應群組設定](lync-server-2013-managing-application-level-response-group-settings.md)

  - [在 Lync Server 2013 中將回應群組移至新的文件庫](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [在災害期間使用 Lync Server 2013 管理回應群組](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

