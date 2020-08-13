---
title: Lync Server 2013：監控簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of monitoring
ms:assetid: 5d5eb658-7fe0-42e6-acaf-700051d0a823
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204937(v=OCS.15)
ms:contentKeyID: 48184261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66dd239acbb274c7223363f1522f2d0c76590c37
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-monitoring-in-lync-server-2013"></a>Lync Server 2013 中的監控概覽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-05_

在 Microsoft Lync Server 2013 中，監控是用來收集使用狀況資訊和經驗品質 (QoE) 有關您的使用者所參與之通訊會話的資料。 會話是一個一般字詞，可涵蓋使用者對下列專案的連線：

  - 會議

  - 會議模態 (例如 Audio/Video 或應用程式共用) 

  - 透過對等交談（如立即訊息或音訊通話）的另一位使用者

<div>


> [!NOTE]  
> Lync Server 2013 保持追蹤每個會話的相關資訊：誰叫誰;會話中使用的端點此會話最後一段時間;會話的感知品質為何;等等。 不過，Lync Server 不會記錄和儲存實際通話。 包括立即訊息會話：雖然 Lync Server 記錄有關立即訊息會話的資訊，但不會維護會話期間所傳送之每個立即訊息的記錄。



</div>

Lync Server 所收集的通話詳細資訊可用於任何數量的使用，包括：

  - **投資回報 (ROI) **。 管理員可以比較監控伺服器所收集的流量資料與為先前的電話語音系統收集的類似資料，以顯示成本節約，並協助論證 Lync Server 的部署。

  - **裝置庫存管理**。 資產管理資訊可協助系統管理員識別仍在使用中但需要取代的舊裝置，以及識別根本不會取得使用的昂貴裝置。

  - 服務台。 疑難排解資料可讓技術人員判斷使用者呼叫失敗的原因，並在不需收集伺服器或用戶端記錄的情況下執行。 不具備 Microsoft Lync 2013 和 Lync Server 2013 相關技術知識的技術支援人員可輕鬆存取及瞭解此資訊。

  - **系統疑難排解**。 讓系統管理員能夠偵測到可能會讓使用者無法執行基本工作的主要問題，例如加入會議、建立通話或傳送立即訊息。

除了這項基本的呼叫資訊之外，監控伺服器也提供一種機制，允許 SIP 端點 (例如 Lync 2013) ，以提供伺服器不需要存取的疑難排解資訊：

  - **影響品質的媒體計量**。 這些計量與通話本身的實際傳輸有關：也就是說，它們會將旅行記錄的種類當做網路上的呼叫 journeys。 這些計量 (包含封包遺失、抖動和來回行程時間等專案。) 提供呼叫從您的端點移至到達其他人端點的時間的相關資訊。

  - **向使用者報告的問題**。 這些度量包含當使用者在電腦上的其他程式使用可用資源時，Lync 2013 對使用者顯示的品質很差的通知，因為其可能離麥克風太遠、過於柔和、網路連線或品質不良。

  - **環境資訊**。 這些指標詳細通話的品質因素，例如使用的麥克風和揚聲器類型、使用者是否透過 VPN 連線來連線，以及使用者是否位於無線連線。

在每次通話結束時，與 SIP 相容的端點會自動將此資訊傳送到進行呼叫的前端伺服器。 您不需要執行任何動作便可取得端點以傳輸該資訊;該行為是內置於 SIP 通訊協定中。 不過，如果您想要收集和儲存該資訊，則需要安裝並啟用監視。 如果您已安裝並啟用監控，則呼叫資訊會由前端伺服器上執行的代理程式所收集，並轉送至一對 SQL Server 資料庫。

請注意，在 Lync Server 2013 中已簡化安裝和設定監視的程式。 在舊版的軟體中，監控需要個別的監控伺服器角色，這通常是一組個別的電腦，用來做為監控伺服器。 不過，在 Lync Server 2013 中已消除監控伺服器角色。 相反地，「整合資料收集代理程式」 ) 的監控服務 (已組合至所有前端伺服器。 這至少有兩個主要優點。 監控服務的組合：

  - 減少實施 Lync Server 2013 時所需的伺服器角色數目。 遞減監控伺服器角色也可避免維護專用伺服器進行監視，以協助降低成本。

  - 降低 Lync Server 2013 設定和管理的複雜性。 在每一部前端伺服器上組合監視服務，您不再需要安裝、設定及管理監控伺服器角色。

如需詳細資訊，請參閱 Lync Server 2013 2013 部署指南中的在[Lync server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)主題。

</div>

<span> </span>

</div>

</div>

</div>

