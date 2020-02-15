---
title: Lync Server 2013： 使用 SIP 主幹路由 E9-1-1 通話
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
ms.openlocfilehash: f45bd91eade0de6f290fd87e52effb25c669999a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013 中使用 SIP 主幹路由 E9-1-1 呼叫

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-29_

使用 SIP 主幹來連線到合格的 E9-1-1 服務提供者，是部署 E9-1-1 的方式之一。 如需詳細資訊來連線至公用交換的電話網路 (PSTN) 使用 ELIN 閘道-型 E9-1-1 服務提供者，請參閱[使用 Lync Server 2013 中的 ELIN 閘道路由 E9-1-1 呼叫](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)。

下圖顯示如何將緊急通話路由傳送從 Lync Server 到公用安全回應點 (PSAP) 當您使用 SIP 主幹及合格的 E9-1-1 服務提供者。

**透過 SIP 主幹路由傳送 E9-1-1 通話**

![緊急電話從 Lync Server 路由傳送至 PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "緊急電話從 Lync Server 路由傳送至 PSAP")

當從相容的 Lync Server 用戶端撥打緊急電話：

1.  Lync server 路由傳送的 SIP INVITE，包含位置、 發話者回撥號碼，以及 （選擇性） 通知 URL 和會議回撥號碼。

2.  Lync Server 比對緊急號碼，並將通話路由傳送 （依據適用位置原則中定義的**PSTN 使用方式**值） 到中繼伺服器，並且從那裡透過 SIP 主幹 E9-1-1 服務提供者。

3.  E9-1-1 服務提供者會依據隨附於通話的位置，將緊急通話路由傳送至正確的 PSAP。當用戶端將驗證過的緊急回應位置 (ERL) 隨附於緊急通話，提供者會自動將通話路由傳送至適當的 PSAP。如果位置是由使用者手動輸入，緊急通話回應中心 (ECRC) 會先向發話者口頭確認位置的精確度，才將緊急通話路由傳送至 PSAP。

4.  如果您設定的位置原則，通知，一或多個組織的安全性人員所傳送的特殊 Lync 緊急通知立即訊息。 此訊息一律會快顯在安全人員的螢幕上，並包含發話者的名稱、電話號碼、時間和位置，讓安全人員能夠使用立即訊息或語音，快速回應緊急發話者。

5.  如果您設定了會議的位置原則，且其受到 E9-1-1 服務提供者支援，則內部安全性桌面會以單向音訊或雙向音訊加入電話會議。

6.  如果通話突然中斷，PSAP 會直接使用回撥號碼來連絡發話者。

</div>

<span> </span>

</div>

</div>

</div>

