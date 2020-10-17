---
title: Lync Server 2013：整合 Lync Server 和 Outlook Web App 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f822afb4ba0f3dabfd133caf92a434eadac82fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534753"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>整合 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-03_

除了與 Microsoft Outlook 2013 的整合之外，Microsoft Lync Server 2013 也可以與 Microsoft Outlook Web App 2013 完全整合;此外，這會在 Outlook Web App 中新增立即訊息和目前狀態，並可讓您的整合連絡人清單在 Outlook Web App 和 Microsoft Lync 2013 間共用。 為了整合 Lync Server 2013 和 Outlook Web App，您必須先確認您的 Microsoft Exchange Server 2013 後端伺服器中已安裝整合通訊 Managed API 4.0 Runtime。 您可以尋找下列登錄值是否存在，以執行這項操作：

HKEY \_ LOCAL \_ MACHINE \\ SYSTEM \\ CurrentControlSet \\ Services \\ MSExchange OWA \\ InstantMessaging \\ ImplementationDLLPath

ImplementationDLLPath 應該指向檔 Microsoft.Rtc.Internal.Ucweb.dll 的資料夾位置。 否則，請從 Microsoft 下載中心下載並安裝 UCMA Runtime 安裝程式（如果不存在的話），然後從 <https://www.microsoft.com/download/details.aspx?id=34992> 。 有關如何安裝 UCMA Runtime 的資訊，可在相同網頁上找到。

**回溯相容性**

Lync Server 2013 可以與整合通訊和 Outlook Web App 的 Microsoft Exchange Server 2010 版本整合。 如需詳細資訊，請參閱部署 On-Premises Exchange UM 以提供 Lync Server 2010 語音信箱的文章 [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) 。 如果您與 Exchange 2010 整合，您將不會有 Lync Server 的特定功能，例如整合的連絡人存放區和 Lync 對 Exchange 封存。

Microsoft Lync 2013 也可以與 Exchange 2010 和 Outlook 2010 一起使用。 不過，您可以再次使用新功能，例如整合連絡人存放區和高解析度相片，Lync 2013 使用者將無法使用這些功能。 這些新功能需要 Lync Server 2013 和 Exchange 2013。

**為 Outlook Web App 建立信任的應用程式集區**

如果您已在同一部電腦上安裝 Microsoft Exchange 整合通訊呼叫路由器服務和 Microsoft Exchange 整合通訊服務，則不需要為 Outlook Web App 建立信任的應用程式集區。  (這會假定有問題的伺服器主控 SipName UM 撥號對應表。 ) 如果您使用一部電腦來主控這兩項服務，您可以跳到此檔中的區段，其標題為 **啟用 Outlook Web App 上的立即訊息**。

Lync Server 2013 可以自動探索主控 SipName UM 撥號對應表的任何 Exchange 伺服器;這些伺服器會自動新增至 [Lync Server 已知伺服器] 清單。 不需要建立信任的應用程式集區，並將這些伺服器新增至已知的伺服器清單。 實際上，這樣做會導致 Outlook Web App 整合停止運作。

<div>


> [!NOTE]  
> 這是因為 Lync Server 拓撲現在會有兩個專案可用於同一部電腦： autodiscovered 專案和手動新增的專案。 若要修正此問題，並使 Outlook Web App 重新運作，請使用 Windows PowerShell 移除伺服器的受信任集區和受信任應用程式專案。 如需詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">new-cstrustedapplicationpool</A> 和 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">remove-CsTrustedApplication</A> Cmdlet 的 [說明] 主題。



</div>

如果這兩項服務是在不同的電腦上執行，當您確認已安裝整合通訊 Managed API 4.0 Runtime 之後，您必須建立 Lync Server 信任的應用程式集區，以及與 Outlook Web App 相關聯的信任應用程式;這會將伺服器新增至已知的伺服器清單。 若要這麼做，請先在 Lync Server 管理命令介面中執行類似下列的命令：

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

在上述命令中，atl-owa-001.litwareinc.com 是 Outlook Web App 集區的完整功能變數名稱;此名稱必須與提供 Outlook Web App 存取權之憑證的 [主體名稱] 和 [主體別名] 欄位 (SAN) ] 欄位相同。 同樣地，atl-cs-001.litwareinc.com 是 Lync Server 2013 集區的完整功能變數名稱，該功能變數名稱會主控新的信任的應用程式集區。 請注意，指定的 site （Redmond）代表 Lync Server 網站的 SiteID。 SiteID 不一定與網站 DisplayName 相同;您可以從 Lync Server 管理命令介面執行下列命令，以取得 Lync Server 網站的 SiteIDs：

    Get-CsSite | Select-Object DisplayName, SiteID

在建立信任的應用程式集區之後，請使用類似下列的命令，設定 Outlook Web App 的應用程式身分識別及埠：

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

在上述命令中，ApplicationID 只是用於分辨信任的應用程式的易記識別碼。ApplicationID 可以是任何文字字串，不包括空格或其他禁止的字元 (為了確保您建立的是有效識別碼，建議您在指定 ApplicationId 時只使用字母和數字)。指派給 Port 參數的值也是留待系統管理員決定：可以是任何可用的網路連接埠。

