---
title: Lync Server 2013 中央管理存放區容錯移轉
description: Lync Server 2013 中央管理存放區容錯移轉。
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
ms.openlocfilehash: d2960a55d6bdc49e00bf22997bc53946d4770fde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544369"
---
# <a name="central-management-store-failover-in-lync-server-2013"></a>Lync Server 2013 中的中央管理存放區容錯移轉

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

中央管理存放區包含 Lync 2013 部署中伺服器和服務的設定資料。 它可為定義、設定、維護、管理、描述及操作 Lync 2013 部署所需的資料提供強健的 schematized 儲存。 它也驗證資料，以確保設定一致性。

每個 Lync 部署都包含一個中央管理存放區，由一個前端集區的後端伺服器主控。

當您建立的集區配對包含主控中央管理存放區的集區時，會在備份組區中設定備份中央管理存放區資料庫，並在兩個集區中安裝中央管理存放區服務。 在任何時間點，其中一個中央管理存放區資料庫是作用中的主資料庫，另一個則是待機狀態。 備份服務會將內容從使用中主圖形複製到待機狀態。

在包含主控中央管理存放區之集區的集區容錯移轉期間，管理員必須先容錯移轉中央管理存放區，再失敗轉移前端集區。

修復災難後，不需要對中央管理存放區進行容錯回復。 修復之後，原始備份組區中的中央管理存放區可以保留為作用中主圖形。

集中式管理存放區容錯移轉的工程目標是5分鐘的復原時間目標 (RTO) 和5分鐘用於復原點目標 (RPO) 。

</div>

<span> </span>

</div>

</div>

</div>

