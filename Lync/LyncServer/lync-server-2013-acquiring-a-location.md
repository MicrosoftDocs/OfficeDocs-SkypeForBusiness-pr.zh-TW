---
title: Lync Server 2013： 取得位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88ed32ed07f709e0a047e8fc07e9124bc129adca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>取得 Lync Server 2013 中的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-06_

在 Lync Server 2013 E9-1-1 部署中，每個內部連線的 Lync 或 Lync Phone Edition 用戶端主動取得它自己的位置。 SIP 註冊後，用戶端提供它所知本身其位置要求中的位置資訊服務，也就是由複寫的 SQL Server 資料庫的 web 服務的所有網路連線資訊。 每個中央網站集區有位置資訊服務，它會使用網路資訊來查詢比對的位置記錄。 如果沒有相符項目，位置資訊服務會傳回給用戶端的位置。 如果不相符項目，可能會提示使用者輸入位置，以手動方式 （根據位置原則 」 設定）。 位置資料傳送回至名為目前狀態資訊的資料格式位置物件 (PIDF-LO) 的用戶端中網際網路工程任務推動小組 (IETF) 標準化 XML 格式。

Lync Server 用戶端中包含 PIDF-LO 資料一部分緊急通話，並用此資料 E9-1-1 服務提供者來決定適當的 PSAP，並路由傳送至該 PSAP 連同正確的 esqk 一起，可讓 PSAP 調度員得以取得來電發話者的位置。

下圖顯示 Lync Server 用戶端如何取得位置 （但不包括第三方用戶端 MAC 位址型方法）：

![用戶端如何取得位置圖表](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "用戶端如何取得位置圖表")

若要取得位置用戶端，必須執行下列步驟進行：

1.  由系統管理員將網路線路圖 （將各種網路位址對應至對應的緊急事故回應位置 (Erl) 的表格） 的位置資訊服務資料庫。

2.  如果您使用 SIP 主幹 E9-1-1 服務提供者時，系統管理員會驗證針對 E9-1-1 服務提供者所維護的主要街道地址指南 (MSAG) 資料庫的 Erl 市街地址部分。 如果您使用 ELIN 閘道時，系統管理員可確保，PSTN 電信業者會將上傳 Elin 到自動位置識別 (ALI) 資料庫。

3.  凡是登錄或網路變更發生時，內部連線用戶端會傳送位置要求，其中包含用戶端被發現的位置資訊服務的網路位址。

4.  位置資訊服務查詢已發行的記錄位置，並如果找到相符項目，就會傳回 ERL 給用戶端以 PIDF-LO 格式。

</div>

<span> </span>

</div>

</div>

</div>

