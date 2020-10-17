---
title: Lync Server 2013：行動性功能及功能
description: Lync Server 2013：行動性功能和功能。
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
ms.openlocfilehash: 20713145c18260f22d9635c34af291e9a7c5ea9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550579"
---
# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Lync Server 2013 中的行動功能與功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 的累計更新所引進的行動功能：2月2013支援 Lync 2010 Mobile 和 Lync 2013 行動用戶端功能。 當您部署 Lync Server 2013 行動性服務時，使用者可以使用支援的 Apple iOS、Android 和 Windows Phone 或 Nokia Symbian 行動裝置執行諸如傳送和接收立即訊息、查看連絡人及查看顯示狀態等活動。 此外，行動裝置還可支援某些 Enterprise Voice 功能，例如按一下加入會議、從公司撥號、單一號碼搜尋、語音信箱及未接來電。 Lync Server 2013 的累計更新所引進的新功能：二月份2013包括「語音 over IP」 (VoIP) 功能和影片 (對會議出席者的 H-p) 。

Lync Server 2013 的累計更新引進的行動功能：2月2013支援 Lync 2013 行動用戶端功能。 Lync Server 2013 的累計更新：2月2013安裝統一通訊網頁 API 或 UCWA。 UCWA 是 Lync 2013 行動用戶端所使用的元件。 在 Lync Server 2013 中，Mcx 是用於 Lync 2010 行動用戶端。 Lync Server 2013 的累計更新：二月份2013引進 UCWA 做為行動服務的新進入點。 Lync Server 2013 同時在 Lync Server 2011 2010 的累積更新中引入行動服務 (Mcx) ，並提供對 Lync 2010 Mobile 的支援。 當您部署 Lync Server 2013 的累計更新時：2月2013，使用者可以使用支援的 Apple iOS、Android 和 Windows Phone mobile 裝置執行這類活動，如下所示：

<div>


> [!IMPORTANT]  
> Lync Server 2010 的累計更新支援的行動服務功能：11月 2011 (Mcx) 中注明。 所有列出的功能都是由 UCWA 所支援，在 Lync Server 2013 的累計更新中引進：2月2013。



</div>

  -  (Mcx) 傳送和接收立即訊息

  -  (Mcx) 中查看顯示狀態

  -  (Mcx) 中查看連絡人

  - 按一下以加入會議 (Mcx) 

  - 透過作品撥打 (Mcx) 

  - 單一號碼 (Mcx) 

  - 語音信箱 (Mcx) 

  - 未接來電通知 (Mcx) 

  - Voice over IP (VoIP)

  - 出席者影片 (H-p) 

<div>


> [!NOTE]  
> Lync 2010 Mobile 提供 Nokia Symbian 裝置的用戶端。 Lync 2013 Mobile 將不會有用戶端用於 Nokia Symbian 型裝置。



</div>

Apple iPad 使用者將可存取增強型功能。 使用音訊來電加入會議之後，iPad 使用者就能夠在會議中查看上傳的 Microsoft PowerPoint 簡報、共用應用程式與桌面、查看會議參與者清單，以及接收其他在會議中共用的內容類型通知。

<div>


> [!TIP]  
> 使用單一號碼搜尋時，使用者可以用行動電話接收撥打至公司號碼的電話。 透過公司的來電，使用者可以使用公司電話號碼，而不是行動電話號碼，從 Lync Mobile 用戶端撥出電話。 透過撥出，用戶端會根據 Lync Mobile 版本) ，將要求傳送至 Mcx 或 UCWA (，以進行呼叫。 此伺服器會起始通話，然後回撥給使用者的行動電話。 當使用者應答時，伺服器就會撥打給另一方，以完成通話。 藉由使用「從公司撥號」，使用者可以在通話期間維持其公司身分識別，這表示受話者不會看到來電者的行動電話號碼，而且來電者可避免產生撥出電話的費用。



</div>

<div>


> [!NOTE]  
> 並非所有功能都會在所有行動裝置上以完全相同的方式運作。 如需行動裝置上支援之功能的詳細資訊，請參閱 at Mobile Client Comparison Tables <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A> 。 如需支援的裝置和作業系統的詳細資訊，請參閱 <A href="lync-server-2013-planning-for-mobile-clients.md">規劃 Lync Server 2013 中行動用戶端</A>的需求主題。



</div>

當您使用 Lync Server 2013 自動探索功能時，行動應用程式可以自動找出 Lync Server 2013 Web 服務，而不需要使用者在其裝置設定中手動輸入 URLs。 但是也支援在行動裝置設定中手動輸入 URL，主要是用於疑難排解。

<div>


> [!IMPORTANT]  
> Mcx 和 UCWA 都是免費服務，且都是部署來支援 Lync 2010 Mobile 和 Lync 2013 行動用戶端。 Lync 2013 Mobile 將無法登入 Lync Server 2010 部署。 Lync 2010 行動裝置和 Lync 2013 行動裝置將能夠使用 Lync Server 2013 部署，其累計更新為 Lync Server 2013：已套用二月份2013。



</div>

行動功能也可以為不支援在背景執行應用程式的行動裝置，支援「推播通知」**。 推播通知是針對在行動應用程式為非使用中狀態時所發生的事件，傳送給行動裝置的通知。 例如，未接立即訊息 (IM) 邀請可能會產生推播通知。

Lync Server 2013 提供 Mcx、UCWA、自動探索服務及支援推播通知。 更新用戶端功能，並將 UCWA 當作行動性進入點，會在 Lync Server 2013 的累計更新中引進：2月2013。

</div>

<span> </span>

</div>

</div>

</div>