在建立信任的應用程式之後，您必須執行下列命令，以啟用 Lync Server 拓撲的變更：

    Enable-CsTopology

請注意，您也必須將 Exchange 用戶端存取和信箱伺服器新增至所有 SIP Uri 撥號對應表。 接著，這會將伺服器設定為受信任的 SIP 對等與 Lync Server 的 ExUmRouting 拓撲。

**在 Outlook Web App 上啟用立即訊息**

在設定正確的 Lync 伺服器後，您就可以開始設定 Outlook Web App。 該程式中的第一個步驟是在前端伺服器上的所有 Outlook Web App 虛擬目錄上啟用立即訊息。  (您不需要在後端伺服器上為虛擬目錄啟用立即訊息。 實際上，建議您不要在後端伺服器上啟用立即訊息。在用戶端存取伺服器上，您可以從 Exchange 管理命令介面中執行下列命令，以在用戶端存取伺服器上啟用 ) 立即訊息：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> 依預設，當您安裝 Outlook Web App 時，會啟用立即訊息;也就是說，InstantMessagingEnabled 屬性會設定為 True。 不過，您仍必須執行先前的命令，才能將立即訊息類型設定為 OCS。 根據預設，InstantMessagingType 會設為 None。



</div>

接下來，您必須將下列兩行新增至 Outlook Web App Web.config 檔案 (此檔案通常位於資料夾 C： \\ Program Files \\ Microsoft \\ Exchange Server \\ v15 版 \\ ClientAccess \\ Owa) 。 這兩行應該新增在 Web.config 檔的 \<AppSettings\> 節點底下，此程式應該只在已安裝 Outlook Web App 的後端伺服器上執行：

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

在上述範例中，IMCertificateThumbprint 的值必須是安裝在後端伺服器上的 Exchange 2013 憑證的指紋。 您可以從 Exchange 管理命令介面執行下列命令，以取回該資訊：

    Get-ExchangeCertificate

請注意，指派給 IMServerName 的值也是 Lync 伺服器集區的完整功能變數名稱，您已在此伺服器集區中建立 Outlook Web App 的信任應用程式集區。

您用於 Outlook Web App 的憑證必須是 Lync Server 所信任的憑證。 若要確保 Lync Server 與 Exchange 皆信任的憑證是使用您的內部憑證授權單位單位，在信箱伺服器上建立憑證，請確定伺服器 FQDN 用於主體名稱，而此 FQDN 會出現在 [憑證替代名稱] 欄位中。 建立憑證之後，即可將它匯入至後端伺服器。 Net 結果是兩個目的使用相同的憑證： 1) Exchange 整合通訊與 Lync Server 之間的通訊;而且，2) Outlook Web App 和 Lync Server 之間的整合。

更新 Web.config 檔案之後，您應該在 Exchange 後端伺服器上執行下列命令，以便回收 Outlook Web App 集區：

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

如果回收操作成功，您會在 Exchange 管理命令介面中看到下列訊息：

    "MSExchangeOWAAppPool" successfully recycled

**設定 Outlook Web App 信箱原則**

此時，您可以使用下列命令，在適當的 Outlook Web App 信箱原則 (或原則) 上設定立即訊息。 例如，此命令會在其中一部信箱伺服器上執行，啟用預設原則上的立即訊息：

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

而且此命令會啟用所有 Outlook Web App 信箱原則的立即訊息：

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

啟用信箱原則之後，由該原則管理的所有使用者，都會在 Lync Server 和 Outlook Web App 之間進行完整整合，但前提是：

  - 使用者在 Exchange 2013 上有信箱。

  - 使用者已啟用 Lync Server 2013。

  - 使用者有有效的 SIP Proxy 位址。

**停用 Outlook Web App 中的立即訊息**

如先前所述，Outlook Web App 中預設會啟用立即訊息。 這表示，如果您不會將 Outlook Web App 與 Lync Server 整合，使用者會在每次登入 Outlook Web App 時看到空白的顯示狀態圖示及錯誤訊息。 若要避免此問題，請使用下列 Exchange 管理命令介面命令停用 Outlook web App 中的立即訊息：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**驗證與 Outlook Web App 的整合**

若要確認立即訊息和目前狀態已與 Outlook Web App 整合，請登入 Outlook Web App 2013。 在螢幕的右上角，您會看到您的 Exchange 顯示名稱。 如果您的名稱旁邊有顯示狀態圖示 (例如，表示您目前狀態的綠色圖示可供使用) 表示您已成功整合 Lync Server 和 Outlook Web App。

在初次登入 Outlook Web App 後，請查看是否有事件識別碼為112的事件 (，並已將來源 MSExchange OWA) 寫入至信箱伺服器上的事件記錄。 此事件表示立即訊息端點管理員初始化成功。 如果立即訊息似乎沒有正常運作，請在信箱伺服器上，于資料夾 C： \\ Program files \\ Microsoft \\ Exchange server \\ v15 版 \\ 記錄 \\ OWA \\ InstantMessaging 中尋找記錄檔。 如果記錄或 InstantMessaging 資料夾不存在，表示整合失敗。 在此情況下，您可以在 Lync Server 上使用 SIPStack 追蹤 (所有層級和所有旗) 標，以嘗試及判斷整合失敗的原因。

</div>

<span> </span>

</div>

</div>

</div>

