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
ms.openlocfilehash: faa75694ecaac662a643d331a4efdf91b41223e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="47344-102">整合 Microsoft Lync Server 2013 與 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="47344-102">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47344-103">_**主題上次修改日期：** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="47344-103">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="47344-104">除了與 Microsoft Outlook 2013 整合之外，Microsoft Lync Server 2013 還可以與 Microsoft Outlook Web App 2013 完全整合;在其他專案中，這會新增立即訊息和目前狀態至 Outlook Web App，並可讓您的整合連絡人清單在 Outlook Web App 與 Microsoft Lync 2013 之間共用。</span><span class="sxs-lookup"><span data-stu-id="47344-104">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="47344-105">若要整合 Lync Server 2013 和 Outlook Web App，您必須先確認已在 Microsoft Exchange Server 2013 後端伺服器中安裝整合通訊管理 API 4.0 執行時間。</span><span class="sxs-lookup"><span data-stu-id="47344-105">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="47344-106">您可以透過尋找下列登錄值是否存在來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="47344-106">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="47344-107">HKEY\_本機\_電腦\\系統\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="47344-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="47344-108">ImplementationDLLPath 應該指向 [Ucweb] 檔案的 [資料夾位置]。</span><span class="sxs-lookup"><span data-stu-id="47344-108">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="47344-109">如果沒有，或登錄值不存在，您應該從 Microsoft 下載中心下載並安裝 UCMA 執行時間<http://www.microsoft.com/en-us/download/details.aspx?id=34992>設定程式。</span><span class="sxs-lookup"><span data-stu-id="47344-109">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <http://www.microsoft.com/en-us/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="47344-110">有關如何安裝 UCMA 執行時間的資訊，可以在相同的網頁上找到。</span><span class="sxs-lookup"><span data-stu-id="47344-110">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="47344-111">**向後相容性**</span><span class="sxs-lookup"><span data-stu-id="47344-111">**Backward Compatibility**</span></span>

