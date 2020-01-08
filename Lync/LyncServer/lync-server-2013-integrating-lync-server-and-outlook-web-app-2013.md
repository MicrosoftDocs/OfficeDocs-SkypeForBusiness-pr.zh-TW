---
title: Lync Server 2013：整合 Lync Server 和 Outlook Web App 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a25e1d0a6410171201af578d6b28f496468e06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>整合 Microsoft Lync Server 2013 與 Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-03_

除了與 Microsoft Outlook 2013 整合之外，Microsoft Lync Server 2013 還可以與 Microsoft Outlook Web App 2013 完全整合;在其他專案中，這會新增立即訊息和目前狀態至 Outlook Web App，並可讓您的整合連絡人清單在 Outlook Web App 與 Microsoft Lync 2013 之間共用。 若要整合 Lync Server 2013 和 Outlook Web App，您必須先確認已在 Microsoft Exchange Server 2013 後端伺服器中安裝整合通訊管理 API 4.0 執行時間。 您可以透過尋找下列登錄值是否存在來執行此動作：

HKEY\_本機\_電腦\\系統\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath 應該指向 [Ucweb] 檔案的 [資料夾位置]。 如果沒有，或登錄值不存在，您應該從 Microsoft 下載中心下載並安裝 UCMA 執行時間<http://www.microsoft.com/en-us/download/details.aspx?id=34992>設定程式。 有關如何安裝 UCMA 執行時間的資訊，可以在相同的網頁上找到。

**向後相容性**

