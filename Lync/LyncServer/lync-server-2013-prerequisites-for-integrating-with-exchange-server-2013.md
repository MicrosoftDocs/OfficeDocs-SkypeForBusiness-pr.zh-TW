---
title: Lync Server 2013：與 Exchange Server 2013 整合的先決條件
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
ms.openlocfilehash: 1a381f765c9c91e9c5e218d66320d542a11bf878
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013 的先決條件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

在您整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 之前，您必須先確定已完成所有必備步驟。 正如您預期的，在 Exchange 2013 和 Lync Server 2013 完整安裝並執行之後，才無法進行整合。 如需安裝 Exchange 的詳細資訊，請參閱 Exchange 2013 規劃與部署[http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)檔（位於）。 如需安裝 Lync Server 2013 的詳細資訊，請參閱中的規劃[http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)與部署檔。

在伺服器啟動並執行之後，您必須將伺服器對伺服器驗證憑證指派給 Lync Server 2013 和 Exchange 2013;這些憑證可讓 Lync Server 與 Exchange 交換資訊，並與其他人通訊。 當您安裝 Exchange 2013 時，會為您建立一個名稱為 Microsoft Exchange Server Auth 憑證的自我簽署憑證。 這個可在本機電腦憑證存放區中找到的憑證應該用於 Exchange 2013 上的伺服器對伺服器驗證。 如需在 Exchange 2013 中指派憑證的詳細資料，請參閱「設定郵件流程與[http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)用戶端存取」。

對於 Lync Server 2013，您可以使用現有的 Lync 伺服器憑證作為伺服器對伺服器驗證憑證;例如，您的預設憑證也可以用來做為 OAuthTokenIssuer 憑證。 Lync Server 2013 可讓您使用任何 Web 服務器憑證作為伺服器對伺服器驗證的憑證，前提是：

  - 憑證在 [Subject] 欄位中包含您 SIP 網域的名稱。

  - 在所有前端伺服器上，相同的憑證都設定為 OAuthTokenIssuer 憑證。

  - 憑證的長度至少為2048位。

如需 Microsoft Lync Server 2013 的伺服器到伺服器驗證憑證的詳細資料，請參閱[將伺服器對伺服器驗證憑證指派給 Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)。

在已指派憑證之後，您必須在 Exchange 2013 上設定自動探索服務。 在 Exchange 2013 中，自動探索服務會設定使用者設定檔，並在使用者登入系統時提供 Exchange 服務的存取權。 使用者以其電子郵件地址和密碼出示自動探索服務;接著，服務會為使用者提供下列資訊：

  - Exchange 2013 內部與外部連線的連線資訊。

  - 使用者信箱伺服器的位置。

  - Outlook 功能的 Url，例如 [空閒/忙碌] 資訊、[整合訊息] 和 [離線通訊錄]。

  - Outlook Anywhere 伺服器設定。

您必須先設定自動探索服務，才能整合 Lync Server 2013 與 Exchange 2013。 您可以從 Exchange 管理命令介面執行下列命令，並檢查 AutoDiscoverServiceInternalUri 屬性的值，以驗證自動探索服務是否已設定：

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

如果此值為空白，您必須為自動探索服務指派 URI。 通常，此 URI 看起來會像這樣：

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

您可以執行如下的命令來指派自動探索 URI：

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

如需自動探索服務的詳細資訊，請參閱「瞭解自動探索[http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)服務」。

在已設定自動探索服務之後，您必須修改 Lync Server OAuth 設定設定;這可確保 Lync Server 知道發現自動探索服務的位置。 若要在 Lync Server 2013 中修改 OAuth 設定設定，請在 Lync Server 管理命令介面中執行下列命令。 執行此命令時，請確定您已將 URI 指定到您的 Exchange 伺服器上執行的自動探索服務，然後使用 [**自動**探索] 來指向服務位置，而不是 [自動探索] **。 .xml** （指向服務所使用的 xml 檔案）：

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> 上述命令中的身分識別參數是選擇性的，這是因為 Lync Server 只允許您使用單一、全域的 OAuth 設定集合。 在其他專案中，這表示您可以使用這個稍微簡單的命令來設定自動探索 URL：<BR>Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"<BR>如果您不熟悉該技術，OAuth 是由許多主要網站使用的標準授權通訊協定。 在 OAuth 中，使用者認證和密碼不會從一部電腦傳送至另一部電腦。 相反地，驗證與授權是以安全權杖的交換為基礎;這些標記會針對特定的一組資源，授予存取權。



</div>

除了設定自動探索服務之外，您也必須為指向您的 Exchange 伺服器的服務建立 DNS 記錄。 例如，如果您的自動探索服務位於 autodiscover.litwareinc.com，您將需要建立 autodiscover.litwareinc.com 的 DNS 記錄，以解析為 Exchange 伺服器的完整功能變數名稱（例如，atl-exchange-001.litwareinc.com）。

</div>

<span> </span>

</div>

</div>

</div>

