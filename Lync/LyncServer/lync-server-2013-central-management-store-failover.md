---
title: Lync Server 2013 中央管理存放區容錯移轉
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central Management store failover
ms:assetid: f464d715-68a4-462c-9584-00f41ab10db0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205376(v=OCS.15)
ms:contentKeyID: 48185809
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38bde96b74fa1c00fc937a159c5e8e40df42d4dc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a>Lync Server 2013 中的中央管理存放區容錯移轉

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

中央管理存放區包含有關 Lync 2013 部署中伺服器和服務的配置資料。 它提供了資料的強健、schematized 儲存，以定義、設定、維護、管理、描述及操作 Lync 2013 部署。 它也會驗證資料，以確保配置一致性。

每個 Lync 部署都包含一個中央管理儲存區，該商店是由一個前端池的後端伺服器所託管。

當您建立包含託管中央管理存儲區的 pool 時，會在備份池中設定備份中央管理儲存資料庫，並在這兩個池中都安裝集中式管理儲存服務。 在任何時間點，兩個中央管理儲存資料庫之一是 [作用中的主要檔]，另一個是 [備用]。 該內容會由備份服務從 [作用中] 主機複製到 [備用]。

在涉及託管管理中心存儲區的 pool 容錯移轉期間，系統管理員必須先將中央管理存儲容錯移轉，然後才能失敗轉移到前端池。

修復災難之後，不需要對中央管理儲存進行容錯回復。 修復之後，原始備份池中的中央管理儲存區可以保留為作用中的主版。

針對集中式管理商店容錯移轉的工程目標，在恢復時間目標（RTO）中為5分鐘，而針對復原點目標（RPO）則為5分鐘。

</div>

<span> </span>

</div>

</div>

</div>

