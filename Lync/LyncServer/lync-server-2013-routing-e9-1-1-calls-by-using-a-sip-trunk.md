---
title: Lync Server 2013：使用 SIP 主幹路由 E9-1-1 來電
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 918aaf97b1567f012a2b41de7128db23aa383acb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>在 Lync Server 2013 中使用 SIP 主幹路由 E9-1-1 來電

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

使用 SIP 主幹來連線至合格的 E9-1-1 服務提供者，是一種部署 E9-1-1 的方式。 如需使用 ELIN 閘道連線至公用交換電話網絡（PSTN） E9-1-1 服務提供者的詳細資料，請參閱[在 Lync Server 2013 中使用 ELIN 閘道進行路由 E9-1 通話](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。

下圖顯示當您使用 SIP 幹線與合格的 E9-1 服務提供者時，緊急通話如何從 Lync Server 路由到公用安全應答點（PSAP）。

**透過 SIP 主幹路由 E9-1-1 通話**

![將緊急電話從 Lync Server 路由傳送至 PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "將緊急電話從 Lync Server 路由傳送至 PSAP")

從相容的 Lync Server 用戶端發出緊急通話時：

1.  包含位置的 SIP 邀請、來電者的回呼號碼，以及（選擇性）通知 URL 和會議回呼號碼都會路由至 Lync Server。

2.  Lync Server 符合緊急號碼，並將呼叫路由（根據適用位置原則中定義的**PSTN 使用量**值）到中繼伺服器，然後從 SIP 主幹轉移至 E9-1-1 服務提供者。

3.  E9-1-1 服務提供者會根據通話隨附的位置，將緊急通話路由到正確的 PSAP。 當用戶端包含具有緊急呼叫的驗證緊急回應位置（ERL）時，提供者會自動將呼叫路由至適當的 PSAP。 如果該位置是由使用者手動輸入，則緊急呼叫回應中心（ECRC）會先 verbally 驗證與來電者之間的位置準確性，然後才會將緊急呼叫傳送至 PSAP。

4.  如果您已設定通知的位置原則，您組織的一個或多個安全主管會傳送特殊的 Lync 緊急通知立即訊息。 此訊息永遠會出現在安全性監察官的畫面上，並包含來電者的名稱、電話號碼、時間和位置，讓安全人員能使用立即訊息或語音來快速回應緊急來電者。

5.  如果您已設定會議的位置原則，且 E9-1-1 服務提供者支援它，就會使用一種單向音訊或雙向音訊，在通話中 conferenced 內部安全服務台。

6.  如果通話過早中斷，PSAP 會使用回呼號碼直接聯絡來電者。

</div>

<span> </span>

</div>

</div>

</div>

