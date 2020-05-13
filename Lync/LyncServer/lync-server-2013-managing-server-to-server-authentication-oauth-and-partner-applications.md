---
title: 管理伺服器對伺服器驗證（OAuth）和夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f3f32b4e0c13ea68df183d19b020118e32205b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>在 Lync Server 2013 中管理伺服器對伺服器驗證（OAuth）和夥伴應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-14_

Microsoft Lync Server 2013 必須能夠與其他應用程式和伺服器產品進行安全、順利的通訊。 例如，您可以設定 Lync Server 2013，讓連絡人資料和（或）封存資料儲存在 Microsoft Exchange Server 2013 中;不過，只有當 Lync Server 和 Exchange 能夠安全地與彼此進行通訊時，才可執行此動作。 同樣地，您可以在 Microsoft SharePoint Server 中排程 Lync Server 會議；但是，也只有在這兩部伺服器 ((SharePoint 及 Lync Server) 互相信任的情況下，這才有辦法達成。 雖然可以針對 Lync 對 Exchange 通訊使用一種驗證機制，而針對 Lync 對 SharePoint 通訊使用另外一種機制，更好又更有效的方式為針對所有伺服器對伺服器的驗證及授權使用標準化方法。

使用單一標準化方法進行伺服器對伺服器的驗證是 Lync Server 2013 所採用的方法。 針對2013版本，Lync Server 2013 （包括 Exchange 2013 和 Microsoft SharePoint Server）的其他 Microsoft Server 產品都支援伺服器對伺服器驗證和授權的 OAuth （開放授權）通訊協定。 藉由 OAuth (一些主要網站皆使用的標準授權通訊協定)，使用者認證及密碼並不會在電腦間傳遞。 驗證及授權是基於安全性權杖的交換，這些權杖會授與一段特定時間內一組特定資源的存取權。

OAuth 驗證通常涉及三方：單一授權伺服器及兩個需要互相通訊的領域。 （您也可以不使用授權伺服器進行伺服器對伺服器的驗證，這會在本檔稍後將討論的程式。）安全性權杖是由授權伺服器（也稱為安全性權杖伺服器）所發行，以進行通訊的兩個領域;這些權杖會驗證來自某個領域的通訊是否應該由其他領域所信任。 例如，授權伺服器可能會發出權杖，以確認特定 Lync Server 2013 領域的使用者能夠存取指定的 Exchange 2013 領域，反之亦然。

<div>


> [!NOTE]
> 領域只是安全性容器。 Lync Server 2013 預設會使用您的預設 SIP 網域作為其 OAuth 領域。 其他 SIP 命名空間會新增至 OAuth 憑證中的主體替代名稱清單。



</div>

Lync Server 2013 支援三種伺服器對伺服器驗證案例。 使用 Lync Server 2013，您可以：

  - 設定 Lync Server 2013 的內部部署安裝與 Exchange 2013 和/或 Microsoft SharePoint Server 的內部部署安裝之間的伺服器對伺服器驗證。

  - 設定一對 Microsoft 365 元件之間的伺服器對伺服器驗證（例如，在 Microsoft Exchange 和 Microsoft Lync Server 之間，或在 Microsoft Lync Server 和 Microsoft SharePoint 之間）。

  - 在跨部署環境中設定伺服器對伺服器的驗證（也就是在內部部署伺服器與 Microsoft 365 元件之間的伺服器對伺服器驗證）。

請注意，目前只有 Exchange 2013、SharePoint Server 和 Lync Server 2013 支援伺服器對伺服器驗證;如果您未執行這些伺服器之一，您將無法完全執行 OAuth 驗證。

您也應該指出，您不需要使用伺服器對伺服器驗證：不需要伺服器對伺服器驗證即可部署 Lync Server 2013。 如果 Lync Server 2013 不需要與其他伺服器（例如 Exchange 2013）進行通訊，則不需要伺服器對伺服器驗證。

然而，如果要使用 Lync Server 某些新功能 (例如，整合連絡人存放區)，則需要伺服器對伺服器驗證。 使用整合連絡人存放區時，Lync Server 2013 連絡人資訊會儲存在 Exchange 2013 中，而不是儲存在 Lync Server 中;這可讓使用者有一組可在 Lync、Microsoft Outlook 或 Microsoft Outlook Web Access 中輕鬆存取的連絡人。 由於整合的連絡人存放區需要 Lync Server 2013，以與 Exchange 2013 共用資訊，因此您必須使用伺服器對伺服器驗證，才能部署該功能。 如果您選擇使用 Exchange 封存（其中立即訊息會話的記錄會儲存為 Exchange 2013 電子郵件，而不是個別的資料庫記錄），則也需要伺服器對伺服器驗證。

若要讓 Microsoft 365 版本的 Lync Server 與其 Exchange 對應，Lync Server 2013 必須先取得授權伺服器的安全性權杖。 然後，Lync Server 會使用該安全性權杖，將自己識別為 Exchange。 Microsoft 365 版本的 Exchange 必須經過相同的程式，才能與 Lync Server 2013 進行通訊。

不過，對於兩部 Microsoft 伺服器之間的內部部署伺服器對伺服器驗證，則不需要使用協力廠商權杖伺服器。 伺服器產品（如 Lync Server 2013 和 Exchange 2013）具有內建的權杖伺服器，可供與支援伺服器對伺服器驗證之其他 Microsoft 伺服器（例如 SharePoint Server）進行驗證。 例如，Lync Server 2013 可以自行發行並簽署安全性權杖，然後使用該權杖來與 Exchange 2013 通訊。 在這種情況下，便不需要協力廠商權杖伺服器。

若要為 Lync Server 2013 的內部部署執行設定伺服器對伺服器驗證，您必須執行下列兩項作業：

  - 指派憑證給 Lync Server 內建的權杖發行者。

  - 將 Lync Server 2013 通訊的伺服器設定為 "partner application"。 例如，如果 Lync Server 2013 需要與 Exchange 2013 通訊，則您必須將 Exchange 設定為合作夥伴應用程式。

<div>


> [!NOTE]
> 「協力廠商應用程式」是 Lync Server 2013 可以直接交換安全性權杖的任何應用程式，而不需要經過協力廠商安全性權杖伺服器。



</div>

請注意，OAuth 是產品的核心部分，無法停用或移除。

<div>

## <a name="see-also"></a>另請參閱


[將伺服器對伺服器驗證憑證指派給 Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[在跨部署環境中設定 Microsoft Lync Server 2013](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

