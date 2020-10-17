---
title: Lync Server 2013 會議負載分配
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f7b2d759ec9370bbf7eeeb2844edd3511ba0f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499200"
---
# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Lync Server 2013 中的會議負載分配

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-22_

與其他一些專用會議解決方案不同的是，Lync Server 架構是共用硬體模型。 這表示相同的硬體可以由許多軟體元件共用，每個軟體元件都支援不同的即時通訊。 每個類型的即時通訊都會在伺服器上放置特定的負載。 例如，前端伺服器可以執行會話初始通訊協定 (SIP) 路由元件、web 應用程式 (例如通訊錄搜尋) 、Web 會議服務、A/V 會議服務、Enterprise Voice 應用程式 (例如會議應答應用程式及回應群組應用程式) ，以及轉送伺服器。 前端伺服器上的一組資料庫也會為使用者、連絡人、顯示狀態、會議及語音路由資料提供儲存和處理。 藉由此硬體共用，元件、服務及處理程序就能競用 CPU 和記憶體資源，讓非會議的工作負載能夠在伺服器延展上產生直接影響。

與其他硬體埠型會議解決方案相較，Lync Server 會議架構為無保留模型。 當使用者排程會議時，Lync Server 會在會議資料庫中建立記錄，而該記錄會儲存會議資料，但不會事先為排程的會議保留任何硬體資源。 相反地，Lync Server 具有內建負載平衡邏輯，可在前端伺服器上以平均方式，在集區中的所有前端伺服器上，以平均方式分配會議資源。 這樣會以有效率的方式來佈建和運用硬體資源，但在支援超大型會議時便是一項挑戰 (特別是在沒有適當規劃的情況下)。 例如，當 Lync Server 2013 集區正在接近其最上層容量時，每一部前端伺服器可能會裝載大約125平均大小的會議。 新增另一個小型會議不是問題，但為1000使用者新增會議時，可能會有問題，因為前端伺服器可能無法與其他125會議同時支援這類大型會議。

</div>

<span> </span>

</div>

</div>

</div>

