---
title: Lync Server 2013：與 Microsoft Exchange Server 2013 整合
description: Lync Server 2013：與 Microsoft Exchange Server 2013 整合。
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
ms.openlocfilehash: 54ab4a81e5455bc0a44677b1509876f39ff4d985
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543979"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-07-09_

Exchange 和 Lync Server 的整合和相容性很長。 這種整合在各自的用戶端應用程式內最為明顯。 例如，您可以在 Microsoft Outlook 中報告 Lync 目前狀態資訊。同樣地，Lync 也可以使用 Outlook calendar 來自動更新該顯示狀態資訊。  (例如，當您的行事曆顯示您已排程的會議時，Lync 可以將您的狀態變更為「忙碌」。 ) 雖然您不需要執行 Exchange 來執行 Lync Server (或反過來) ，但很不確定使用這兩種產品 epitomizes 非常定義的字詞「一起」。

在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的版本中，尤其如此。 除了 Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中所提供的功能（如整合通訊和 IM 及目前狀態）之外，該伺服器產品的2013版本也包含許多新功能。 這些功能包含下列項目：

  - **Lync 封存整合**。 在 Lync 2013 Server 中，系統管理員仍然可以選擇將立即訊息和 Web 會議記錄封存至 SQL Server (與這些記錄在 Lync Server 2010) 中封存的方式相同。 不過，系統管理員也可以選擇將工作封存為 Exchange 2013，將這些記錄儲存在個別使用者信箱中，與 Exchange 封存通訊的方式相同。 這表示從 Exchange 和 Lync Server) 中 (所有電子通訊的單一存放庫，可讓您在需要發生時，搜尋及找回那些已封存的通訊更為容易。

  - **整合的連絡人存放區**。 在 Lync Server 2010 中，使用者必須在 Outlook 和 Lync 中維護不同的連絡人清單。實際上，為了確保這兩種產品都能使用相同的連絡人，您必須維護重複的連絡人清單，一個用於 Outlook，另一個用於 Lync。 不過，使用 Lync Server 2013，使用者連絡人可以儲存在 Exchange 2013 和整合連絡人存放區中。 使用單一連絡人存放區可讓使用者只保留一組連絡人，並在 Lync 2013、Outlook 2013 和 Outlook Web Access 2013 中提供相同的連絡人集。

  - **來自 OWA 的 Lync 會議排程**。 透過 Lync Server 2013 和 Exchange 2013 整合，使用者可以從 Outlook Web Access 2013 排程 Lync 會議。

  - **高解析度相片**。 Lync 2010 只會顯示您的連絡人的小照片;這是因為這些相片儲存在 Active Directory 中，而且 Active Directory 在儲存的相片上會有48圖元的大小限制，以48圖元為單位。 不過，使用 Lync Server 2013，相片可以儲存在 Microsoft Exchange 中;可提供高解析度的相片，最大648圖元乘以648圖元。 如您所料，Lync 2013 已升級為允許顯示這些高解析度照片。

請記住，這些新功能需要同時使用 Lync Server 2013 和 Exchange 2013。 除此之外，希望充分利用這些新功能的使用者，必須在 Lync Server 2013 和 Exchange 2013 上具有帳戶，而且必須使用最新版的用戶端軟體 (例如 Lync 2013) 。 例如，已駐留在 Lync Server 2010 上的使用者無法使用整合連絡人存放區;同樣地，無法在 Lync 2010 中顯示高解析度照片。

這份檔提供有關整合 Lync Server 2013 和 Exchange 2013 的資訊。 包含啟用新功能（如封存整合和整合連絡人存放區）的逐步資訊。 這兩種產品的初始設定和設定都不是本檔的功能。 如需部署 Lync Server 2013 的詳細資訊，請參閱 Lync Server 2013 技術中心，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127) 。 如需部署 Exchange 2013 的詳細資訊，請參閱 Exchange 2013 技術中心，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528) 。

<div>

## <a name="in-this-section"></a>本章節內容

[整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的必要條件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定合作夥伴應用程式](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[設定 Microsoft Lync Server 2013 以使用 Microsoft Exchange Server 2013 封存](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[設定 Microsoft SharePoint Server 2013 以搜尋封存的 Microsoft Lync Server 2013 資料](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[設定 Microsoft Lync Server 2013 以使用整合連絡人存放區](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[在 Microsoft Lync Server 2013 中設定高解析度相片的使用](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[針對 Microsoft Lync Server 2013 語音信箱設定 Microsoft Exchange Server 2013 整合通訊](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[整合 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

