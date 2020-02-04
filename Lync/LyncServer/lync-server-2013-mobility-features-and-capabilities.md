---
title: Lync Server 2013：行動功能與性能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e00274e62cc0fe7cf55c45e11a49670c7f1e6a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Lync Server 2013 中的行動功能與性能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 的累積更新中引入的行動功能：2月2013支援 Lync 2010 行動裝置和 Lync 2013 行動用戶端功能。 當您部署 Lync Server 2013 行動服務時，使用者可以使用支援的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 行動裝置來執行諸如傳送和接收立即訊息、查看連絡人及查看目前狀態等活動。 此外，行動裝置支援一些企業語音功能，例如按一下以加入會議、透過工作撥打電話、單一號碼達到、語音信箱及未接來電。 Lync Server 2013 的累積更新中引入的新功能：2月2013包含適用于會議出席者的語音 IP （VoIP）功能和視頻（H-p）。

Lync Server 2013 的累積更新中引入的行動功能功能：2月2013支援 Lync 2013 行動用戶端功能。 Lync Server 2013 的累計更新：2月2013安裝統一通訊網頁 API 或 UCWA。 UCWA 是 Lync 2013 行動用戶端所用的元件。 在 Lync Server 2013 中，Mcx 是用於 Lync 2010 行動用戶端。 Lync Server 2013 的累積更新：2月2013將 UCWA 做為行動服務的新進入點。 Lync Server 2013 同時實現行動服務（Mcx），這是在 Lync Server 2010 的累積更新中引入的（即年11月2011，並提供 Lync 2010 行動裝置支援。 當您部署 Lync Server 2013 2013 的累加更新時，使用者可以使用支援的 Apple iOS、Android 和 Windows Phone 行動裝置來執行下列活動：

<div>


> [!IMPORTANT]  
> 行動服務支援的功能來自 Lync Server 2010 的累積更新：2011年11月，請注意（Mcx）。 在 Lync Server 2013 的累積更新中引入的所有列出功能都受 UCWA：2013年2月。



</div>

  - 傳送和接收立即訊息（Mcx）

  - [查看目前狀態] （Mcx）

  - [查看連絡人] （Mcx）

  - 按一下以加入會議（Mcx）

  - 透過公司通話（Mcx）

  - 單一數位延伸（Mcx）

  - 語音信箱（Mcx）

  - 未接來電通知（Mcx）

  - [語音 over IP （VoIP）]

  - 出席者影片（H-p）

<div>


> [!NOTE]  
> Lync 2010 Mobile 提供 Nokia Symbian 裝置的用戶端。 Lync 2013 Mobile 將沒有適用于 Nokia Symbian 裝置的用戶端。



</div>

Apple iPad 使用者將能夠存取增強功能。 使用音訊來電加入會議之後，iPad 使用者就能在會議中查看上傳的 Microsoft PowerPoint 簡報、共用應用程式和桌上型電腦、查看會議參與者清單，以及接收其他內容類型的通知在會議中共用的專案。

<div>


> [!TIP]  
> 在有一個數位的情況下，使用者會在已撥打至公司電話的行動電話上接聽通話。 透過 [通話]，使用者可以使用公司電話號碼（而不是行動電話號碼），從 Lync 行動用戶端撥出出站通話。 在撥出時，用戶端會傳送要求給 Mcx 或 UCWA （根據 Lync 行動裝置版本）來撥打電話給他們。 伺服器會啟動通話，然後將使用者傳回行動電話。 當使用者應答時，伺服器會撥打電話給其他方來完成通話。 透過 [透過公司通話]，使用者可以在通話期間維持自己的工作身分識別，這表示通話收件者不會看到來電者的行動電話號碼，且來電者不會產生撥出電話費。



</div>

<div>


> [!NOTE]  
> 並非所有的功能在所有行動裝置上都能完全相同。 如需行動裝置上支援之功能的詳細資訊，請參閱中的<A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>行動用戶端比較表。 如需支援的裝置和作業系統的詳細資料，請參閱<A href="lync-server-2013-planning-for-mobile-clients.md">規劃 Lync Server 2013 中行動用戶端</A>的需求主題。



</div>

當您使用 Lync Server 2013 自動探索功能時，行動應用程式可以自動找出 Lync Server 2013 Web 服務，而不需要使用者在其裝置設定中手動輸入 Url。 在行動裝置設定中，也支援手動輸入 Url，主要是為了進行疑難排解。

<div>


> [!IMPORTANT]  
> Mcx 和 UCWA 都是免費服務，而且都是為了支援 Lync 2010 行動裝置和 Lync 2013 行動用戶端而部署。 Lync 2013 Mobile 將無法登入 Lync Server 2010 部署。 Lync 2010 行動裝置和 Lync 2013 行動裝置將能夠使用 Lync server 2013 部署與 Lync Server 2013 的累積更新：已套用二月2013。



</div>

行動裝置功能也支援不支援在背景中執行之應用程式之行動裝置的*推播通知*。 推播通知是傳送給行動裝置的通知，在行動應用程式處於非使用中時，發生該事件。 例如，未接的立即訊息（IM）邀請可能會產生推播通知。

Mcx、UCWA、自動探索服務以及 Lync Server 2013 中提供推播通知支援。 更新之用戶端功能、功能，以及使用 UCWA 做為行動進入點，會在 Lync Server 2013 的累積更新中引入：2013年2月。

</div>

<span> </span>

</div>

</div>

</div>

