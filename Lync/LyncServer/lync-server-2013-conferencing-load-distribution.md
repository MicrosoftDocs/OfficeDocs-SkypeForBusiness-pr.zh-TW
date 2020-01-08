---
title: Lync Server 2013 會議載入發佈
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd78b6dcedc66f5a2235b45066be7faf70d4379b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>在 Lync Server 2013 中的會議載入發佈

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

與其他一些專用會議解決方案不同，Lync Server 架構是共用硬體模型。 這表示同一個硬體是由許多軟體元件所共用，每個元件都支援不同的即時通訊。 每個即時通訊類型都會將伺服器上的特定負載放在一起。 例如，前端伺服器可以執行會話初始通訊協定（SIP）路由元件、web 應用程式（例如通訊錄搜尋）、Web 會議服務、A/V 會議服務、企業語音應用程式（例如，會議助理應用程式與回應群組應用程式），以及中繼伺服器。 前端伺服器上的一組資料庫也會提供儲存與處理，以供使用者、連絡人、目前狀態、會議及語音路由資料使用。 針對 CPU 和記憶體資源而言，有這種硬體共用、元件、服務和程式可爭用，所以非會議工作負載會直接影響伺服器的規模。

與其他硬體埠式會議解決方案相比，Lync Server 會議架構是無保留模型。 當使用者排程會議時，Lync Server 會在會議資料庫中建立一筆記錄，該記錄會儲存會議資料，但不會提前為排程的會議保留任何硬體資源。 相反地，Lync Server 有內建的負載平衡邏輯，可在前端伺服器上以平均分佈負載的方式，在池中的所有前端伺服器上平均分配會議資源。 這會有效地提供和使用硬體資源，但在支援超大型會議時，特別是不需要進行適當規劃的挑戰。 例如，當 Lync Server 2013 池執行接近其最上層容量時，每個前端伺服器都可能主持大約125平均大小的會議。 新增另一個小型會議並不是問題，但為1000使用者新增會議時可能會有問題，因為前端伺服器可能無法與其他125會議同時支援這類大型會議。

</div>

<span> </span>

</div>

</div>

</div>

