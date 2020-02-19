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
ms.openlocfilehash: 8d19b045e23efa39c9f70f70ba7ac0236e77cc13
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="central-management-store-failover-in-lync-server-2013"></a>Lync Server 2013 中的中央管理存放區容錯移轉

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-18_

中央管理存放區包含伺服器和 Lync 2013 部署中的服務相關的組態資料。 它提供穩定、 結構描述化為儲存區的定義、 設定、 維護、 管理、 說明，以及操作 Lync 2013 部署所需的資料。 它也驗證資料，以確保設定一致性。

每個 Lync 的部署包含一個中央管理存放區，這後端伺服器的一個前端集區所主控。

當您建立集區配對，其中包含裝載的中央管理存放區的集區時，備份的中央管理存放區資料庫設定的備份集區，與服務會安裝在兩個集區的中央管理存放區中。 在任何時間點，其中兩個中央管理存放區資料庫是作用中的主圖形，且另一個是待命。 內容會複寫至待命從作用中主備份服務。

期間牽涉到主控的中央管理存放區的集區的集區容錯移轉，系統管理員必須容錯移轉前失敗的中央管理存放區上的前端集區。

嚴重損壞修復後，它不需要容錯回復的中央管理存放區。 修復後，在原始的備份集區的中央管理存放區可以保持為作用中的主圖形。

中央管理存放區容錯移轉的程式設計目標是 5 分鐘，復原時間目標 (RTO) 和 5 分鐘，復原點目標 (RPO)。

</div>

<span> </span>

</div>

</div>

</div>