Lync Server 2013 可以與統一訊息和 Outlook Web App 的 Microsoft Exchange Server 2010 版本整合。 如需詳細資訊，請參閱部署內部部署 Exchange UM 以提供 Lync Server 2010 語音信箱的文章[http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。 如果您整合 Exchange 2010，您將不會有 Lync Server 的特定功能，例如 [整合連絡人] 存放區和 [Lync 到 Exchange] 歸檔。

Microsoft Lync 2013 也可以與 Exchange 2010 和 Outlook 2010 搭配使用。 不過，新功能（例如 [整合連絡人] 存放區和高解析度相片）不會提供給 Lync 2013 使用者使用。 這些新功能需要 Lync Server 2013 和 Exchange 2013。

**為 Outlook Web App 建立受信任的應用程式池**

如果您已在同一部電腦上安裝 Microsoft Exchange 整合訊息呼叫路由器服務和 Microsoft Exchange 整合訊息服務，就不需要為 Outlook Web App 建立信任的應用程式池。 （這假設有問題的伺服器是託管 SipName UM 撥號方案。）如果您使用單一電腦來託管這兩種服務，您可以跳至此檔中標題為 [**在 Outlook Web App 上啟用立即訊息**] 的章節。

Lync Server 2013 可以自動探索任何託管 SipName UM 撥號方案的 Exchange 伺服器;這些伺服器會自動新增至 [Lync Server 已知伺服器] 清單。 您不需要建立信任的應用程式池，並將這些伺服器新增到 [已知伺服器] 清單中。 事實上，這麼做會導致 Outlook Web App 整合停止運作。

<div>


> [!NOTE]  
> 這是因為 Lync Server 拓朴現在會有兩個專案可供同一台電腦使用： autodiscovered 專案和手動新增的專案。 若要修正此問題，並重新取得 Outlook Web App，請使用 Windows PowerShell 來移除伺服器的信任池和受信任的應用程式專案。 如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">CsTrustedApplicationPool</A>與<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">remove CsTrustedApplication</A> Cmdlet 的說明主題。



</div>

如果這兩項服務是在不同的電腦上執行，當您確認已安裝整合通訊 Managed API 4.0 執行時間之後，就必須建立一個 Lync Server 受信任的應用程式池以及與下列專案相關聯的信任應用程式Outlook Web App;這會將伺服器新增到 [已知伺服器] 清單中。 若要這樣做，請先在 Lync Server 管理命令介面中執行如下所示的命令：

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

在上述命令中，atl-owa-001.litwareinc.com 是 Outlook Web App 區的完整功能變數名稱;此名稱必須與提供 Outlook Web App 存取權之憑證的 [Subject 名稱] 和 [消費者替換名稱（SAN）] 欄位中出現的名稱相同。 同樣地，atl-cs-001.litwareinc.com 是 Lync Server 2013 擁有者的完整功能變數名稱，該功能變數名稱會主持新的受信任的應用程式池。 請注意，指定的網站（雷蒙德）代表 Lync Server 網站的 SiteID。 SiteID 不一定與網站的 DisplayName 相同;您可以從 Lync Server 管理命令介面執行下列命令，以取得 Lync Server 網站的 SiteIDs：

    Get-CsSite | Select-Object DisplayName, SiteID

建立受信任的應用程式池之後，請使用類似下列的命令來設定應用程式身分識別及 Outlook Web App 的埠：

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

在上述命令中，ApplicationID 只是用來區分受信任之應用程式的友好識別碼。 ApplicationID 可以是不包含空格或其他禁止字元的任何文字字串。 （若要確保您建立的是有效識別碼，建議您在指定 ApplicationId 時，只使用字母和數位）。指派給 Port 參數的值也會留給管理員的決定：這可以是任何可用的網路埠。

在建立受信任的應用程式後，您必須執行下列命令，才能啟用 Lync Server 拓撲的變更：

    Enable-CsTopology

請注意，您也必須將 Exchange 用戶端存取和信箱伺服器新增到所有 SIP Uri 撥號方案。 接著，這會將伺服器設定為受信任的 SIP 對等，以及 Lync Server 的 ExUmRouting 拓撲。

**在 Outlook Web App 上啟用立即訊息**

在 Lync 伺服器設定正確之後，您就可以開始設定 Outlook Web App。 該程式中的第一個步驟是在您的前端伺服器上的所有 Outlook Web App 虛擬目錄上啟用立即訊息。 （不需要在後端伺服器上啟用虛擬目錄的立即訊息。 事實上，建議您不要在後端伺服器上啟用 [立即訊息]。）若要在用戶端存取伺服器上啟用立即訊息，請從 Exchange 管理命令介面中執行下列命令：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> 根據預設，當您安裝 Outlook Web App 時，會啟用立即訊息;也就是說，InstantMessagingEnabled 屬性會設定為 True。 不過，您仍然必須執行前面的命令，才能將立即訊息類型設定為 OCS。 根據預設，InstantMessagingType 會設定為 [無]。



</div>

接下來，您必須將下列兩行新增至 Outlook Web App Web.config 檔案（此檔案通常位於資料夾 C：\\Program 檔案中，\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa）。 您應該在 web.config 檔案中的\<AppSettings\>節點底下加上這兩行，而且應該只在已安裝 Outlook Web App 的後端伺服器上執行此程式：

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

在前面的範例中，IMCertificateThumbprint 的值必須是安裝在後端伺服器上的 Exchange 2013 憑證的指紋。 您可以從 Exchange 管理命令介面執行下列命令，以取得該資訊：

    Get-ExchangeCertificate

請注意，指派給 IMServerName 的值也是您在其中建立 Outlook Web App 受信任的應用程式池之 Lync 伺服器池的完整功能變數名稱。

您在 Outlook Web App 中使用的憑證必須是受 Lync 伺服器信任的憑證。 確保 Lync Server 與 Exchange 信任的憑證的其中一個方法是使用您的內部認證機構在信箱伺服器上建立憑證，確認已將伺服器 FQDN 用於使用中的消費者名稱，且此 FQDN 出現在 t[憑證替換名稱] 欄位。 建立證書之後，就可以將它匯入到後端伺服器。 最終結果是使用相同的憑證進行兩個用途：1） Exchange 整合訊息和 Lync Server 之間的通訊;而且，2） Outlook Web App 和 Lync Server 之間的整合。

更新 web.config 檔案之後，您必須在 Exchange 後端伺服器上執行下列命令，才能回收 Outlook Web App 區：

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

如果回收操作成功，您會在 Exchange 管理命令介面中看到下列訊息：

    "MSExchangeOWAAppPool" successfully recycled

**設定 Outlook Web App 信箱原則**

此時，您可以使用下列命令，在適當的 Outlook Web App 信箱原則（或原則）上設定立即訊息。 例如，此命令會在您的其中一個信箱伺服器上執行，並在預設原則上啟用 [立即訊息]：

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

這個命令會針對您所有的 Outlook Web App 信箱原則啟用立即訊息：

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

啟用信箱原則之後，該原則所管理的所有使用者都會在 Lync Server 和 Outlook Web App 之間取得完整整合，前提是：

  - 使用者在 Exchange 2013 上有信箱。

  - 已啟用 Lync Server 2013 的使用者。

  - 使用者擁有有效的 SIP proxy 位址。

**在 Outlook Web App 中停用立即訊息**

如先前所述，Outlook Web App 中預設會啟用 [立即訊息]。 也就是說，如果您沒有將 Outlook Web App 與 Lync Server 整合，使用者在每次登入 Outlook Web App 時，都會看到空白的目前狀態圖示和錯誤訊息。 若要避免此問題，請使用下列 Exchange Management Shell 命令來停用 Outlook web App 中的立即訊息：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**驗證與 Outlook Web App 的整合**

若要確認立即訊息和目前狀態與 Outlook Web App 已集成，請登入 Outlook Web App 2013。 在畫面右上角，您會看到您的 Exchange 顯示名稱。 如果您的名稱旁邊有 [目前狀態] 圖示（例如，綠色圖示指出您目前的狀態為可用），表示您已成功整合 Lync Server 和 Outlook Web App。

初次登入至 Outlook Web App 之後，請檢查是否有事件 ID 112 （以及來源 MSExchange OWA）的事件已寫入信箱伺服器上的事件記錄。 此事件表示立即訊息端點管理員已成功初始化。 如果立即訊息看起來沒有作用，請在信箱伺服器上尋找資料夾\\C： Program 檔案中的記錄檔案\\Microsoft\\Exchange server\\V15\\記錄\\OWA\\InstantMessaging。 如果 [記錄] 或 [InstantMessaging] 資料夾不存在，表示該整合失敗。 在這種情況下，您可以在 Lync Server （所有層級和所有旗標）上使用 SIPStack 追蹤，以嘗試並判斷整合失敗的原因。

</div>

<span> </span>

</div>

</div>

</div>

