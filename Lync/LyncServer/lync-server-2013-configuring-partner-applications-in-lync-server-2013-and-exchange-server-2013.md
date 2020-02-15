---
title: Lync Server 2013 和 Exchange Server 2013 中設定夥伴應用程式
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
ms.openlocfilehash: 5d6eb00b5efcd811d0fbf1397bce5f8b965c9110
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定夥伴應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-12_

伺服器對伺服器驗證通常涉及三個實體： 兩部伺服器需要彼此通訊，以及協力廠商安全性權杖伺服器。 如果兩部伺服器 （例如，伺服器 A 和伺服器 B） 需要進行通訊，然後這兩個這些伺服器通常啟動連絡 token 的伺服器，並取得彼此信任安全性 token。 伺服器的然後顯示該安全性權杖伺服器 B （反之亦然） 的方式，確保其授權和其可信度。

不過，這是一般規則。 Lync Server 2013、 Microsoft Exchange Server 2013 和 Microsoft SharePoint Server 2013 不需要使用協力廠商權杖伺服器，與另一個; 通訊時這是因為這些伺服器產品可以建立安全性權杖可以接受的另一個，而不需要個別的權杖伺服器。 （此功能只有在 Lync Server 2013、 Exchange 2013 和 SharePoint Server 2013。 如果您需要設定與其他伺服器的伺服器對伺服器驗證，包括其他 Microsoft server 產品，則您將需要這麼做使用協力廠商權杖伺服器。）

若要設定 Lync Server 和 Exchange 之間的伺服器對伺服器驗證，您必須執行下列兩件事： 1) 您必須將適當的憑證指派給每個伺服器;和，2） 您必須設定為夥伴應用程式的另一部伺服器的每一部伺服器： 這表示您必須設定 Lync Server 2013 到 Exchange 2013 中，為合作夥伴應用程式，您必須設定為 Lync Server 2013 的協力廠商應用程式的 Exchange 2013。

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>設定 Lync Server 2013 到 Exchange 2013 為合作夥伴應用程式

設定 Lync Server 2013 與 Exchange 2013 為合作夥伴應用程式的最簡單方法是執行 Configure-enterprisepartnerapplication.ps1 指令碼，隨附於 Exchange 2013 的 Windows PowerShell 指令碼。 若要執行此指令碼，您必須提供 URL Lync Server 驗證中繼資料文件;這通常會接著尾碼 /metadata/json/1 Lync Server 2013 集區完整的網域名稱。 例如：

    https://atl-cs-001.litwareinc.com/metadata/json/1

若要設定 Lync Server 作為夥伴應用程式，請開啟 Exchange 管理命令介面並執行如下的命令 （假設已在 c： 磁碟機上安裝 Exchange，且其使用預設資料夾路徑）：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

設定夥伴應用程式之後建議您停止並重新啟動您的 Exchange 信箱和用戶端存取伺服器上的網際網路資訊服務 (IIS)。 您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：

    iisreset atl-exchange-001

在 Exchange 管理命令介面中，或是從任何其他命令視窗中執行系統管理員權限，可以從執行此命令。

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>設定 Lync Server 2013 的協力廠商應用程式的 Exchange 2013

您已設定 Lync Server 2013 到 Exchange 2013 為合作夥伴應用程式之後，您必須接著設定 Lync Server 的協力廠商應用程式的 Exchange。 這可以經由使用 Lync Server 管理命令介面和 exchange; 指定驗證中繼資料文件這通常會接著尾碼 /metadata/json/1 Exchange 自動探索服務的 URI。 例如：

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

在 Lync Server 中，使用[New-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet 設定夥伴應用程式。 除了指定 URI 的中繼資料也應設定應用程式信任層級為 Full;這樣可讓 Exchange 來表示本身和領域中的任何授權的使用者。 例如：

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

或者，您可以藉由複製和修改 Lync Server 2013 伺服器對伺服器驗證文件中找到的指令碼程式碼建立夥伴應用程式。 請參閱[Managing 伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)的詳細資訊。

如果您已成功設定協力應用程式的 Lync Server 和 Exchange，表示您已也成功設定這兩項產品之間的伺服器對伺服器驗證。 Lync Server 2013 包含 Windows PowerShell cmdlet， [Test-csexstorageconnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))，可讓您確認已正確設定伺服器對伺服器驗證和 Lync Server 儲存體服務可以連線至 Exchange 2013。 指令程式的運作方式連線至 Exchange 2013 使用者信箱，寫入交談記錄資料夾中的項目，該使用者的然後選擇性地刪除該項目。

若要測試的 Lync Server 2013 和 Exchange 2013 的整合，請執行命令類似從 Lync Server 管理命令介面中：

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

在上述命令中，SipUri 代表具有 Exchange 2013 /; 帳戶的使用者的 SIP 位址您的命令會失敗這不是有效的使用者帳戶。

如果測試成功且建立連線，您可以再繼續設定選用功能，例如封存整合和整合連絡人存放區。

</div>

</div>

<span> </span>

</div>

</div>

</div>

