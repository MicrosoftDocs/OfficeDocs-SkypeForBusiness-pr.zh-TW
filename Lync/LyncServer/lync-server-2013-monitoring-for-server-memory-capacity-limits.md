---
title: Lync Server 2013：監視伺服器記憶體容量限制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring for server memory capacity limits
ms:assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689982(v=OCS.15)
ms:contentKeyID: 48183506
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5c9746240335b1c66606da24edf6ffa2a0e7bda
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>監視 Lync Server 2013 中的伺服器記憶體容量限制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> 本主題中參照容量規劃的資訊，只適用于 Lync 2010 行動用戶端和行動服務（Mcx）。 Lync 2013 行動用戶端所使用之整合通訊網頁 API （UCWA）的容量規劃是由 Lync Server 2013、規劃工具所提供。



</div>

兩個行動性效能計數器可協助您判斷您目前的使用量，並協助您規劃 Lync Server 2013 行動服務（Mcx）的容量，以及監視 UCWA 的記憶體使用量。 若是 UCWA，計數器類別是**LS： WEB – UCWA**。 針對行動服務（Mcx），計數器位於類別**LS： WEB Mobile 通訊服務**。 要監視的計數器包括：

  - **目前使用中的目前狀態訂閱的目前活動會話計數**，也就是透過 UCWA 或行動服務（Mcx）提供作用中的目前狀態訂閱（永不連線的行動使用者數目）

  - 目前使用中的**會話計數**，是透過 UCWA 或行動服務註冊的目前端點數目

如果**目前使用中的目前狀態訂閱與**目前的**活動會話計數**之間的差異在一段時間內很小，這表示大多數行動裝置使用者都有一個永不連線的裝置，例如 Android 或 Nokia 行動裝置（僅適用于 Mcx）。 UCWA [永不連線的裝置] 包括執行 Lync 2013 行動用戶端的 Apple 和 Android 裝置。 如果**目前的活動會話計數**比目前使用中**的目前狀態訂閱**要高許多，這表示您的使用者使用的是背景端點裝置，例如 Apple iOS 裝置或 Mcx 下的 Windows Phone。 （Windows Phone 是唯一的 Lync 2013 行動用戶端，會以這種方式註冊）。

您應該根據預期使用量、容量規劃結果，以及持續監視行動服務與其他前端伺服器計數器，來針對**目前使用中的會話計數**以及**目前的活動會話計數**效能計數器來設定限制。 您設定的限制應該能讓您評估伺服器容量，並在超過容量時引發警示。

若要判斷適當的限制，您必須先決定可在行動服務的前端伺服器上使用多少記憶體。 根據下列公式監視計數器，以判斷您何時需要規劃額外的容量：

Mcx 行動服務（MB）所使用的記憶體總量 = 164 + （400 + 134）/1024 \* **目前使用中的目前狀態訂閱的會話數**+ 400 \* /1024 （目前作用中**的**會話**計數**與作用中的目前狀態訂閱）

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 容量計算機是預先填入了所有公式的試算表，可讓 planner 判斷伺服器的需求，包括 CPU、記憶體及硬碟。 您可以在下列網址下載試算表及相關聯的檔：<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

前端伺服器需要足夠的可用記憶體，才能在容錯移轉情況下支援行動服務。 您可以使用**\\記憶體可用的 mb**計數器，或使用先前所述的方程式來規劃預期行動服務所要使用的記憶體量，來監視前端伺服器上目前可用的記憶體。

如果在您規劃預期的行動使用者數量時，前端伺服器上可用的記憶體量低於 1500 MB，您需要新增更多硬體來支援行動服務。 如需詳細資訊，請參閱在作業檔中[監視 Lync Server 2013 的效能行動](lync-server-2013-monitoring-mobility-for-performance.md)。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中監控行動能力以提高效能](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

