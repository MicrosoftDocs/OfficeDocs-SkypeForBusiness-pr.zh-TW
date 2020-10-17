---
title: Lync Server 2013：取得位置
description: Lync Server 2013：取得位置。
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
ms.openlocfilehash: 25aa907b5373cadd9eb8ffe9e32a7531afa01deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571109"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a>在 Lync Server 2013 中取得位置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

在 Lync Server 2013 E9-1-1 部署中，每個內部連線的 Lync 或 Lync Phone Edition 用戶端都會主動取得自己的位置。 在 SIP 註冊後，用戶端會將其本身所知道的所有網路連線資訊 furnishes 至位置資訊服務（即複製的 SQL Server 資料庫所支援的 web 服務）的位置要求。 每個中央網站集區都有一個位置資訊服務，可使用網路資訊來查詢其記錄中的相符位置。 如果有相符的位置資訊服務會將位置傳回用戶端。 如果不符合，系統會提示使用者手動輸入位置 (，視位置原則設定) 而定。 位置資料會傳回網際網路工程工作中的用戶端。 (的 IETF) 標準化 XML 格式，稱為目前狀態資訊資料格式位置物件 (PIDF-LO) 。

Lync Server 用戶端在緊急通話過程中包含 PIDF-LO 資料，而 E9-1-1 服務提供者會使用此資料來判斷適當的 PSAP，並將通話路由傳送至該 PSAP，也就是正確的 ESQK 一起，讓 PSAP dispatcher 可以取得來電者的位置。

下圖顯示 Lync Server 用戶端如何取得位置 (，但不包括協力廠商用戶端 MAC 位址型位置方法) ：

![用戶端如何取得位置圖表](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "用戶端如何取得位置圖表")

若要讓用戶端取得位置，必須進行下列步驟：

1.  系統管理員會以網路線路圖將各種網路位址對應至對應緊急回應位置（ (Erl) # A3）的 [網路] (表格，填入位置資訊服務資料庫。

2.  如果您使用 SIP 主幹 E9-1-1 服務提供者，則系統管理員會依照主要街道位址指南 (MSAG) E9-1-1 服務提供者所維護的資料庫來驗證 Erl 的市政位址部分。 如果您使用的是 ELIN 閘道，則系統管理員會確保 PSTN 載波將 Elin 上傳至自動位置識別 (阿裡) 資料庫。

3.  在註冊期間或網路變更發生時，內部連線的用戶端會傳送包含用戶端已探索網路位址的位置要求至位置資訊服務。

4.  位置資訊服務會查詢其發佈的記錄的位置，如果找到相符的記錄，則會以 PIDF-LO 格式將 ERL 傳回用戶端。

</div>

<span> </span>

</div>

</div>

</div>

