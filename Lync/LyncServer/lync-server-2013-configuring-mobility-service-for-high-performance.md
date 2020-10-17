---
title: Lync Server 2013：設定行動服務以取得高效能
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
ms.openlocfilehash: 9d587444dfd1fbe4fae8898438a51bc9cfb2b5ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526950"
---
# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>在 Lync Server 2013 中設定高效能的行動服務

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-17_

<div>


> [!IMPORTANT]  
> 本主題只適用于 Lync Server 2013 行動服務 (Mcx) ，而且不會套用至「整合通訊 Web API (UCWA) ，但在 Lync Server 2013 的累計更新中已傳遞：2月2013。



</div>

當您在網際網路資訊服務 (IIS) 7.5 上安裝行動服務 (Mcx) 時，行動性服務安裝程式會在前端伺服器上設定某些效能設定。 建議您使用 IIS 7.5 以用於行動性。 這些設定會影響並行使用者要求數目上限，以及行動性服務所允許的執行緒數目上限。

效能設定如下：

<div>

## <a name="settings-for-mcx-on-iis-75"></a>IIS 7.5 上的 Mcx 設定

1.  **maxConcurrentThreadsPerCPU** 設定為零 (0) 。

2.  **maxConcurrentRequestsPerCPU** 設定為零 (0) 。

3.  ASP.NET 進程模型設定為僅) IIS 7.5 的自動設定 (。

4.  HTTP.sys 佇列限制預設設定為 1000 () 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

