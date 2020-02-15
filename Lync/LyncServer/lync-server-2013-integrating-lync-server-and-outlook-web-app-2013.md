---
title: Lync Server 2013： 整合 Lync Server 與 Outlook Web App 2013https
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
ms.openlocfilehash: 44de5139d3ad8f38c5177a18260045fda7abdeea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>整合 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-03_

除了整合與 Microsoft Outlook 2013 時，Microsoft Lync Server 2013 可以完全整合與 Microsoft Outlook Web App 2013https;除此之外，這將立即訊息和目前狀態新增至 Outlook Web App，並可讓您整合的連絡人清單，Outlook Web App 和 Microsoft Lync 2013 之間共用。 若要整合 Lync Server 2013 和 Outlook Web App，您必須先確認 Unified Communications Managed API 4.0 Runtime，已安裝在您的 Microsoft Exchange Server 2013 後端伺服器。 藉由尋找下列登錄值存在，您可以執行這項操作：

HKEY\_本機\_機器\\系統\\CurrentControlSet\\服務\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath

ImplementationDLLPath 應指向 Microsoft.Rtc.Internal.Ucweb.dll 之檔案的資料夾位置。 如果沒有，或如果登錄值不存在，接著您應該下載並安裝 UCMA Runtime 安裝程式從 Microsoft 下載中心<http://www.microsoft.com/download/details.aspx?id=34992>。 可以在該相同的 [web] 頁面上找到有關如何安裝的 UCMA 執行階段的資訊。

**回溯相容性**

Lync Server 2013 可以與 Microsoft Exchange Server 2010 版本的 unified messaging 和 Outlook Web App 整合。 如需詳細資訊，請參閱文章部署內部部署 Exchange UM 以提供 Lync Server 2010 的語音信箱在[http://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。 如果您整合 Exchange 2010 與您將沒有 Lync Server 的特定功能，例如整合連絡人存放區和 Lync-Exchange 封存。

Microsoft Lync 2013 也可用於與 Exchange 2010 和 Outlook 2010 一起使用。 再次重申，不過，例如高解析度相片與整合連絡人存放區的新功能將無法使用 Lync 2013 的使用者。 這些新功能需要 Lync Server 2013 和 Exchange 2013。

**建立信任的應用程式集區的 Outlook Web App**

如果您已經在同一部電腦上安裝 Microsoft Exchange 整合通訊呼叫路由器服務和 Microsoft Exchange 整合通訊服務有則不需要在 Outlook Web app 建立信任的應用程式集區。 （這假設有問題的伺服器裝載 SipName UM 撥號對應表）。如果您使用一部電腦裝載這兩種服務您可以略過這份文件標題為 [**啟用 Outlook Web App 的立即訊息**] 區段。

Lync Server 2013 可以自動探索任何 Exchange 伺服器，裝載 SipName UM 撥號對應表規劃;這些伺服器會自動新增至 [Lync Server 已知的伺服器清單。 便不需要建立信任的應用程式集區，並將這些伺服器新增到已知的 [伺服器] 清單。 事實上，這樣做會停止運作的 Outlook Web App 整合。

<div>


> [!NOTE]  
> 這是因為用 Lync Server 拓撲現在會出現在同一部電腦的兩個項目: autodiscovered 項目，並以手動方式新增項目。 若要修正這個問題，並取得一次使用的 Outlook Web App，使用 Windows PowerShell 移除受信任的集區和伺服器的信任的應用程式項目。 請參閱說明主題中的<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">移除 CsTrustedApplicationPool</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-cstrustedapplication</A>指令程式，如需詳細資訊。



</div>

如果這兩項服務會執行在不同的電腦上，則您已經驗證已安裝 Unified Communications Managed API 4.0 Runtime，您必須建立之後 Lync 伺服器信任的應用程式集區和受信任的應用程式相關聯Outlook Web App;會將伺服器加入已知的 [伺服器] 清單。 若要這麼做，請先執行 Lync Server 管理命令介面從如下的命令：

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

在上述命令中，atl-cs-owa-001.litwareinc.com 是 Outlook Web 應用程式集區中; 的完整的網域名稱這必須是憑證的相同的名稱，會出現在 Outlook Web app 提供存取的主體名稱和主體替代名稱 (SAN) 欄位。 同樣地，atl-cs-001.litwareinc.com 是將裝載新的受信任的應用程式集區的 Lync Server 2013 集區的完整的網域名稱。 請注意，指定的站台 Redmond，代表 Lync Server 網站的 SiteID。 SiteID 不一定是相同站台的 DisplayName;您可以從 Lync Server 管理命令介面執行下列命令，為您的 Lync Server 網站擷取 SiteIDs:

    Get-CsSite | Select-Object DisplayName, SiteID

之後建立的信任的應用程式集區，請使用類似下列的命令來設定 Outlook Web App 相關應用程式的應用程式身分識別和連接埠：

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

在上述命令中，ApplicationID 只是用於分辨信任的應用程式的易記識別碼。ApplicationID 可以是任何文字字串，不包括空格或其他禁止的字元 (為了確保您建立的是有效識別碼，建議您在指定 ApplicationId 時只使用字母和數字)。指派給 Port 參數的值也是留待系統管理員決定：可以是任何可用的網路連接埠。

建立信任的應用程式之後，您必須執行下列命令，以啟用 Lync Server 拓撲所做的變更：

    Enable-CsTopology

請注意，您也必須將 Exchange 用戶端存取和信箱伺服器加入到所有 SIP Uri 撥號對應表計劃。 接著，這會設定伺服器與 ExUmRouting 拓撲的信任 SIP 對等 Lync server。

**啟用立即訊息在 Outlook Web App**

與 Lync Server 已正確設定，您可以再開始設定 Outlook Web App。 該程序的第一個步驟是啟用所有 Outlook Web App 虛擬目錄上您的前端伺服器上的立即訊息。 （便不需要啟用立即訊息後端伺服器上的虛擬目錄。 事實上，它是建議使用，您不啟用立即訊息後端伺服器上）。立即訊息可以啟用用戶端存取伺服器上執行 Exchange 管理命令介面中的下列命令：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> 根據預設，立即訊息時，會啟用您安裝 Outlook Web App;亦即 InstantMessagingEnabled 屬性設為 True。 不過，您仍然必須執行才能的立即訊息類型設為 OCS 上述命令。 根據預設，InstantMessagingType 設為 None。



</div>

您必須將下列兩行新增至 Outlook Web 應用程式 Web.config 檔案的下一步] (此檔案通常位於資料夾 c:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa)。 這兩行應新增\<AppSettings\>節點中的 Web.config 檔案，以及此程序應該只在已安裝 Outlook Web App 的後端伺服器上執行：

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

在上述範例中，IMCertificateThumbprint 的值必須是安裝在您的後端伺服器的 Exchange 2013 憑證的指紋。 您可以從 Exchange 管理命令介面執行下列命令，以擷取該資訊：

    Get-ExchangeCertificate

請注意，指派給 IMServerName 的值是 Outlook Web app 建立信任的應用程式集區所在的 Lync 伺服器集區的完整的網域名稱。

您使用 Outlook Web App 的憑證必須由 Lync 伺服器信任的憑證。 若要確定會在 Lync 伺服器和 Exchange 受信任憑證的其中一個方法是使用您的內部憑證授權單位建立憑證的信箱伺服器上，確定伺服器 FQDN 使用主體名稱，這個 FQDN 出現在 t他憑證替代名稱] 欄位。 在建立憑證之後它可以再匯入到您的後端伺服器。 最後結果就是相同的憑證用於兩種用途： 1) Exchange 整合通訊與 Lync Server 之間的通訊和，2） 的 Outlook Web App 和 Lync Server 之間的整合。

