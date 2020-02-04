---
title: 管理伺服器對伺服器驗證（OAuth）與合作夥伴應用程式
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
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>在 Lync Server 2013 中管理伺服器間驗證（OAuth）與合作夥伴應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-14_

Microsoft Lync Server 2013 必須能夠與其他應用程式和伺服器產品進行安全且嚴密的通訊。 例如，您可以設定 Lync Server 2013，讓連絡人資料和/或歸檔資料儲存在 Microsoft Exchange Server 2013 中;不過，只有當 Lync Server 和 Exchange 能夠安全地與其他人通訊時，才能進行這項操作。 同樣地，您可以在 Microsoft SharePoint Server 中排程 Lync Server 會議;不過，這只會在兩個伺服器（SharePoint 和 Lync Server）相互信任時才執行。 雖然您可以使用一種驗證機制進行 Lync 到 Exchange 通訊，以及讓 Lync 對 SharePoint 通訊的另一種機制，但更好且更有效的方法是針對所有伺服器到伺服器使用標準化的方法。驗證和授權。

使用單一、標準化的伺服器到伺服器驗證方法，就是 Lync Server 2013 所採用的方法。 針對2013版本，Lync Server 2013 （以及其他 Microsoft Server 產品，包括 Exchange 2013 和 Microsoft SharePoint Server）支援用於伺服器到伺服器驗證和授權的 OAuth （開放授權）通訊協定。 使用 OAuth （由許多主要網站使用的標準授權通訊協定），使用者認證和密碼不會從一部電腦傳送到另一部電腦。 相反地，驗證與授權是以安全權杖的交換為基礎;這些標記會針對特定的一組資源，授予存取權。

OAuth 驗證通常涉及三個參與方：單一授權伺服器，以及需要彼此通訊的兩個領域。 （您也可以執行伺服器對伺服器驗證，而不使用授權伺服器，本檔稍後會討論的程式。）安全權杖是由授權伺服器（也稱為安全權杖伺服器）頒發給需要通訊的兩個領域;這些權杖會確認源自某個領域的通訊應該受到其他領域的信任。 例如，授權伺服器可能會頒發標記，以驗證來自特定 Lync Server 2013 領域的使用者可以存取指定的 Exchange 2013 領域，反之亦然。

<div>


> [!NOTE]
> 領域只是一個安全性容器。 根據預設，Lync Server 2013 會使用您的預設 SIP 網域作為其 OAuth 領域。 其他 SIP 命名空間會新增至 OAuth 憑證中的 [Subject 替換名稱] 清單。



</div>

Lync Server 2013 支援三種伺服器對伺服器驗證案例。 使用 Lync Server 2013，您可以：

  - 在 Lync Server 2013 的內部部署安裝與 Exchange 2013 和/或 Microsoft SharePoint Server 的內部部署安裝之間設定伺服器對伺服器驗證。

  - 在一對 Office 365 元件（例如，在 Microsoft Exchange 與 Microsoft Lync Server 之間，或在 Microsoft Lync Server 與 Microsoft SharePoint 之間）設定伺服器對伺服器驗證。

  - 在跨內部部署環境中設定伺服器對伺服器驗證（也就是在內部部署伺服器與 Office 365 元件之間的伺服器對伺服器驗證）。

請注意，在這個時間點，只有 Exchange 2013、SharePoint Server 和 Lync Server 2013 支援伺服器對伺服器驗證;如果您沒有執行其中一個伺服器，您將無法完全實現 OAuth 驗證。

您也應該指出，您不需要使用伺服器對伺服器驗證：您不需要使用伺服器對伺服器驗證，即可部署 Lync Server 2013。 如果 Lync Server 2013 不需要與其他伺服器通訊（例如 Exchange 2013），則不需要伺服器對伺服器驗證。

不過，如果您想要使用 Lync 伺服器的一些新功能（例如「整合連絡人存放區」），則必須使用伺服器對伺服器驗證。 在 [整合連絡人存放區] 中，Lync Server 2013 連絡人資訊會儲存在 Exchange 2013 中，而非 Lync Server 中;這可讓使用者擁有一組可在 Lync、Microsoft Outlook 或 Microsoft Outlook Web Access 中輕鬆存取的單一連絡人。 因為「整合連絡人存放區」需要 Lync Server 2013 來與 Exchange 2013 共用資訊，所以您必須使用伺服器對伺服器驗證，才能部署該功能。 如果您選擇使用 Exchange 封存，且在其中將立即訊息會話的腳本儲存為 Exchange 2013 電子郵件，而不是個別的資料庫記錄，也需要伺服器對伺服器驗證。

若要讓 Office 365 版本的 Lync Server 與其 Exchange 對應專案通訊，Lync Server 2013 必須先從授權伺服器取得安全權杖。 接著 Lync Server 會使用該安全權杖來識別 Exchange 本身。 Office 365 版本的 Exchange 必須經過同一個處理常式，才能與 Lync Server 2013 進行通訊。

不過，對於兩個 Microsoft 伺服器之間的內部部署伺服器與伺服器驗證，不需要使用協力廠商的權杖伺服器。 伺服器產品（例如 Lync Server 2013 和 Exchange 2013）有內建的權杖伺服器，可用於針對支援伺服器對伺服器驗證的其他 Microsoft 伺服器（例如 SharePoint Server）進行驗證。 例如，Lync Server 2013 可以自行發出並簽署安全權杖，然後使用該權杖與 Exchange 2013 進行通訊。 在這種情況下，不需要使用協力廠商的權杖伺服器。

若要為 Lync Server 2013 的內部部署實現設定伺服器對伺服器驗證，您必須執行下列兩項動作：

  - 將憑證指派給 Lync Server 的內建權杖頒發者。

  - 設定 Lync Server 2013 將與其通訊的伺服器為「合作夥伴應用程式」。 例如，如果 Lync Server 2013 需要與 Exchange 2013 通訊，則您必須將 Exchange 設定為合作夥伴應用程式。

<div>


> [!NOTE]
> 「合作夥伴應用程式」是 Lync Server 2013 可以直接與 exchange 安全權杖交換的任何應用程式，而不需要經過協力廠商安全權杖伺服器。



</div>

請注意，OAuth 是產品的核心元件，且無法停用或移除。

<div>

## <a name="see-also"></a>請參閱


[指派伺服器對伺服器驗證憑證至 Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[在跨內部部署環境中設定 Microsoft Lync Server 2013](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