<span data-ttu-id="47344-112">Lync Server 2013 可以與統一訊息和 Outlook Web App 的 Microsoft Exchange Server 2010 版本整合。</span><span class="sxs-lookup"><span data-stu-id="47344-112">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="47344-113">如需詳細資訊，請參閱部署內部部署 Exchange UM 以提供 Lync Server 2010 語音信箱的文章[http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="47344-113">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="47344-114">如果您整合 Exchange 2010，您將不會有 Lync Server 的特定功能，例如 [整合連絡人] 存放區和 [Lync 到 Exchange] 歸檔。</span><span class="sxs-lookup"><span data-stu-id="47344-114">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="47344-115">Microsoft Lync 2013 也可以與 Exchange 2010 和 Outlook 2010 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="47344-115">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="47344-116">不過，新功能（例如 [整合連絡人] 存放區和高解析度相片）不會提供給 Lync 2013 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="47344-116">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="47344-117">這些新功能需要 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="47344-117">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="47344-118">**為 Outlook Web App 建立受信任的應用程式池**</span><span class="sxs-lookup"><span data-stu-id="47344-118">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="47344-119">如果您已在同一部電腦上安裝 Microsoft Exchange 整合訊息呼叫路由器服務和 Microsoft Exchange 整合訊息服務，就不需要為 Outlook Web App 建立信任的應用程式池。</span><span class="sxs-lookup"><span data-stu-id="47344-119">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="47344-120">（這假設有問題的伺服器是託管 SipName UM 撥號方案。）如果您使用單一電腦來託管這兩種服務，您可以跳至此檔中標題為 [**在 Outlook Web App 上啟用立即訊息**] 的章節。</span><span class="sxs-lookup"><span data-stu-id="47344-120">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="47344-121">Lync Server 2013 可以自動探索任何託管 SipName UM 撥號方案的 Exchange 伺服器;這些伺服器會自動新增至 [Lync Server 已知伺服器] 清單。</span><span class="sxs-lookup"><span data-stu-id="47344-121">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="47344-122">您不需要建立信任的應用程式池，並將這些伺服器新增到 [已知伺服器] 清單中。</span><span class="sxs-lookup"><span data-stu-id="47344-122">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="47344-123">事實上，這麼做會導致 Outlook Web App 整合停止運作。</span><span class="sxs-lookup"><span data-stu-id="47344-123">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47344-124">這是因為 Lync Server 拓朴現在會有兩個專案可供同一台電腦使用： autodiscovered 專案和手動新增的專案。</span><span class="sxs-lookup"><span data-stu-id="47344-124">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="47344-125">若要修正此問題，並重新取得 Outlook Web App，請使用 Windows PowerShell 來移除伺服器的信任池和受信任的應用程式專案。</span><span class="sxs-lookup"><span data-stu-id="47344-125">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="47344-126">如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">CsTrustedApplicationPool</A>與<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">remove CsTrustedApplication</A> Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="47344-126">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="47344-127">如果這兩項服務是在不同的電腦上執行，當您確認已安裝整合通訊 Managed API 4.0 執行時間之後，就必須建立一個 Lync Server 受信任的應用程式池以及與下列專案相關聯的信任應用程式Outlook Web App;這會將伺服器新增到 [已知伺服器] 清單中。</span><span class="sxs-lookup"><span data-stu-id="47344-127">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="47344-128">若要這樣做，請先在 Lync Server 管理命令介面中執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="47344-128">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="47344-129">在上述命令中，atl-owa-001.litwareinc.com 是 Outlook Web App 區的完整功能變數名稱;此名稱必須與提供 Outlook Web App 存取權之憑證的 [Subject 名稱] 和 [消費者替換名稱（SAN）] 欄位中出現的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="47344-129">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="47344-130">同樣地，atl-cs-001.litwareinc.com 是 Lync Server 2013 擁有者的完整功能變數名稱，該功能變數名稱會主持新的受信任的應用程式池。</span><span class="sxs-lookup"><span data-stu-id="47344-130">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="47344-131">請注意，指定的網站（雷蒙德）代表 Lync Server 網站的 SiteID。</span><span class="sxs-lookup"><span data-stu-id="47344-131">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="47344-132">SiteID 不一定與網站的 DisplayName 相同;您可以從 Lync Server 管理命令介面執行下列命令，以取得 Lync Server 網站的 SiteIDs：</span><span class="sxs-lookup"><span data-stu-id="47344-132">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="47344-133">建立受信任的應用程式池之後，請使用類似下列的命令來設定應用程式身分識別及 Outlook Web App 的埠：</span><span class="sxs-lookup"><span data-stu-id="47344-133">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="47344-134">在上述命令中，ApplicationID 只是用來區分受信任之應用程式的友好識別碼。</span><span class="sxs-lookup"><span data-stu-id="47344-134">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications.</span></span> <span data-ttu-id="47344-135">ApplicationID 可以是不包含空格或其他禁止字元的任何文字字串。</span><span class="sxs-lookup"><span data-stu-id="47344-135">The ApplicationID can be any text string that does not include blank spaces or other prohibited characters.</span></span> <span data-ttu-id="47344-136">（若要確保您建立的是有效識別碼，建議您在指定 ApplicationId 時，只使用字母和數位）。指派給 Port 參數的值也會留給管理員的決定：這可以是任何可用的網路埠。</span><span class="sxs-lookup"><span data-stu-id="47344-136">(To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="47344-137">在建立受信任的應用程式後，您必須執行下列命令，才能啟用 Lync Server 拓撲的變更：</span><span class="sxs-lookup"><span data-stu-id="47344-137">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="47344-138">請注意，您也必須將 Exchange 用戶端存取和信箱伺服器新增到所有 SIP Uri 撥號方案。</span><span class="sxs-lookup"><span data-stu-id="47344-138">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="47344-139">接著，這會將伺服器設定為受信任的 SIP 對等，以及 Lync Server 的 ExUmRouting 拓撲。</span><span class="sxs-lookup"><span data-stu-id="47344-139">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="47344-140">**在 Outlook Web App 上啟用立即訊息**</span><span class="sxs-lookup"><span data-stu-id="47344-140">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="47344-141">在 Lync 伺服器設定正確之後，您就可以開始設定 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="47344-141">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="47344-142">該程式中的第一個步驟是在您的前端伺服器上的所有 Outlook Web App 虛擬目錄上啟用立即訊息。</span><span class="sxs-lookup"><span data-stu-id="47344-142">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="47344-143">（不需要在後端伺服器上啟用虛擬目錄的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="47344-143">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="47344-144">事實上，建議您不要在後端伺服器上啟用 [立即訊息]。）若要在用戶端存取伺服器上啟用立即訊息，請從 Exchange 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="47344-144">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="47344-145">根據預設，當您安裝 Outlook Web App 時，會啟用立即訊息;也就是說，InstantMessagingEnabled 屬性會設定為 True。</span><span class="sxs-lookup"><span data-stu-id="47344-145">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True.</span></span> <span data-ttu-id="47344-146">不過，您仍然必須執行前面的命令，才能將立即訊息類型設定為 OCS。</span><span class="sxs-lookup"><span data-stu-id="47344-146">However, you must still run the preceding command in order to set the instant messaging type to OCS.</span></span> <span data-ttu-id="47344-147">根據預設，InstantMessagingType 會設定為 [無]。</span><span class="sxs-lookup"><span data-stu-id="47344-147">By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="47344-148">接下來，您必須將下列兩行新增至 Outlook Web App Web.config 檔案（此檔案通常位於資料夾 C：\\Program 檔案中，\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa）。</span><span class="sxs-lookup"><span data-stu-id="47344-148">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="47344-149">您應該在 web.config 檔案中的\<AppSettings\>節點底下加上這兩行，而且應該只在已安裝 Outlook Web App 的後端伺服器上執行此程式：</span><span class="sxs-lookup"><span data-stu-id="47344-149">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="47344-150">在前面的範例中，IMCertificateThumbprint 的值必須是安裝在後端伺服器上的 Exchange 2013 憑證的指紋。</span><span class="sxs-lookup"><span data-stu-id="47344-150">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="47344-151">您可以從 Exchange 管理命令介面執行下列命令，以取得該資訊：</span><span class="sxs-lookup"><span data-stu-id="47344-151">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="47344-152">請注意，指派給 IMServerName 的值也是您在其中建立 Outlook Web App 受信任的應用程式池之 Lync 伺服器池的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="47344-152">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="47344-153">您在 Outlook Web App 中使用的憑證必須是受 Lync 伺服器信任的憑證。</span><span class="sxs-lookup"><span data-stu-id="47344-153">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="47344-154">確保 Lync Server 與 Exchange 信任的憑證的其中一個方法是使用您的內部認證機構在信箱伺服器上建立憑證，確認已將伺服器 FQDN 用於使用中的消費者名稱，且此 FQDN 出現在 t[憑證替換名稱] 欄位。</span><span class="sxs-lookup"><span data-stu-id="47344-154">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="47344-155">建立證書之後，就可以將它匯入到後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="47344-155">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="47344-156">最終結果是使用相同的憑證進行兩個用途：1） Exchange 整合訊息和 Lync Server 之間的通訊;而且，2） Outlook Web App 和 Lync Server 之間的整合。</span><span class="sxs-lookup"><span data-stu-id="47344-156">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="47344-157">更新 web.config 檔案之後，您必須在 Exchange 後端伺服器上執行下列命令，才能回收 Outlook Web App 區：</span><span class="sxs-lookup"><span data-stu-id="47344-157">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="47344-158">如果回收操作成功，您會在 Exchange 管理命令介面中看到下列訊息：</span><span class="sxs-lookup"><span data-stu-id="47344-158">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="47344-159">**設定 Outlook Web App 信箱原則**</span><span class="sxs-lookup"><span data-stu-id="47344-159">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="47344-160">此時，您可以使用下列命令，在適當的 Outlook Web App 信箱原則（或原則）上設定立即訊息。</span><span class="sxs-lookup"><span data-stu-id="47344-160">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies).</span></span> <span data-ttu-id="47344-161">例如，此命令會在您的其中一個信箱伺服器上執行，並在預設原則上啟用 [立即訊息]：</span><span class="sxs-lookup"><span data-stu-id="47344-161">For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="47344-162">這個命令會針對您所有的 Outlook Web App 信箱原則啟用立即訊息：</span><span class="sxs-lookup"><span data-stu-id="47344-162">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="47344-163">啟用信箱原則之後，該原則所管理的所有使用者都會在 Lync Server 和 Outlook Web App 之間取得完整整合，前提是：</span><span class="sxs-lookup"><span data-stu-id="47344-163">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="47344-164">使用者在 Exchange 2013 上有信箱。</span><span class="sxs-lookup"><span data-stu-id="47344-164">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="47344-165">已啟用 Lync Server 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="47344-165">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="47344-166">使用者擁有有效的 SIP proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="47344-166">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="47344-167">**在 Outlook Web App 中停用立即訊息**</span><span class="sxs-lookup"><span data-stu-id="47344-167">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="47344-168">如先前所述，Outlook Web App 中預設會啟用 [立即訊息]。</span><span class="sxs-lookup"><span data-stu-id="47344-168">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="47344-169">也就是說，如果您沒有將 Outlook Web App 與 Lync Server 整合，使用者在每次登入 Outlook Web App 時，都會看到空白的目前狀態圖示和錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="47344-169">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="47344-170">若要避免此問題，請使用下列 Exchange Management Shell 命令來停用 Outlook web App 中的立即訊息：</span><span class="sxs-lookup"><span data-stu-id="47344-170">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="47344-171">**驗證與 Outlook Web App 的整合**</span><span class="sxs-lookup"><span data-stu-id="47344-171">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="47344-172">若要確認立即訊息和目前狀態與 Outlook Web App 已集成，請登入 Outlook Web App 2013。</span><span class="sxs-lookup"><span data-stu-id="47344-172">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="47344-173">在畫面右上角，您會看到您的 Exchange 顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="47344-173">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="47344-174">如果您的名稱旁邊有 [目前狀態] 圖示（例如，綠色圖示指出您目前的狀態為可用），表示您已成功整合 Lync Server 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="47344-174">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="47344-175">初次登入至 Outlook Web App 之後，請檢查是否有事件 ID 112 （以及來源 MSExchange OWA）的事件已寫入信箱伺服器上的事件記錄。</span><span class="sxs-lookup"><span data-stu-id="47344-175">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="47344-176">此事件表示立即訊息端點管理員已成功初始化。</span><span class="sxs-lookup"><span data-stu-id="47344-176">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="47344-177">如果立即訊息看起來沒有作用，請在信箱伺服器上尋找資料夾\\C： Program 檔案中的記錄檔案\\Microsoft\\Exchange server\\V15\\記錄\\OWA\\InstantMessaging。</span><span class="sxs-lookup"><span data-stu-id="47344-177">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="47344-178">如果 [記錄] 或 [InstantMessaging] 資料夾不存在，表示該整合失敗。</span><span class="sxs-lookup"><span data-stu-id="47344-178">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="47344-179">在這種情況下，您可以在 Lync Server （所有層級和所有旗標）上使用 SIPStack 追蹤，以嘗試並判斷整合失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="47344-179">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

