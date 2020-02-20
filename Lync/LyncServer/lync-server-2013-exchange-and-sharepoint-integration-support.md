---
title: 'Lync Server 2013: Exchange 與 SharePoint 整合支援'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdfaffa12d84b57f0ae0203ebc14491bb6d8d4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange 和 SharePoint 整合支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-01-18_

Lync Server 2013 和 Lync 2013 可以安全地傳達順暢地與其他應用程式和伺服器產品，包括 Office 2013、 Exchange Server 2013、 Exchange Server 2016 和 SharePoint 中，如果您在整合這些產品。 整合 Lync Server 2013 和 Office 提供的內容存取的使用者的立即訊息 (IM)、 增強顯示狀態、 電話語音] 和 Lync 會議功能。 Office 使用者可以存取 Lync 功能從 Outlook 2013 通訊和共同作業用戶端和其他 Office 程式中，或是從 SharePoint] 頁面。 使用者也可以檢視 Lync 交談記錄中的 Outlook 交談歷程記錄資料夾。 當與 Exchange 2013、 Exchange 2016 或 Exchange Online 整合，Lync Server 2013 也支援下列項目：

  - 整合連絡人存放區，讓使用者可以將所有聯絡人資訊儲存在 Exchange 或 Exchange Online，以便資訊皆可全域 Lync 2013、 Exchange、 Outlook 和 Outlook Web App。

  - 交談歷程記錄和 Web 會議歷程記錄，也就是在 Exchange 中儲存使用者資料夾。

  - 從 Lync IM 和會議內容，例如封存的內容可以儲存在 Exchange 儲存區。

<div>


> [!NOTE]  
> Lync Server 2013 支援與舊版 Microsoft Exchange Server 與 SharePoint Server 的整合，但這些先前的版本，例如封存存放區與 Microsoft Exchange 整合支援並非所有的功能。<BR>如果您將您的使用者移轉至 Exchange 2013 或 Exchange 2016，您可以使用 Exchange 儲存區與 Lync Server 儲存區基礎過渡，當您完成移轉。 不支援永久使用 Exchange 與 Lync Server 儲存區。



</div>

整合的 Lync Server 2013 與 Exchange Server 和 SharePoint Server 需要執行 Lync Server 2013、 Exchange Server 和 SharePoint Server 的伺服器之間的伺服器對伺服器驗證。 Lync Server 2013 支援伺服器對伺服器驗證及授權的 OAuth (Open Authorization) 通訊協定。 針對 Microsoft 伺服器之間的內部部署伺服器對伺服器驗證，並不需要使用協力廠商 Token 伺服器。 Lync Server 2013、 Exchange Server 和 SharePoint Server 具有內建的權杖伺服器可以用於驗證目的彼此。 例如，Lync Server 2013 可以發出簽署安全性權杖由本身，並與 Exchange 進行通訊時使用該權杖。 在此情況下，則不需要使用協力廠商 Token 伺服器。

Lync Server 2013 支援兩個伺服器對伺服器驗證案例。 這些功能包括下列之間的伺服器對伺服器驗證的設定：

  - Lync Server 2013 和 Exchange Server 2013、 Exchange Server 2016、 和/或 SharePoint Server 的內部部署安裝的內部部署安裝。

  - 一組 Office 元件 （例如，Microsoft Exchange 365 和 Microsoft Lync Server 365，之間或 Microsoft Lync Server 365 及 Microsoft SharePoint 365 之間）。

<div>


> [!NOTE]  
> 此 Lync Server 2013 版本不支援在內部伺服器與 Office 365 元件之間的伺服器對伺服器驗證。 除此之外，這表示您無法設定內部部署安裝 Lync Server 2013 和 Microsoft Exchange 365 之間的伺服器對伺服器驗證。



</div>

如需有關伺服器對伺服器驗證的詳細資訊，請參閱部署文件或作業文件中的[管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

</div>

<span> </span>

</div>

</div>

</div>