之後您已更新您然後應該執行的 Exchange 後端伺服器上的下列命令，以便回收 Outlook Web 應用程式集區的 Web.config 檔案：

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

如果回收作業成功，您會看到下列訊息在 Exchange 管理命令介面：

    "MSExchangeOWAAppPool" successfully recycled

**設定 Outlook Web App 信箱原則**

此時您可以使用下列命令來設定適當的 Outlook Web App 信箱原則 （或原則） 上的立即訊息。 例如，在其中一部信箱伺服器，執行此命令可讓 im 預設原則：

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

與此命令可啟用立即訊息的所有 Outlook Web App 信箱原則：

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

原則已啟用信箱後，再由該原則所管理的所有使用者都會都具有 Lync Server 與 Outlook Web App，提供的完整整合：

  - 使用者擁有的信箱位於 Exchange 2013。

  - 使用者已啟用 Lync Server 2013。

  - 使用者有有效的 SIP Proxy 位址。

**停用 Outlook Web App 中的立即訊息**

如先前所述，立即訊息預設會啟用 Outlook Web App 中。 這表示，如果您不執行 Lync Server 整合 Outlook Web App，使用者會看到空白狀態圖示和錯誤訊息每次登入 Outlook Web App。 若要避免此問題，請使用下列 Exchange 管理命令介面命令來停用 Outlook web App 中的立即訊息：

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**驗證與 Outlook Web App 的整合**

若要確認立即訊息與顯示狀態必須已經整合與 Outlook Web App，登入 Outlook Web App 2013https。 在螢幕的右上角，您會看到您的 Exchange 顯示名稱。 如果沒有您的名稱 （例如，綠色圖示表示您目前的狀態適用於） 旁顯示狀態圖示，表示您必須成功整合 Lync Server 與 Outlook Web App。

在初始登入至 Outlook Web App 之後, 查看有 mailbox server 上已是否事件與事件識別碼 112 （來源為 MSExchange OWA） 寫入至事件記錄檔。 此事件會指出即時通訊端點管理員已順利初始化。 若立即訊息未出現可運作然後，在信箱伺服器上，尋找 [c:] 資料夾中的記錄檔\\Program Files\\Microsoft\\Exchange 伺服器\\V15\\記錄\\OWA\\InstantMessaging。 如果 [記錄] 或 [InstantMessaging 資料夾不存在，指出失敗整合。 在此情況下，您可以使用裡包含 SIPStack 追蹤 （所有層級和所有旗標），再試，並判斷整合的失敗原因的 Lync 伺服器上。

</div>

<span> </span>

</div>

</div>

</div>

