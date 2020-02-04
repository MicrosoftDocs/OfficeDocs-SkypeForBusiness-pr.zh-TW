---
title: Lync Server 2013 IM 和目前狀態
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
ms.openlocfilehash: 57f57d4fae488a7d4946a0adb1f8350d02114a7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="im-and-presence-in-lync-server-2013"></a>Lync Server 2013 中的 IM 和目前狀態

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-10-07_

[立即訊息（IM）] 和 [目前狀態] 會自動安裝在任何 Lync Server 部署中。

目前*狀態*資訊可讓使用者在適當的時間以適當的溝通方式來處理同事，以提高工作環境的效率。 使用者的目前狀態是資訊的集合，包括可用性、溝通意願、其他記事（例如位置與狀態），以及如何聯繫使用者。 Lync Server 中的目前狀態會隨著圖片、位置資訊以及豐富的目前狀態，包括「已提供」、「請勿打擾」和「立即返回」等基本狀態（例如「可用」、「忙碌」」和「在會議中」）。 系統管理員也可以定義自訂的組織特定的目前狀態。

連絡人管理與使用者存取選項可讓使用者控制其他人可以看到的資訊。 使用者可以設定不同層級的連絡人，每一個都可以查看不同層級的目前狀態資訊。

只要查看連絡人清單，使用者就能一目了然地找到他們需要瞭解的所有專案。 簡單的彩色圖示會指出其他使用者的目前狀態，同時也會顯示圖片和位置。

隨著 Lync Server 與其他產品（例如 Outlook 與 SharePoint）之間的整合，只要出現連絡人的名稱（例如在電子郵件訊息中或在小組網站上），也會顯示狀態和連絡人資訊。 此外，如果您部署 Exchange 2013，Lync Server 和 Exchange 2013 可以共用整合的連絡人存放區，這可由任何一種產品的用戶端存取。

在 Lync Server 中使用立即訊息，使用者就可以使用及時的資訊彼此快速地傳送訊息。 如果您想要的話，您的使用者也可以與公用 IM 網路（例如 MSN/Windows Live、Yahoo\!和 AOL）的使用者通訊。 請注意，對於使用 Windows Live、AOL 和 Yahoo 的公用 IM 連線，可能需要個別的授權\! Lync 伺服器也包括可擴展的訊息和目前狀態通訊協定（XMPP）相容性，因此您的使用者可以與 Google 交談等 XMPP 服務的使用者交換 IM 訊息和目前狀態資訊。

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

[交談記錄] 可讓使用者追蹤舊的 IM 交談，並檢索可能已透過 IM 月前訊息所傳達的資訊。

[持續聊天] 功能可讓使用者參與在一段時間內持續存在的多方主題交談。 張貼到聊天室的訊息（討論論壇）可能是永久性的（也就是隨著時間提供），因此來自不同位置和部門的人員都可以參與，即使他們不是同時在線上。

如果您的組織必須遵循合規性規範，您可以部署郵件封存功能，以封存您組織中所有使用者的立即訊息內容，或只針對您指定的特定使用者封存立即訊息的內容。 如果您同時部署 Exchange 2013，您的 IM 封存可以與 Exchange 的就地保留功能整合，為您的合規性提供單一的管理體驗。

</div>

<span> </span>

</div>

</div>

</div>

