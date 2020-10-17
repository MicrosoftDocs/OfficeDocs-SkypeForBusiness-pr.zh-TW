---
title: Lync Server 2013：定義前端伺服器、立即訊息及顯示狀態的需求
description: Lync Server 2013：定義前端伺服器、立即訊息及顯示狀態的需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 923132b32d5aef80191b19a7b85c3f17276e5946
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545369"
---
# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>在 Lync Server 2013 中定義前端伺服器、立即訊息及顯示狀態的需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

規劃立即訊息 (IM) 和目前狀態的主要工作，是要確保您有足夠的前端伺服器供使用者使用。

<div>

## <a name="enabling-communication-with-external-users"></a>啟用與外部使用者的通訊

您可以讓使用者與外部使用者通訊，以大幅提高在 Lync Server 中投資的效益。 外部使用者包括：

  - **遠端使用者**    組織本身的使用者，當他們在防火牆外工作時使用其膝上型電腦或其他 Lync Server 裝置。

  - 同盟**使用者**    公司的使用者，您也可以使用 Lync Server。 為了方便您的使用者輕鬆連絡這些使用者，您可以和這些公司建立同盟關係。

  - **公用使用者**    公用 IM 服務的使用者，例如網際網路服務、Yahoo 和 AOL 的 Windows Live 網路所提供的 IM 服務， \! 以及使用可擴展郵件和顯示狀態通訊協定 (XMPP) （如 Google 交談）的提供者和伺服器使用者。
    
    <div>
    

    > [!NOTE]  
    > 等公用 IM 進行連線可能需要個別授權

    
    </div>
    
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

若要啟用任何或所有上述案例，您必須部署 Edge Server，以協助啟用 Lync Server 部署與外部使用者之間的安全通訊。 貴組織的遠端使用者和同盟組織的使用者，將能夠看到彼此的目前狀態，並使用 IM 進行通訊。 如需啟用與外部使用者通訊的詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的外部使用者存取](lync-server-2013-planning-for-external-user-access.md) 。

</div>

<div>

## <a name="archiving-im-content"></a>封存 IM 內容

當您的組織必須遵循法規遵從性規定時，Lync Server 會提供您可以使用的功能。 您可以使用封存為組織中的所有使用者或您指定的特定使用者封存 IM 訊息的內容。 如需詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的](lync-server-2013-planning-for-archiving.md) 封存。

如果您也部署 Microsoft Exchange Server 2013，您可以將 Exchange 資料的封存與 Lync Server 資料的封存整合，並使用單一工具來搜尋這兩種類型的封存資料。 如需詳細資訊，請參閱設定 [Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)封存。

</div>

</div>

<span> </span>

</div>

</div>

</div>

