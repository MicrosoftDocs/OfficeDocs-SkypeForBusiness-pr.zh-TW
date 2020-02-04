---
title: Lync Server 2013：定義前端伺服器、立即訊息及顯示狀態的需求
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
ms.openlocfilehash: af371d116948d348b49c552dfe53290c1dae1900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>在 Lync Server 2013 中定義前端伺服器、立即訊息及顯示狀態的需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

規劃 [立即訊息（IM）] 和 [目前狀態] 的主要工作是確保您的使用者擁有足夠的前端伺服器。

<div>

## <a name="enabling-communication-with-external-users"></a>啟用與外部使用者的通訊

您可以讓您的使用者與外部使用者通訊，大幅提高您在 Lync 伺服器投資的益處。 外部使用者可以包括：

  - ****    如果您組織的使用者是在您的防火牆外工作，且正在使用其膝上型電腦或其他 Lync Server 裝置，則可供遠端使用者使用。

  - **同盟使用者**   與公司合作的使用者，您可與其他人同時執行 Lync Server。 若要讓您的使用者能夠輕鬆地與這些使用者聯繫，您可以建立與這些公司的聯盟關聯。

  - ****    公用 IM 服務的公用使用者使用者，例如由 Internet 服務、Yahoo\!和 AOL 的 Windows Live 網路所提供的 IM 服務，以及使用可擴展訊息和目前狀態通訊協定（XMPP）的提供者和伺服器（例如 Google 交談）的使用者。
    
    <div>
    

    > [!NOTE]  
    > 請注意，對於使用 Windows Live、AOL 和 Yahoo！的公用 IM 連線，可能需要個別的授權

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>從2012年9月1日起，Microsoft Lync 公用 IM 連線使用者訂閱授權（「PIC USL」）已不再提供購買新或續約協定的功能。 擁有作用中授權的客戶將能夠繼續與 Yahoo！進行聯盟 信使，直到服務關閉日期為止。 AOL 和 Yahoo！的存留期結束日期為2014年6月 已公佈。 如需詳細資訊，請參閱<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公用立即信使連線支援</A>。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通訊伺服器要與 Yahoo！聯盟時所需的每個使用者每月訂閱授權 名單. Microsoft 提供此服務的能力已因 Yahoo！的支援而定，並向下纏繞的基礎協定。</P>
    > <LI>
    > <P>Lync 是一種功能強大的工具，可跨組織與世界各地的人員連線。 與 Windows Live Messenger 的同盟不需要在 Lync 標準 CAL 以外的其他使用者/裝置授權。 您可以在這個清單中新增 Skype 同盟，讓 Lync 使用者能夠使用 IM 和語音來與成百上千的人取得聯繫。</P></LI></UL>

    
    </div>

若要啟用任何一種或所有案例，您必須部署邊緣伺服器，以協助您在 Lync Server 部署與外部使用者之間進行安全通訊。 貴組織的遠端使用者和聯盟組織中的使用者將能夠彼此查看其目前狀態並使用 IM 進行通訊。 如需有關如何啟用與外部使用者的通訊的詳細資訊，請參閱規劃檔中的[Lync Server 2013 規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)。

</div>

<div>

## <a name="archiving-im-content"></a>封存 IM 內容

如果您的組織必須遵循合規性規範，Lync Server 提供您可以使用的功能。 您可以使用 [封存] 來封存貴組織中所有使用者的 IM 訊息內容，或只針對您指定的特定使用者封存 IM 訊息的內容。 如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的存檔規劃](lync-server-2013-planning-for-archiving.md)。

如果您也已部署 Microsoft Exchange Server 2013，您可以將 Exchange 資料的存檔與 Lync 伺服器資料的存檔整合，然後使用單一工具來搜尋這兩種類型的已歸檔資料。 如需詳細資訊，請參閱設定[Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 歸檔](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

