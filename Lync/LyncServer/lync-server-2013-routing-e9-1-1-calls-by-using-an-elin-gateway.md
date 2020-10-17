---
title: Lync Server 2013：使用 ELIN 閘道路由傳送 E9-1-1 通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a3fb7a36680ff3ef35de44d53fc10a676d46242
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511240"
---
# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>在 Lync Server 2013 中使用 ELIN 閘道路由 E9-1-1 通話

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-05_

Unified Communications Open Interoperability Program 中的部分合作夥伴會提供具合格緊急位置識別碼 (ELIN) 功能的閘道，對合格的 E9-1-1 服務提供者而言，這些閘道可用來作為 SIP 主幹連線的替代方式。 ELIN 閘道支援 ISDN 或集中式自動訊息記帳 (CAMA) 連線到公用交換電話網路 (PSTN) E9-1-1 服務的功能。 如需提供 ELIN 閘道和其檔連結的合作夥伴詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425) 。

與 E9-1-1 服務提供者的 SIP 主幹連線，ELIN 閘道也會提供方法，將緊急通話路由傳送至來電者最適當的公用安全回應點 (PSAP) ，但這些閘道使用 ELIN 做為位置識別碼。 您為組織中的每個緊急回應位置 (ERL) 定義 Elin (如需詳細資訊，請參閱 [在 Lync Server 2013) 中管理 ELIN 閘道的位置](lync-server-2013-managing-locations-for-elin-gateways.md) 。

當您使用 ELIN 閘道進行緊急通話時，請使用相同的 Lync Server E9-1-1 基礎結構，以便用於 SIP 主幹連線。 也就是說，位置資訊服務資料庫會提供 Lync Server 用戶端的位置，而位置原則會啟用該功能及定義路由。 不過，使用 ELIN 閘道時，您必須將 Elin 新增至位置資訊服務資料庫，並讓 PSTN 電信公司將其上傳至自動位置識別 (阿裡) 資料庫。

當 Lync 用戶端從 Location 資訊服務取得位置時，該位置會包含 ELIN。 在緊急通話期間，ELIN 會包含在傳送至 ELIN 閘道的位置中。 ELIN 閘道會將通話識別為緊急通話，並將來電者的號碼更換為 ELIN。 然後 ELIN 閘道會使用 ELIN 作為來電號碼將通話路由傳送至 PSTN。 PSTN E9-1-1 提供者會在 ALI 資料庫中查詢 ELIN，該資料庫是主要街道地址指南 (MSAG) 資料庫的隨附資料庫。 然後 PSTN 會依據 ALI 查詢結果將通話傳送至最合適的 PSAP，PSAP 首先會依據 ALI 查詢結果將回應者傳送至發話方的位置。 在針對回撥預先定義的時間長度內，來電號碼會快取於 ELIN 閘道上。 回撥期間，PSAP 會到達 ELIN 閘道，閘道會將 ELIN 更換為發話方的直接向內撥號 (DID) 號碼。

ELIN 閘道僅支援從您組織的網路內部撥打的緊急通話。 這些閘道不支援從您網路外部撥打的緊急通話。

<div>


> [!NOTE]  
> 如需對緊急通話使用 SIP 主幹連線的詳細資訊，請參閱 <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">在 Lync Server 2013 中使用 sip 主幹路由 E9-1-1 呼叫</A>。



</div>

下圖顯示當您使用 ELIN 閘道時，緊急通話如何從 Lync Server 路由傳送至 PSAP。

**使用 ELIN 閘道路由傳送 E9-1-1 通話**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  包含位置、來電者的回撥號碼，以及 (選用) 通知 URL 和會議回撥號碼的 SIP INVITE 會路由傳送至 Lync Server。

2.  Lync Server 會比對緊急號碼，然後根據適用位置原則中所定義的 **PSTN 使用** 值，將 (通話路由傳送) 至轉送伺服器，以及從那裡 ELIN 閘道。

3.  ELIN 閘道會透過 ISDN 或 CAMA 主幹，將通話路由傳送至 PSTN。

4.  PSTN 會將該通話識別為緊急通話，並將它路由傳送至網路中 E9-1-1 選擇的路由器。E9-1-1 選擇的路由器會在 ALI 資料庫中查閱來電者的號碼，以取得地理位置。E9-1-1 選擇的路由器會根據從 ALI 資料庫擷取的位置資訊，將通話路由傳送至最適當的 PSAP。

5.  如果您已設定通知的位置原則，則會傳送一或多個組織的安全性監察官，以傳送特殊的 Lync 緊急通知立即訊息。 此訊息一律會快顯於安全人員的螢幕上，其中包含來電者的名稱、電話號碼、時間及位置，讓安全人員能夠使用立即訊息或語音，快速回應緊急來電者。

6.  如果通話提前中斷，PSAP 會使用 ELIN 直接連絡來電者。ELIN 閘道會將 ELIN 更換為來電者的 DID。

</div>

<span> </span>

</div>

</div>

</div>

