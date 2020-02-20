---
title: 管理伺服器對伺服器驗證 (OAuth) 與協力廠商應用程式
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
ms.openlocfilehash: 9bb3ef1bdd01a7c5be5e8d32610a754c54f896c2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-05-14_

Microsoft Lync Server 2013 必須能夠與其他應用程式與伺服器產品通訊的安全，且順暢。 例如，您可以設定 Lync Server 2013 讓，請連絡資料及/或封存的資料會儲存在 Microsoft Exchange Server 2013;不過，這只能執行 Lync 伺服器和 Exchange 是否能夠安全地與彼此通訊。 同樣地，您可以在 Microsoft SharePoint Server 中排程 Lync Server 會議；但是，也只有在這兩部伺服器 ((SharePoint 及 Lync Server) 互相信任的情況下，這才有辦法達成。 雖然可以針對 Lync 對 Exchange 通訊使用一種驗證機制，而針對 Lync 對 SharePoint 通訊使用另外一種機制，更好又更有效的方式為針對所有伺服器對伺服器的驗證及授權使用標準化方法。

使用單一，用於伺服器對伺服器驗證標準化的方法是 Lync Server 2013 所採取的方法。 2013年版本、 Lync Server 2013 （以及其他 Microsoft Server 產品，包括 Exchange 2013 和 Microsoft SharePoint Server） 支援伺服器對伺服器驗證及授權的 OAuth (Open Authorization) 通訊協定。 藉由 OAuth (一些主要網站皆使用的標準授權通訊協定)，使用者認證及密碼並不會在電腦間傳遞。 驗證及授權是基於安全性權杖的交換，這些權杖會授與一段特定時間內一組特定資源的存取權。

OAuth 驗證通常涉及三方：單一授權伺服器及兩個需要互相通訊的領域。 （您也可以執行伺服器對伺服器驗證而不需使用授權伺服器，將討論本文稍後的程序。）安全性權杖是由發給授權伺服器 （也稱為安全性權杖伺服器） 兩個通訊; 所需的領域這些語彙基元確認其他領域應信任來自一個領域的通訊。 例如，授權伺服器發行的權杖可確認來自特定 Lync Server 2013 領域的使用者能夠存取指定的 Exchange 2013 領域，反之亦然。

<div>


> [!NOTE]
> 領域只是安全性容器。 根據預設，Lync Server 2013 會使用預設 SIP 網域，做為其 OAuth 領域。 其他 SIP 命名空間新增至中 OAuth 憑證的主體替代名稱清單。



</div>

Lync Server 2013 支援三個伺服器對伺服器驗證案例。 使用 Lync Server 2013 中，您可以：

  - 設定內部部署安裝 Lync Server 2013 和 Exchange 2013 及/或 Microsoft SharePoint Server 的內部部署安裝之間的伺服器對伺服器驗證。

  - 設定一組的 Office 365 元件 （例如，Microsoft Exchange 和 Microsoft Lync Server 之間或 Microsoft Lync Server 與 Microsoft SharePoint 之間） 之間的伺服器對伺服器驗證。

  - 設定跨單位環境下伺服器對伺服器驗證 (亦即內部安裝伺服器及 Office 365 元件之間的伺服器對伺服器驗證)。

請注意，在目前，只有 Exchange 2013、 SharePoint Server 和 Lync Server 2013 支援伺服器對伺服器驗證;如果您不執行下列其中一個這些伺服器然後您就無法完全實作 OAuth 驗證。

它應該也必須指出您不需要使用伺服器對伺服器驗證： 若要將 Lync Server 2013 部署不需要伺服器對伺服器驗證。 如果不需要 Lync Server 2013 與其他伺服器 （例如 Exchange 2013) 通訊就不需要伺服器對伺服器驗證。

然而，如果要使用 Lync Server 某些新功能 (例如，整合連絡人存放區)，則需要伺服器對伺服器驗證。 Lync Server 2013 的連絡資訊儲存在 Lync Server; 而不是 Exchange 2013 中使用整合連絡人存放區，這可讓使用者將可隨時都能存取 Lync、 Microsoft Outlook 或 Microsoft Outlook Web Access 中的連絡人的單一組。 由於整合連絡人存放區必須使用 Lync Server 2013 到 Exchange 2013 與共用資訊，您必須使用伺服器對伺服器驗證，以部署功能。 如果您選擇使用的 Exchange 封存，為 Exchange 2013 的電子郵件，而非個別資料庫記錄的立即訊息工作階段記錄會儲存，則也需要伺服器對伺服器驗證。

Lync Server 能夠與 Exchange 與對應的 Office 365 版本，Lync Server 2013 必須先取得安全性權杖自驗證伺服器。 Lync Server 然後使用該安全性權杖，來識別本身至 Exchange。 Office 365 的 Exchange 版本必須經過相同的程序，才能與 Lync Server 2013 通訊。

不過，對於兩部 Microsoft 伺服器之間的內部部署伺服器對伺服器驗證，則不需要使用協力廠商權杖伺服器。 例如 Lync Server 2013 和 Exchange 2013 伺服器產品必須可以用於驗證用途，與其他 Microsoft 伺服器 （例如 SharePoint server) 支援伺服器對伺服器驗證的內建權杖伺服器。 例如，Lync Server 2013 可以自行發行並簽署安全性權杖，然後使用該權杖來與 Exchange 2013 通訊。 在這種情況下，便不需要協力廠商權杖伺服器。

若要設定 Lync Server 2013 的內部部署實作的伺服器對伺服器驗證，您必須執行下列兩件事：

  - 指派憑證給 Lync Server 內建的權杖發行者。

  - 設定 Lync Server 2013 將會與通訊設為 「 協力廠商應用程式 」。 例如，如果 Lync Server 2013 需要與 Exchange 2013 通訊表示您必須設定為合作夥伴應用程式的 Exchange。

<div>


> [!NOTE]
> 「 夥伴應用程式 」 是 Lync Server 2013 可以與其直接交換安全性權杖，而不必經過協力廠商安全性權杖伺服器的任何應用程式。



</div>

請注意 OAuth 是產品的核心部分，且無法停用或移除。

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

