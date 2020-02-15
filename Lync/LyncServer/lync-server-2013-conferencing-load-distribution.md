---
title: Lync Server 2013 會議負載分散
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
ms.openlocfilehash: 4dad04b445421e27e68cf49900d4bb925918bd43
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Lync Server 2013 中的會議負載分散

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-22_

與其他部分專用的會議解決方案，不同 Lync Server 架構是共用硬體模型。 這表示相同的硬體可以由許多軟體元件共用，每個軟體元件都支援不同的即時通訊。 每個類型的即時通訊都會在伺服器上放置特定的負載。 比方說，前端伺服器可以執行的工作階段初始通訊協定 (SIP) 路由元件、 web 應用程式 （例如通訊錄搜尋）、 Web 會議服務、 A / V 會議服務、 企業語音應用程式 （例如會議服務員應用程式和回應群組應用程式），以及中繼伺服器。 一組的前端伺服器上的資料庫也提供儲存和處理的使用者、 連絡人、 目前狀態、 會議和語音路由的資料。 藉由此硬體共用，元件、服務及處理程序就能競用 CPU 和記憶體資源，讓非會議的工作負載能夠在伺服器延展上產生直接影響。

相較於其他硬體基於連接埠的會議解決方案，Lync Server 會議架構是非保留模型。 當使用者排程會議時，Lync Server 會在會議的資料庫，其中儲存會議資料，但是不會保留的事先排定的會議任何硬體資源建立一筆記錄。 相反地，Lync Server 具有內建負載平衡邏輯以動態方式配置前端伺服器上的會議資源，以分散負載同樣的每個跨所有前端伺服器集區中的方式。 這樣會以有效率的方式來佈建和運用硬體資源，但在支援超大型會議時便是一項挑戰 (特別是在沒有適當規劃的情況下)。 例如，接近其上方容量執行 Lync Server 2013 集區時，每個前端伺服器可能會主控大約 125 個平均大小會議。 新增另一個小型的會議不會發生問題，但新增 1000 個使用者的會議就是問題，因為前端伺服器便可能無法以支援在同一時間為其他 125 個會議這類大型會議。

</div>

<span> </span>

</div>

</div>

</div>

