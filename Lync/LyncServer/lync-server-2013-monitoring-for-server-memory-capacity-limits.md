---
title: Lync Server 2013：監控伺服器記憶體容量限制
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
ms.openlocfilehash: 160d90a5a79291d18afdab00c23ff0a6726fa5b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531940"
---
# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>在 Lync Server 2013 中監控伺服器記憶體容量限制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> 本主題所述的容量規劃的資訊僅適用于 Lync 2010 行動用戶端和行動服務 (Mcx) 。 Lync Server 2013 （計畫工具）提供的整合通訊網頁 API (UCWA) （供 Lync 2013 行動用戶端使用）的容量規劃。



</div>

兩個行動性效能計數器可協助您判斷目前的使用狀況，並協助您規劃 Lync Server 2013 行動性服務的容量 (Mcx) ，以及監視 UCWA 的記憶體使用量。 針對 UCWA，計數器類別為 **LS： WEB – UCWA**。 針對行動服務 (Mcx) ，計數器位於類別 **LS： WEB Mobile Communication Service**。 要監視的計數器包括：

  - **目前使用中的會話計數與使用中狀態訂閱**，這是透過 UCWA 所註冊的端點數目，也就是具有使用中狀態訂閱的行動 (服務) ， (永不連線的行動使用者數目) 

  - 目前使用中的**會話計數**，也就是透過 UCWA 或行動性服務註冊的目前端點數目

如果 **目前使用中狀態訂閱** 和目前作用中的會話計數之間的差異， **目前的會話計數** 很小，這表示大多數行動裝置使用者都有一個永不連線的裝置，例如 Android 或 Nokia mobile Device (僅限 Mcx) 。 UCWA always 連裝置，包括執行 Lync 2013 行動用戶端) 的 Apple 和 Android 裝置。 如果目前作用中的 **會話計數** 比 **目前使用中狀態訂閱目前使用中的會話計數**高，這表示有更多使用者在 Mcx 下使用背景端點裝置，例如 Apple IOS 裝置或 Windows Phone。  (Windows Phone 是唯一會註冊為此) 的 Lync 2013 行動用戶端。

您應該根據預期的使用量、容量規劃結果，以及即時監控行動性服務和其他前端伺服器計數器，來設定目前作用中的 **會話計數與使用中狀態訂閱** 及目前使用中 **會話計數** 效能計數器的限制。 您設定的限制應可讓您評估伺服器容量，並在超出容量時引發警示。

若要判斷適當的限制，您必須先決定可在行動服務的前端伺服器上使用多少記憶體。 根據下列公式，監視計數器，以判斷何時需要規劃額外的容量：

Mcx 行動服務使用的總記憶體 (MB) = 164 + (400 + 134) /1024 目前作用中 \* **的會話計數與使用中的目前狀態訂閱** + 400/1024 (目前作用中的 \* **會話計數** – **目前使用中狀態訂閱的主動會話計數**) 

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 容量計算機是預先填入的試算表，其可讓規劃人員判斷伺服器的需求（包括 CPU、記憶體和硬碟）。 您可以在下列位置下載試算表和相關聯的檔： <A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

前端伺服器需要足夠的可用記憶體，以在容錯移轉的情況下支援行動性服務。 您可以使用 **可用記憶體（ \\ mb** ）計數器（或先前所述的方程式）來監視前端伺服器上目前可用的記憶體，以規劃預期行動服務所要使用的記憶體量。

若當您規劃預期的行動使用者數目時，前端伺服器上可用的記憶體量低於 1500 MB，您需要新增更多硬體以支援行動性服務。 如需詳細資訊，請參閱 Operations 檔中的 [監控在 Lync Server 2013 中的行動性效能](lync-server-2013-monitoring-mobility-for-performance.md) 。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中監控行動性以取得效能](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

