---
title: Lync Server 2013： Exchange 和 SharePoint 整合支援
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
ms.openlocfilehash: 262e31ac6049920ca4e327f50dccaae18d69a2f5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange 和 SharePoint 整合支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-01-18_

當您整合這些產品時，lync Server 2013 和 Lync 2013 可以與其他應用程式和伺服器產品（包括 Office 2013、Exchange Server 2013、Exchange Server 2016 及 SharePoint）安全且順利地通訊。 整合 Lync Server 2013 和 Office 提供使用者對立即訊息（IM）、增強型顯示狀態、電話語音功能的存取，以及 Lync 的會議功能。 Office 使用者可以從 Outlook 2013 訊息與共同作業用戶端和其他 Office 程式或從 SharePoint 頁面存取 Lync 功能。 使用者也可以在 [Outlook 交談記錄] 資料夾中查看 Lync 交談記錄。 當與 Exchange 2013、Exchange 2016 或 Exchange Online 整合時，Lync Server 2013 也支援下列各項：

  - 整合連絡人存放區，可讓使用者在 Exchange 或 Exchange Online 中儲存所有連絡人資訊，使其可在 Lync 2013、Exchange、Outlook 和 Outlook Web App 之間取得全域資訊。

  - [交談記錄] 和 [Web 會議史] （儲存在 Exchange 使用者資料夾中）。

  - Lync 的封存內容（例如 IM 和會議內容）可以儲存在 Exchange 儲存區中。

<div>


> [!NOTE]  
> Lync Server 2013 可支援與舊版的 Microsoft Exchange Server 和 SharePoint Server 整合，但並非這些舊版的支援，例如與 Microsoft Exchange 整合存放的功能。<BR>若要將使用者遷移至 Exchange 2013 或 Exchange 2016，您可以在完成遷移時，定期使用 Exchange storage 和 Lync Server storage。 不支援永久使用 Exchange 和 Lync Server 存放區。



</div>

將 Lync Server 2013 與 Exchange Server 和 SharePoint Server 整合，需要執行 Lync Server 2013、Exchange Server 和 SharePoint Server 的伺服器之間的伺服器對伺服器驗證。 Lync Server 2013 支援伺服器對伺服器驗證和授權的 OAuth （開放授權）通訊協定。 針對 Microsoft 伺服器之間的內部部署伺服器對伺服器驗證，並不需要使用協力廠商 Token 伺服器。 Lync Server 2013、Exchange Server 和 SharePoint 伺服器都有內建的權杖伺服器，可用於彼此進行驗證。 例如，Lync Server 2013 可以自行發行和簽署安全性權杖，並在與 Exchange 通訊時使用該權杖。 在此情況下，則不需要使用協力廠商 Token 伺服器。

Lync Server 2013 支援兩種伺服器對伺服器驗證案例。 這包括設定下列各項之間的伺服器對伺服器驗證：

  - Lync Server 2013 的內部部署安裝和 Exchange Server 2013、Exchange Server 2016 和/或 SharePoint 伺服器的內部部署安裝。

  - 一對 Office 元件（例如，在 Microsoft Exchange 365 和 Microsoft Lync Server 365 之間，或 Microsoft Lync Server 365 和 Microsoft SharePoint 365）。

<div>


> [!NOTE]  
> 在此 Lync Server 2013 版本中不支援內部部署伺服器與 Microsoft 365 或 Office 365 元件之間的伺服器對伺服器驗證。 此外，這表示您無法設定 Lync Server 2013 和 Microsoft Exchange 365 的內部部署安裝之間的伺服器對伺服器驗證。



</div>

如需伺服器對伺服器驗證的詳細資訊，請參閱部署檔或作業檔中的[管理 Lync server 2013 中的伺服器對伺服器驗證（OAuth）和夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

</div>

<span> </span>

</div>

</div>

</div>
