---
title: Lync Server 2013： 監控伺服器記憶體容量限制
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
ms.openlocfilehash: 46580950c30326bb9852abc5ecb2a165398b3587
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-for-server-memory-capacity-limits-in-lync-server-2013"></a>監控的 Lync Server 2013 中的伺服器記憶體容量限制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-12-08_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<div>


> [!WARNING]  
> 容量規劃是指此主題中的資訊只各與 Lync 2010 Mobile 用戶端和行動性服務 (Mcx)。 Lync Server 2013 規劃工具會提供容量規劃的 Unified Communications Web API (UCWA)、 Lync 2013 行動用戶端使用。



</div>

兩個行動效能計數器可協助您判斷您目前的使用量，並協助您規劃容量 Lync Server 2013 行動性服務 (Mcx)，以及想 UCWA 監視記憶體使用量。 Ucwa 的參考，該計數器類別是**LS:WEB – ucwa 的參考**。 Mobility Service (Mcx) 的計數器可**LS:WEB-行動通訊服務**] 類別底下。 計數器可監視如下：

  - 透過 ucwa 的參考，或是有作用中的目前狀態訂閱 （自動連線的行動使用者數目） 的行動性服務 (Mcx) 登錄**Currently Active Session Count with Active Presence Subscriptions**]，這是目前的端點數目

  - 透過 UCWA 或 Mobility Service 登錄**Currently Active Session Count**]，這是目前的端點數目

如果**Currently Active Session Count with Active Presence Subscriptions**和**Currently Active Session Count**之間的差異是小型經過一段時間，這表示大部分的行動裝置使用者具有總是連線裝置，例如 Android 或 Nokia 行動裝置 （適用於僅 Mcx)。 UCWA 總是連線的裝置包括執行 Lync 2013 行動用戶端的 Apple 和 Android 裝置）。 如果**Currently Active Session Count**是遠高於**Currently Active Session Count with Active Presence Subscriptions**，這表示更多使用者會使用背景端點裝置，例如 Apple iOS 裝置或 Windows Phone Mcx 底下。 （在 Windows Phone 是唯一的 Lync 2013 行動用戶端，會註冊為這）。

您應該根據您預期的使用狀況、 容量規劃的結果，並持續監控 Mobility Service 和其他前端伺服器計數器的**Currently Active Session Count with Active Presence Subscriptions**及**Currently Active Session Count**效能計數器設定限制。 您所設定的限制應該能夠讓您評估伺服器容量，當容量不足時會引發警示。

若要決定適當的限制，您需要先判斷多少記憶體使用的 Mobility Service 的前端伺服器上。 監視計數器，以決定當您需要額外容量計劃根據下列公式：

總記憶體使用 Mcx 行動性服務 (MB) = 164 + (400 + 134) / 1024年\* **Currently Active Session Count with Active Presence Subscriptions** ] + 400 / 1024年\*(]**Currently Active Session Count** – [ **Currently Active Session Count with Active Presence Subscriptions**)

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2010 Capacity Calculator 是預先填入所有啟用至判斷需求將會針對伺服器，包括 CPU、 記憶體及硬碟 planner 公式的試算表。 您可以下載試算表和相關文件：<A href="https://go.microsoft.com/fwlink/p/?linkid=212657">https://go.microsoft.com/fwlink/p/?LinkID=212657</A>



</div>

前端伺服器所需記憶體不足，無法在容錯移轉情況中支援 Mobility Service。 您可以監視前端伺服器上目前可用的記憶體使用**記憶體\\Available Mbytes**計數器，或使用先前所述，若要規劃您預計要使用的行動性服務的記憶體量的方程式。

如果在前端伺服器上可用的記憶體量低於 1500 MB 計劃的預期的行動使用者數目時，您需要新增更多的硬體，以支援 Mobility Service。 如需詳細資訊，請參閱作業文件中的[Lync Server 2013 的效能監控行動性](lync-server-2013-monitoring-mobility-for-performance.md)。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 的效能監控行動性](lync-server-2013-monitoring-mobility-for-performance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

