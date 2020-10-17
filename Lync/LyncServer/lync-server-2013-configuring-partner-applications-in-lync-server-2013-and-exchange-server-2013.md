---
title: 在 Lync Server 2013 和 Exchange Server 2013 中設定合作夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8743b012042738ea25653cf49a804e08d59a423
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532510"
---
# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定合作夥伴應用程式

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-12_

伺服器對伺服器驗證一般會包含三個實體：兩個伺服器必須彼此通訊，另一個是協力廠商的安全性權杖伺服器。 例如，如果兩部伺服器 (，則伺服器 A 和伺服器 B) 需要通訊，則這兩部伺服器通常是透過聯繫權杖伺服器並取得相互信任的安全性權杖來開始。 伺服器 A 接著會向伺服器 B 呈現該安全性權杖 (，反之亦然) 做為保證其真偽及其可信性的方式。

不過，這是一般規則。 Lync Server 2013、Microsoft Exchange Server 2013 和 Microsoft SharePoint Server 2013 不需要使用協力廠商的 token 伺服器進行通訊，而是使用另一個憑證伺服器進行通訊;這是因為這些伺服器產品可以建立可以彼此接受的安全性權杖，而不需要個別的權杖伺服器。  (只有在 Lync Server 2013、Exchange 2013 及 SharePoint Server 2013 中才能使用此功能。 如果您需要使用其他伺服器（包括其他 Microsoft server 產品）設定伺服器對伺服器的驗證，則需要使用協力廠商的 token 伺服器來執行。 ) 

若要在 Lync Server 與 Exchange 之間設定伺服器對伺服器驗證，您必須執行下列兩項動作： 1) 您必須將適當的憑證指派給每個伺服器;而且，2) 您必須將每一部伺服器設定為另一部伺服器的夥伴應用程式：也就是說，您必須將 Lync Server 2013 設定為 Exchange 2013 的夥伴應用程式，而且您必須將 Exchange 2013 設定為 Lync Server 2013 的夥伴應用程式。

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>設定 Lync Server 2013 成為 Exchange 2013 的夥伴應用程式

將 Lync Server 2013 設定為具有 Exchange 2013 之夥伴應用程式的最簡單方法，就是執行 Configure-EnterprisePartnerApplication.ps1 腳本，該腳本是隨 Exchange 2013 一起提供的 Windows PowerShell 腳本。 若要執行這個腳本，您必須提供 Lync Server 驗證元資料檔案的 URL;這通常是 Lync Server 2013 集區的完整功能變數名稱，後面加上尾碼/metadata/json/1。 例如：

    https://atl-cs-001.litwareinc.com/metadata/json/1

若要設定 Lync Server 成為夥伴應用程式，請開啟 Exchange 管理命令介面，並執行類似此 (的命令，假設 Exchange 已安裝在磁碟機 C：上，且其使用預設資料夾路徑) ：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

設定夥伴應用程式之後，建議您在 Exchange 信箱和用戶端存取伺服器上停止並重新啟動網際網路資訊服務 (IIS) 。 您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：

    iisreset atl-exchange-001

您可以從 Exchange 管理命令介面或任何其他命令視窗中執行此命令，在系統管理員許可權下執行。

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>將 Exchange 2013 設定為 Lync Server 2013 的夥伴應用程式

將 Lync Server 2013 設定為 Exchange 2013 的夥伴應用程式之後，您必須將 Exchange 設定為 Lync Server 的夥伴應用程式。 使用 Lync Server 管理命令介面，並指定 Exchange 的驗證元資料檔案，即可完成此動作。這通常是 Exchange 自動探索服務的 URI 後接尾碼/metadata/json/1。 例如：

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

在 Lync Server 中，會使用 [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) Cmdlet 來設定夥伴應用程式。 除了指定中繼資料 URI 之外，您還應該將應用程式信任層級設定為 [完整]。這可讓 Exchange 同時代表該領域中的自身和任何經授權的使用者。 例如：

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

或者，您可以複製及修改 Lync Server 2013 伺服器對伺服器驗證檔中找到的腳本程式碼，以建立合作夥伴應用程式。 如需詳細資訊，請參閱 [管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式在 Lync server 2013 中](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 的文章。

如果您已成功為 Lync Server 和 Exchange 設定夥伴應用程式，則表示您已成功設定兩種產品之間的伺服器對伺服器驗證。 Lync Server 2013 包括 Windows PowerShell Cmdlet [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))，可讓您驗證服務器對伺服器驗證是否已正確設定，以及 Lync Server Storage Service 是否可以連線至 Exchange 2013。 此 Cmdlet 是透過連線至 Exchange 2013 使用者的信箱，將專案寫入該使用者的 [交談記錄] 資料夾中，然後選擇性地刪除該專案來執行此動作。

若要測試 Lync Server 2013 和 Exchange 2013 的整合，請在 Lync Server 管理命令介面中執行類似下列的命令：

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

在上述命令中，SipUri 代表在 Exchange 2013 上具有帳戶之使用者的 SIP 位址;您的命令將會失敗。這不是有效的使用者帳戶。

如果測試成功且已建立連線，您就可以繼續設定選用的功能，例如封存整合和整合連絡人存放區。

</div>

</div>

<span> </span>

</div>

</div>

</div>

