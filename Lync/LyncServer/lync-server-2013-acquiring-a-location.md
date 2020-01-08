---
title: Lync Server 2013：擷取位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb123cf2f38d935bc0cc641c67e6d0ff1d54e4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>在 Lync Server 2013 中擷取位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-06_

在 Lync Server 2013 E9-1-1 部署中，每個內部連線的 Lync 或 Lync Phone Edition 用戶端都會主動取得自己的位置。 在 SIP 註冊之後，用戶端會在位置資訊服務（由複製的 SQL Server 資料庫支援的 web 服務）的位置要求中，furnishes 它知道的所有網路連線資訊。 每個中央網站池都有一個位置資訊服務，該服務會使用網路資訊來查詢其記錄中的相符位置。 如果有相符專案，位置資訊服務會傳回用戶端的位置。 如果沒有相符的專案，系統可能會提示使用者手動輸入位置（視位置原則設定而定）。 位置資料會以網際網路工程任務組（IETF）標準化 XML 格式傳回用戶端，稱為「目前狀態資訊資料格式位置」物件（PIDF-LO）。

Lync Server 用戶端會在緊急通話中包含 PIDF-LO 資料，而 E9 1-1 服務提供者會使用此資料來判斷適當的 PSAP，並將呼叫傳送給該 PSAP 以及正確的 ESQK，這可讓 PSAP dispatcher 取得來電者的位置。

下圖顯示 Lync Server 用戶端如何取得位置（除了協力廠商用戶端 MAC 位址的位置方法之外）：

![用戶端如何取得位置圖表](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "用戶端取得位置圖表的方式")

若要讓用戶端取得位置，必須執行下列步驟：

1.  系統管理員會使用 network wiremap （將各種類型的網路位址對應至相對應緊急回應位置（ERLs））來填入位置資訊服務資料庫。

2.  如果您使用 SIP 幹線 E9-1 服務提供者，系統管理員會針對由 E9-1 服務提供者所維護的主要街道位址指南（MSAG）資料庫，驗證 ERLs 的市政位址部分。 如果您使用的是 ELIN 閘道，系統管理員會確保 PSTN 載波將 ELINs 上傳到自動位置識別（阿裡）資料庫。

3.  在註冊期間或每當網路變更時，內部連接的用戶端會傳送包含用戶端探索之網路位址的位置要求給位置資訊服務。

4.  位置資訊服務會針對某個位置查詢其已發佈的記錄，如果找到一個相符專案，則會以 PIDF 格式傳回用戶端的 ERL。

</div>

<span> </span>

</div>

</div>

</div>

