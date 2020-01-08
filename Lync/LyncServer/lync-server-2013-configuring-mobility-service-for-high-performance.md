---
title: Lync Server 2013：針對高效能配置行動服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54a1c9b901e9a861b40a5cfa8c2642e3e3e41ffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>在 Lync Server 2013 中設定行動服務以取得高效能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

<div>


> [!IMPORTANT]  
> 本主題僅適用于 Lync Server 2013 行動服務（Mcx），不適用於在 Lync Server 2013 的累積更新：年2月2013中提供的統一通訊 Web API （UCWA）。



</div>

當您在網際網路資訊服務（IIS）7.5 上安裝行動服務（Mcx）時，行動服務安裝程式會在前端伺服器上設定一些效能設定。 我們建議您使用 IIS 7.5 進行行動。 這些設定會影響並行使用者要求的數目上限，以及行動服務所允許的最大執行緒數。

以下是效能設定：

<div>

## <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上的 Mcx 設定

1.  **maxConcurrentThreadsPerCPU**已設定為零（0）。

2.  **maxConcurrentRequestsPerCPU**已設定為零（0）。

3.  ASP.NET 程式模型已設定為自動設定（僅適用于 IIS 7.5）。

4.  Http.sys 佇列限制設定為1000（依預設）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

