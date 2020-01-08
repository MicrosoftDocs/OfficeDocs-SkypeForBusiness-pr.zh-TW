---
title: 在 Lync Server 2013 和 Exchange Server 2013 中設定合作夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定合作夥伴應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-12_

伺服器對伺服器驗證通常會涉及三個實體：需要彼此通訊的兩個伺服器，以及協力廠商安全權杖伺服器。 如果有兩個伺服器（例如，伺服器 A 和伺服器 B）需要進行通訊，那麼這兩個伺服器通常都是透過聯繫權杖伺服器並取得相互信任的安全權杖來開始。 伺服器 A 接著將該安全權杖呈現給伺服器 B （反之亦然），以保證其真實性及其可信度。

不過，這是一般規則。 Lync Server 2013、Microsoft Exchange Server 2013 及 Microsoft SharePoint Server 2013 在彼此通訊時不需要使用協力廠商的權杖伺服器;這是因為這些伺服器產品可以建立一個可以彼此接受的安全權杖，而不需要個別的權杖伺服器。 （這項功能僅適用于 Lync Server 2013、Exchange 2013 和 SharePoint Server 2013。 如果您需要設定與其他伺服器（包括其他 Microsoft 伺服器產品）的伺服器對伺服器驗證，您需要使用協力廠商的權杖伺服器來執行此操作。

若要在 Lync Server 與 Exchange 之間設定伺服器對伺服器的驗證，您必須執行兩個動作：1）您必須將適當的憑證指派給每個伺服器;而且，2）您必須將每個伺服器設定為其他伺服器的合作夥伴應用程式：這表示您必須將 Lync Server 2013 設定為 Exchange 2013 的合作夥伴應用程式，而且您必須將 Exchange 2013 設定為 Lync Server 2013 的合作夥伴應用程式。

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>將 Lync Server 2013 設定為適用于 Exchange 2013 的合作夥伴應用程式

若要將 Lync Server 2013 設定為使用 Exchange 2013 的合作夥伴應用程式，最簡單的方法是執行 Configure-EnterprisePartnerApplication. ps1 腳本（即隨附于 Exchange 2013 的 Windows PowerShell 腳本）。 若要執行此腳本，您必須提供 Lync Server 驗證元資料檔案的 URL;這通常是 Lync Server 2013 池的完整功能變數名稱，後面接著尾碼/metadata/json/1。 例如：

    https://atl-cs-001.litwareinc.com/metadata/json/1

若要將 Lync Server 設定為合作夥伴應用程式，請開啟 Exchange 管理命令介面，並執行類似這個的命令（假設 Exchange 已安裝在磁碟機 C：，且它使用預設的資料夾路徑）：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

在設定合作夥伴應用程式之後，建議您在 Exchange 信箱和用戶端存取伺服器上停止並重新啟動 Internet 資訊服務（IIS）。 您可以使用類似這個的命令重新開機 IIS，這會重新開機電腦 atl-exchange-001 的服務：

    iisreset atl-exchange-001

這個命令可以從 Exchange 管理命令介面或從任何其他命令視窗在 [管理員許可權] 下執行。

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>將 Exchange 2013 設定為 Lync Server 2013 的合作夥伴應用程式

將 Lync Server 2013 設定為 Exchange 2013 的合作夥伴應用程式之後，您必須將 Exchange 設定為 Lync Server 的合作夥伴應用程式。 您可以使用 Lync Server 管理命令介面，並指定 Exchange 的驗證元資料檔案來完成此動作。這通常會是 Exchange 自動探索服務的 URI，後面接著尾碼/metadata/json/1。 例如：

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

在 Lync Server 中，合作夥伴應用程式是使用[CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) Cmdlet 進行設定。 除了指定中繼資料 URI 之外，您也應該將應用程式信任等級設為 Full;這將允許 Exchange 代表其本身以及領域中的任何授權使用者。 例如：

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

或者，您可以複製並修改在 Lync Server 2013 伺服器對伺服器驗證檔中找到的腳本程式碼，以建立合作夥伴應用程式。 如需詳細資訊，請參閱[管理 Lync server 2013 中的伺服器到伺服器驗證（OAuth）與合作夥伴應用程式一](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)文。

如果您已成功為 Lync Server 和 Exchange 設定合作夥伴應用程式，表示您也已成功地在兩個產品之間設定伺服器對伺服器的驗證。 Lync Server 2013 包含 Windows PowerShell Cmdlet、[測試 CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15))，可讓您確認已正確設定伺服器對伺服器驗證，且 Lync Server Storage Service 可以連線到 Exchange 2013。 這個 Cmdlet 是透過連線至 Exchange 2013 使用者的信箱、將專案寫入該使用者的 [交談記錄] 資料夾中，然後再選擇刪除該專案來執行此動作。

若要測試 Lync Server 2013 與 Exchange 2013 的整合，請在 Lync Server 管理命令介面中執行如下所示的命令：

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

在上述命令中，SipUri 代表在 Exchange 2013 上有帳戶的使用者 SIP 位址;您的命令會失敗，這不是有效的使用者帳戶。

如果測試成功且已建立連線，您就可以繼續設定 [存檔整合] 和 [整合連絡人存放區] 等選用功能。

</div>

</div>

<span> </span>

</div>

</div>

</div>

