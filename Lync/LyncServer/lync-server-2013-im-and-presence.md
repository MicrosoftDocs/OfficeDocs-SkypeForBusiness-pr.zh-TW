---
title: Lync Server 2013 IM 及顯示狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IM and presence
ms:assetid: 6a93ae95-3b64-410b-ab72-74dea232f065
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417162(v=OCS.15)
ms:contentKeyID: 48184398
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25fceca5dfb3b308d7f9d545268c258c3e32609c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Lync Server 2013 中的 IM 和目前狀態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

立即訊息 (IM) 和目前狀態會自動安裝在任何 Lync Server 部署中。

*「目前狀態」* 資訊可讓使用者在正確的時間使用正確的通訊方式連絡同事，進而產生更具生產力的工作環境。 使用者的目前狀態是資訊的集合，包括顯示狀態、通訊意願、其他記事 (如位置及狀態)，以及使用者的連絡方式。 Lync Server 中的目前狀態已增強，包含圖片、位置資訊，以及豐富的顯示狀態集，除了基本狀態（如「可用」、「忙碌」和「在會議中」）之外，還包括「離線工作」、「請勿打擾」及「是「正確」等基本狀態。 系統管理員也可以定義自訂的組織特有目前狀態。

連絡人管理及使用者存取選項可讓使用者控制其他人可以看到的資訊。使用者可以設定不同的連絡人層級，而各層級都可以檢視不同的目前狀態資訊層級。

只要查看連絡人清單，使用者就可以快速找到他們需要知道的所有資訊。簡易彩色圖示可指出其他使用者的目前狀態，也會顯示圖片及位置。

透過 Lync Server 與其他產品（如 Outlook 和 SharePoint）之間的整合，每當出現連絡人的名稱時（例如電子郵件訊息或小組網站），也會顯示狀態和連絡人資訊。 此外，如果您部署 Exchange 2013，Lync Server 和 Exchange 2013 可以共用統一連絡人存放區，可供任何產品的用戶端存取。

在 Lync Server 中使用立即訊息，使用者就可以透過及時的資訊快速訊息對方。 如果您願意，您的使用者也可以與公用 IM 網路的使用者通訊，例如 MSN/Windows Live、Yahoo \! 和 AOL。 請注意，與 Windows Live、AOL 和 Yahoo 的公用 IM 連線可能需要個別授權\! Lync Server 也包含可延伸的訊息和顯示狀態通訊協定 (XMPP) 相容性，所以您的使用者可以使用 XMPP 服務（如 Google 交談）的使用者來交換 IM 訊息和目前狀態資訊。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>從2012年9月1日起，Microsoft Lync Public IM 連線使用者訂閱授權 ( 「PIC USL」 ) 不再提供購買新的或更新的協定。 具有使用中授權的客戶將可以繼續與 Yahoo！進行聯盟 信使直到服務關閉日期。 AOL 和 Yahoo！的循環結束日期為2014年6月 已宣告。 如需詳細資訊，請參閱 <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">支援 Lync Server 2013 中的公用立即信使</A>連線。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通訊伺服器與 Yahoo！進行同盟所需的個別使用者每個月訂閱授權 信使。 Microsoft 提供此服務的能力已因 Yahoo！中的支援而產生，其所向下纏繞的底層合約。</P>
> <LI>
> <P>Lync 是一種強大的工具，可跨組織和世界各地的個人進行連線。 與 Windows Live Messenger 的同盟需要 Lync Standard CAL 以外的其他使用者/裝置授權。 隨即會將 Skype 同盟新增至此清單，讓 Lync 使用者可以使用 IM 和語音來傳送成百上千的人員。</P></LI></UL>



</div>

交談記錄可讓使用者追蹤舊的 IM 交談，以及擷取數月前透過 IM 進行通訊的資訊。

Persistent Chat 功能可讓使用者加入一段時間內的多方、主題型交談。 張貼至聊天室 (討論論壇) 的訊息可以持續存在 (也就是長期可用)，因此來自不同位置和部門的人員都可以參與，即使並非同時在線上。

如果您的組織必須遵循規範要求，則可以部署訊息封存功能來封存組織中所有使用者的 IM 訊息內容，或只封存所指定特定使用者的立即訊息內容。 如果您也部署 Exchange 2013，您的 IM 封存可以與 Exchange 的 In-Place 保留功能整合，為您的相容性提供單一的管理經驗。

</div>

<span> </span>

</div>

</div>

</div>

