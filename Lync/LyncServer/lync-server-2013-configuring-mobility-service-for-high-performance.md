---
title: Lync Server 2013： 設定高效能的 Mobility Service
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 460c56a9e51ab64491402eed22d40d60ad7d89c1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030527"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>設定 Lync Server 2013 中的高效能的 Mobility Service

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-17_

<div>


> [!IMPORTANT]  
> 本主題僅適用於 Lync Server 2013 行動性服務 (Mcx)，並不會套用至 Unified Communications Web API (UCWA)、 為 Lync Server 2013 累計更新中傳遞： 2 月 2013年。



</div>

當您安裝 Mobility Service (Mcx) 網際網路資訊服務 (IIS) 7.5 上時，Mobility Service 安裝程式會在前端伺服器上設定一些效能設定。 建議您使用 IIS 7.5 以用於行動性。 設定會影響最大並行使用者要求數目與所允許的 Mobility Service 的執行緒數目上限。

以下是效能設定：

<div>

## <a name="settings-for-mcx-on-iis-75"></a>在 IIS 7.5 Mcx 設定

1.  **maxConcurrentThreadsPerCPU**設為零 (0)。

2.  **maxConcurrentRequestsPerCPU**設為零 (0)。

3.  ASP.NET 處理序模型設為自動設定 （適用於僅使用 IIS 7.5)。

4.  HTTP.sys 佇列限制設為 1000 （預設）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

