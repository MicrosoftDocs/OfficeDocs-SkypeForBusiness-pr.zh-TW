---
title: Lync Server 2013：與 Microsoft Exchange Server 2013 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-09_

Exchange 和 Lync Server 的整合與相容性較長。 這個整合在各自的用戶端應用程式中最明顯。 例如，您可以在 Microsoft Outlook 中報告 Lync 目前狀態資訊。同樣地，Lync 可以使用 Outlook 行事歷來自動更新該目前狀態資訊。 （例如，Lync 可隨時將您的狀態變更為 [忙碌]，行事曆會顯示您已排程會議。）雖然您不需要執行 Exchange，就能執行 Lync Server （或反之），不過您不一定要使用這兩個產品一起 epitomizes [更好地配合] 的定義。

在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的發行中，尤其如此。 除了 Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中的 [整合郵件] 和 [IM 與目前狀態] 等功能之外，伺服器產品的2013版本都包含許多新功能。 這些功能包括下列各項：

  - **Lync 存檔整合**。 在 Lync Server 2013 中，系統管理員仍能選擇將即時消息和網路會議記錄存檔至 SQL Server （與在 Lync Server 2010 中歸檔這些記錄的方式相同）。 或者，管理員可以選擇將記錄歸檔至 Exchange 2013，將這些記錄儲存在個別的使用者信箱中，就像 Exchange 存檔通訊一樣。 這代表所有電子通訊的單一儲備庫（來自 Exchange 和 Lync Server），可讓您更輕鬆地搜尋及取回那些已歸檔的通訊（如果需要）。

  - **整合連絡人存放區**。 在 Lync Server 2010 中，使用者必須在 Outlook 和 Lync 中維護獨立的連絡人清單;事實上，若要確保您在兩種產品中都能使用相同的連絡人，您必須維護重複的連絡人清單，一個適用于 Outlook，另一個適用于 Lync。 不過，您可以使用 Lync Server 2013，將使用者連絡人儲存在 Exchange 2013 和整合連絡人存放區中。 使用單一連絡人存放區可以讓使用者只保留一組連絡人，並在 Lync 2013、Outlook 2013 和 Outlook Web Access 2013 中提供相同的連絡人集合。

  - **從 OWA 進行 Lync 會議排程**。 透過 Lync Server 2013 與 Exchange 2013 整合，使用者可以從 Outlook Web Access 2013 排程 Lync 會議。

  - **高解析度相片**。 Lync 2010 只能顯示較小的連絡人相片，這是因為這些相片是儲存在 Active Directory 中，而 Active Directory 在儲存的相片上以48圖元大小限制的方式來強加48圖元。 不過，有了 Lync Server 2013，相片可以儲存在 Microsoft Exchange 中;這可讓高解析度相片的大小為648圖元乘648圖元。 您可能會想到，Lync 2013 已升級為允許顯示這些高解析度相片。

請記住，這些新功能需要同時使用 Lync Server 2013 和 Exchange 2013。 此外，想要充分利用這些新功能的使用者，都必須在 Lync Server 2013 和 Exchange 2013 上擁有帳戶，且必須使用最新版本的用戶端軟體（例如 Lync 2013）。 例如，已在 Lync Server 2010 上託管的使用者無法使用「整合連絡人存放區」;同樣地，在 Lync 2010 中無法顯示高解析度相片。

本檔提供集成 Lync Server 2013 與 Exchange 2013 的相關資訊。 包括啟用新功能（例如，歸檔整合與整合連絡人存放區）的逐步資訊。 本檔中的內容不會討論這兩個產品的初始設定和配置。 如需有關部署 Lync Server 2013 的詳細資訊，請參閱 Lync Server [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)2013 技術中心（位於）。 如需有關部署 Exchange 2013 的詳細資訊，請參閱 Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)2013 技術中心。

<div>

## <a name="in-this-section"></a>本節內容

[整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013 的先決條件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定合作夥伴應用程式](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[將 Microsoft Lync Server 2013 設定為使用 Microsoft Exchange Server 2013 歸檔](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[設定 Microsoft SharePoint Server 2013 以搜尋已歸檔的 Microsoft Lync Server 2013 資料](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[將 Microsoft Lync Server 2013 設定為使用整合連絡人存放區](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[在 Microsoft Lync Server 2013 中設定高解析度相片的使用](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[針對 Microsoft Lync Server 2013 語音信箱設定 Microsoft Exchange Server 2013 整合通訊](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[整合 Microsoft Lync Server 2013 與 Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

