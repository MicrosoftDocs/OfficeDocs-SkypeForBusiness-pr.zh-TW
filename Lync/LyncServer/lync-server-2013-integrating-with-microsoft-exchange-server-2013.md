---
title: 'Microsoft Exchange Server 2013 與整合 Lync Server 2013:'
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
ms.openlocfilehash: 489c5023ab995700762fa5e19ba361df1b49a6b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-07-09_

Exchange 和 Lync Server 具有整合和相容性的長歷程記錄。 這項整合是最明顯其各自的用戶端應用程式內。 例如，在 Microsoft Outlook 中報告 Lync 目前狀態資訊同樣地，Lync 可用於 Outlook 行事曆的目前狀態資訊會自動更新。 （例如，Lync 可以變更您的狀態為忙碌任何時間行事曆中顯示您已排定的會議。）雖然您不需要執行 Exchange，以執行 Lync Server （反之亦然） 沒有小有疑問，同時使用這兩項產品 epitomizes 非常術語的定義更妥善地 」 放在一起。 」

特別是與 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的版本。 除了功能，例如整合通訊和 IM 和目前狀態，Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中找到的伺服器產品的 2013年版本會包含新功能的數的字。 這些功能包含下列項目：

  - **Lync 封存整合**。 Lync Server 2013 中的系統管理員仍然可以選擇讓立即訊息和 Web 會議記錄封存至 SQL Server （這些記錄已封存 Lync Server 2010 中的相同方式）。 或者，不過，系統管理員可以選擇讓記錄封存至 Exchange 2013 中，將這些記錄之個別使用者信箱中儲存在 Exchange 中封存的通訊的方式相同。 這表示在單一存放庫的所有電子通訊 （從 Exchange 和 Lync 伺服器），讓更容易搜尋並擷取這些封存的通訊應該需要發生。

  - **整合的連絡人存放區**。 在 Lync Server 2010 中，使用者必須維護在 Outlook 和 Lync; 中的個別連絡人清單事實上，以確保您具有相同您必須維護重複這兩個產品中可用的連絡人連絡清單，一個適用於 Outlook，一個 lync。 搭配 Lync Server 2013，不過，使用者的連絡人可以儲存在 Exchange 2013 和整合連絡人存放區。 使用單一的連絡人存放區可讓使用者維護與連絡人不會出現在 Lync 2013、 Outlook 2013 和 Outlook Web Access 2013 中的同一組只是一組連絡人。

  - **從 OWA 排程 Lync 會議**。 與 Lync Server 2013 和 Exchange 2013 整合，使用者可以排程 Lync 會議，從 Outlook Web Access 2013。

  - **高解析度相片**。 Lync 2010 可能只會顯示小型的連絡人; 相片這是因為這些相片被儲存在 Active Directory，以及 Active Directory 施加 48 個像素的預存的相片 48 個像素大小限制。 搭配 Lync Server 2013，不過，相片可以儲存在 Microsoft Exchange;可讓高解析度相片高達 648 像素 x 648 像素為單位。 如您所預期，Lync 2013 已升級為允許這些高解析度相片的顯示。

請記住，這些新功能需要使用 Lync Server 2013 和 Exchange 2013。 所，希望能夠充分利用這些新功能的使用者必須能夠在 Lync Server 2013 和 Exchange 2013 的帳戶，且必須使用最新版的用戶端軟體 (例如，Lync 2013)。 例如，且無法供具有已位於 Lync Server 2010; 使用者整合連絡人存放區同樣地，高解析度相片無法顯示在 Lync 2010。

這份文件提供整合 Lync Server 2013 和 Exchange 2013 的相關資訊。 包括上啟用新功能，例如封存整合和整合連絡人存放區的逐步說明資訊。 這份文件不會不做什麼是討論的初始安裝與設定下列兩項產品。 如需 Lync Server 2013 部署的詳細資訊，請參閱 Lync Server 2013 技術中心，在[https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127)。 如需 Exchange 2013 部署的詳細資訊，請參閱在 Exchange 2013 Tech Center [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528)。

<div>

## <a name="in-this-section"></a>本章節內容

[整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的必要條件](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定夥伴應用程式](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[設定 Microsoft Lync Server 2013 使用 Microsoft Exchange Server 2013 封存](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[設定 Microsoft SharePoint Server 2013 搜尋已封存的 Microsoft Lync Server 2013 資料](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[設定 Microsoft Lync Server 2013 使用整合連絡人存放區](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[在 [Microsoft Lync Server 2013 中設定使用高解析度相片](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[設定 Microsoft Exchange Server 2013 整合通訊的 Microsoft Lync Server 2013 語音信箱](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[整合 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

