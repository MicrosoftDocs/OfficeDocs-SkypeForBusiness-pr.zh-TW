---
title: Lync Server 2013：使用 SIP 主幹路由傳送 E9-1-1 通話
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
ms.openlocfilehash: cc64047c932244499da820569a96c6f115c24ab7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511250"
---
# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>在 Lync Server 2013 中使用 SIP 主幹路由傳送 E9-1-1 通話

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

使用 SIP 主幹來連線到合格的 E9-1-1 服務提供者，是部署 E9-1-1 的方式之一。 如需使用 ELIN 閘道來連線至公用交換電話網路 (PSTN) 型 E9-1-1 服務提供者的詳細資訊，請參閱 [在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。

下圖顯示當您使用 SIP 主幹和合格的 E9-1-1 服務提供者時，如何將緊急通話從 Lync Server 路由傳送至公用安全回復點 (PSAP) 。

**透過 SIP 主幹路由傳送 E9-1-1 通話**

![從 Lync Server 到 PSAP 的緊急通話路由](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "從 Lync Server 到 PSAP 的緊急通話路由")

當緊急通話來自相容的 Lync Server 用戶端時：

1.  包含位置、來電者的回撥號碼，以及 (選用) 通知 URL 和會議回撥號碼的 SIP INVITE 會路由傳送至 Lync Server。

2.  Lync Server 會根據 E9-1-1 服務提供者的適用位置) 原則中所定義的 **PSTN 使用** 值，以符合緊急號碼，並將 (通話路由傳送至-1-1-1 服務提供者。

3.  E9-1-1 服務提供者會依據隨附於通話的位置，將緊急通話路由傳送至正確的 PSAP。當用戶端將驗證過的緊急回應位置 (ERL) 隨附於緊急通話，提供者會自動將通話路由傳送至適當的 PSAP。如果位置是由使用者手動輸入，緊急通話回應中心 (ECRC) 會先向發話者口頭確認位置的精確度，才將緊急通話路由傳送至 PSAP。

4.  如果您已設定通知的位置原則，則會傳送一或多個組織的安全性監察官，以傳送特殊的 Lync 緊急通知立即訊息。 此訊息一律會快顯在安全人員的螢幕上，並包含發話者的名稱、電話號碼、時間和位置，讓安全人員能夠使用立即訊息或語音，快速回應緊急發話者。

5.  如果您設定了會議的位置原則，且其受到 E9-1-1 服務提供者支援，則內部安全性桌面會以單向音訊或雙向音訊加入電話會議。

6.  如果通話突然中斷，PSAP 會直接使用回撥號碼來連絡發話者。

</div>

<span> </span>

</div>

</div>

</div>

