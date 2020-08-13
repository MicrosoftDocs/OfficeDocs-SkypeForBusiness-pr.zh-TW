---
title: Lync Server 2013：與 Exchange Server 2013 整合的必要條件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ea70be8c4d431b6231b1cf8e8dc252581643b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的必要條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

您必須先確定已完成所有必要步驟，才能整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013。 如您所料，在 Exchange 2013 和 Lync Server 2013 完整安裝及執行之前，不會發生整合。 如需安裝 Exchange 的詳細資訊，請參閱 Exchange 2013 規劃和部署檔，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539) 。 如需安裝 Lync Server 2013 的詳細資訊，請參閱規劃和部署檔，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806) 。

在執行伺服器並執行後，您必須將伺服器對伺服器驗證憑證指派給 Lync Server 2013 和 Exchange 2013;這些憑證可讓 Lync Server 和 Exchange 交換資訊，並彼此通訊。 當您安裝 Exchange 2013 時，會為您建立具有名稱為 Microsoft Exchange Server 驗證憑證的自我簽署憑證。 此憑證可以在本機電腦憑證存放區中找到，以供 Exchange 2013 上的伺服器對伺服器驗證使用。 如需在 Exchange 2013 中指派憑證的詳細資訊，請參閱的「設定郵件流程和用戶端存取」 [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540) 。

對於 Lync Server 2013，您可以使用現有的 Lync Server 憑證作為伺服器對伺服器驗證憑證;例如，您的預設憑證也可以當做 OAuthTokenIssuer 憑證使用。 Lync Server 2013 可讓您使用任何網頁伺服器憑證作為伺服器對伺服器驗證的憑證，但前提是：

  - 憑證包含 [主旨] 欄位中的 SIP 網功能變數名稱稱。

  - 在所有前端伺服器上，相同的憑證會設定為 OAuthTokenIssuer 憑證。

  - 憑證的長度至少為2048位。

如需 Microsoft Lync Server 2013 之伺服器對伺服器驗證憑證的詳細資訊，請參閱 [將伺服器對伺服器驗證憑證指派給 Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)。

在指派憑證之後，您必須在 Exchange 2013 上設定自動探索服務。 在 Exchange 2013 中，自動探索服務會設定使用者設定檔，並在使用者登入系統時，提供 Exchange 服務的存取權。 使用者會以他們的電子郵件地址和密碼呈現自動探索服務。反過來，服務也會為使用者提供下列資訊：

  - Exchange 2013 的內部及外部連線的連線資訊。

  - 使用者的信箱伺服器位置。

  - URLs Outlook 功能（例如空閒/忙碌資訊、整合通訊與離線通訊錄）。

  - Outlook Anywhere 伺服器設定。

您必須先設定自動探索服務，才能整合 Lync Server 2013 和 Exchange 2013。 您可以從 Exchange 管理命令介面執行下列命令，並檢查 AutoDiscoverServiceInternalUri 屬性的值，以確認是否已設定自動探索服務：

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

如果此值為空白，您必須將 URI 指派給自動探索服務。 通常此 URI 如下所示：

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

您可以執行類似如下的命令來指派自動探索 URI：

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

如需自動探索服務的詳細資訊，請參閱中的「瞭解自動探索服務」 [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542) 。

設定自動探索服務之後，您必須修改 Lync Server OAuth 的設定）;這可確保 Lync Server 知道哪裡可以找到自動探索服務。 若要在 Lync Server 2013 中修改 OAuth 設定設定，請在 Lync Server 管理命令介面內執行下列命令。 當您執行此命令時，請確定您指定的是在 Exchange 伺服器上執行之自動探索服務的 URI，而且您使用 **自動探索。 svc** 指向服務位置，而不是 **autodiscover.xml** (指向服務位置) 所使用的 XML 檔案：

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> 以上命令中的 Identity 參數是選用的;這是因為 Lync Server 只允許您擁有單一、全域的 OAuth 配置設定集合。 除此之外，也表示您可以使用這個稍微簡單的命令來設定自動探索 URL：<BR>Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl " https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc "<BR>如果您不熟悉此技術，OAuth 是許多主要網站所使用的標準授權通訊協定。 使用 OAuth 時，使用者認證和密碼不會從一部電腦傳遞到另一部電腦。 驗證及授權是基於安全性權杖的交換，這些權杖會授與一段特定時間內一組特定資源的存取權。



</div>

除了設定自動探索服務之外，您還必須為指向 Exchange 伺服器的服務建立 DNS 記錄。 例如，如果您的自動探索服務位於 autodiscover.litwareinc.com，您將需要為 autodiscover.litwareinc.com 建立 DNS 記錄，以便解析為 Exchange server (的完整功能變數名稱，例如，atl-exchange-001.litwareinc.com) 。

</div>

<span> </span>

</div>

</div>

</div>

