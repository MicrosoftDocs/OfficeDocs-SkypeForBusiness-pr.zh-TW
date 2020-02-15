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

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="ad8b1-102">整合 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="ad8b1-102">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad8b1-103">_**上次修改主題：** 2013年-02-03_</span><span class="sxs-lookup"><span data-stu-id="ad8b1-103">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="ad8b1-104">除了整合與 Microsoft Outlook 2013 時，Microsoft Lync Server 2013 可以完全整合與 Microsoft Outlook Web App 2013https;除此之外，這將立即訊息和目前狀態新增至 Outlook Web App，並可讓您整合的連絡人清單，Outlook Web App 和 Microsoft Lync 2013 之間共用。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-104">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="ad8b1-105">若要整合 Lync Server 2013 和 Outlook Web App，您必須先確認 Unified Communications Managed API 4.0 Runtime，已安裝在您的 Microsoft Exchange Server 2013 後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-105">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="ad8b1-106">藉由尋找下列登錄值存在，您可以執行這項操作：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-106">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="ad8b1-107">HKEY\_本機\_機器\\系統\\CurrentControlSet\\服務\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="ad8b1-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="ad8b1-108">ImplementationDLLPath 應指向 Microsoft.Rtc.Internal.Ucweb.dll 之檔案的資料夾位置。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-108">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="ad8b1-109">如果沒有，或如果登錄值不存在，接著您應該下載並安裝 UCMA Runtime 安裝程式從 Microsoft 下載中心<http://www.microsoft.com/download/details.aspx?id=34992>。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-109">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <http://www.microsoft.com/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="ad8b1-110">可以在該相同的 [web] 頁面上找到有關如何安裝的 UCMA 執行階段的資訊。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-110">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="ad8b1-111">**回溯相容性**</span><span class="sxs-lookup"><span data-stu-id="ad8b1-111">**Backward Compatibility**</span></span>

<span data-ttu-id="ad8b1-112">Lync Server 2013 可以與 Microsoft Exchange Server 2010 版本的 unified messaging 和 Outlook Web App 整合。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-112">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="ad8b1-113">如需詳細資訊，請參閱文章部署內部部署 Exchange UM 以提供 Lync Server 2010 的語音信箱在[http://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-113">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [http://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="ad8b1-114">如果您整合 Exchange 2010 與您將沒有 Lync Server 的特定功能，例如整合連絡人存放區和 Lync-Exchange 封存。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-114">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="ad8b1-115">Microsoft Lync 2013 也可用於與 Exchange 2010 和 Outlook 2010 一起使用。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-115">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="ad8b1-116">再次重申，不過，例如高解析度相片與整合連絡人存放區的新功能將無法使用 Lync 2013 的使用者。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-116">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="ad8b1-117">這些新功能需要 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-117">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="ad8b1-118">**建立信任的應用程式集區的 Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="ad8b1-118">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="ad8b1-119">如果您已經在同一部電腦上安裝 Microsoft Exchange 整合通訊呼叫路由器服務和 Microsoft Exchange 整合通訊服務有則不需要在 Outlook Web app 建立信任的應用程式集區。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-119">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="ad8b1-120">（這假設有問題的伺服器裝載 SipName UM 撥號對應表）。如果您使用一部電腦裝載這兩種服務您可以略過這份文件標題為 [**啟用 Outlook Web App 的立即訊息**] 區段。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-120">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="ad8b1-121">Lync Server 2013 可以自動探索任何 Exchange 伺服器，裝載 SipName UM 撥號對應表規劃;這些伺服器會自動新增至 [Lync Server 已知的伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-121">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="ad8b1-122">便不需要建立信任的應用程式集區，並將這些伺服器新增到已知的 [伺服器] 清單。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-122">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="ad8b1-123">事實上，這樣做會停止運作的 Outlook Web App 整合。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-123">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad8b1-124">這是因為用 Lync Server 拓撲現在會出現在同一部電腦的兩個項目: autodiscovered 項目，並以手動方式新增項目。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-124">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="ad8b1-125">若要修正這個問題，並取得一次使用的 Outlook Web App，使用 Windows PowerShell 移除受信任的集區和伺服器的信任的應用程式項目。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-125">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="ad8b1-126">請參閱說明主題中的<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">移除 CsTrustedApplicationPool</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-cstrustedapplication</A>指令程式，如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-126">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="ad8b1-127">如果這兩項服務會執行在不同的電腦上，則您已經驗證已安裝 Unified Communications Managed API 4.0 Runtime，您必須建立之後 Lync 伺服器信任的應用程式集區和受信任的應用程式相關聯Outlook Web App;會將伺服器加入已知的 [伺服器] 清單。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-127">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="ad8b1-128">若要這麼做，請先執行 Lync Server 管理命令介面從如下的命令：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-128">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="ad8b1-129">在上述命令中，atl-cs-owa-001.litwareinc.com 是 Outlook Web 應用程式集區中; 的完整的網域名稱這必須是憑證的相同的名稱，會出現在 Outlook Web app 提供存取的主體名稱和主體替代名稱 (SAN) 欄位。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-129">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="ad8b1-130">同樣地，atl-cs-001.litwareinc.com 是將裝載新的受信任的應用程式集區的 Lync Server 2013 集區的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-130">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="ad8b1-131">請注意，指定的站台 Redmond，代表 Lync Server 網站的 SiteID。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-131">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="ad8b1-132">SiteID 不一定是相同站台的 DisplayName;您可以從 Lync Server 管理命令介面執行下列命令，為您的 Lync Server 網站擷取 SiteIDs:</span><span class="sxs-lookup"><span data-stu-id="ad8b1-132">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="ad8b1-133">之後建立的信任的應用程式集區，請使用類似下列的命令來設定 Outlook Web App 相關應用程式的應用程式身分識別和連接埠：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-133">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="ad8b1-p110">在上述命令中，ApplicationID 只是用於分辨信任的應用程式的易記識別碼。ApplicationID 可以是任何文字字串，不包括空格或其他禁止的字元 (為了確保您建立的是有效識別碼，建議您在指定 ApplicationId 時只使用字母和數字)。指派給 Port 參數的值也是留待系統管理員決定：可以是任何可用的網路連接埠。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-p110">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications. The ApplicationID can be any text string that does not include blank spaces or other prohibited characters. (To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="ad8b1-137">建立信任的應用程式之後，您必須執行下列命令，以啟用 Lync Server 拓撲所做的變更：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-137">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="ad8b1-138">請注意，您也必須將 Exchange 用戶端存取和信箱伺服器加入到所有 SIP Uri 撥號對應表計劃。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-138">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="ad8b1-139">接著，這會設定伺服器與 ExUmRouting 拓撲的信任 SIP 對等 Lync server。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-139">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="ad8b1-140">**啟用立即訊息在 Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="ad8b1-140">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="ad8b1-141">與 Lync Server 已正確設定，您可以再開始設定 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-141">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="ad8b1-142">該程序的第一個步驟是啟用所有 Outlook Web App 虛擬目錄上您的前端伺服器上的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-142">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="ad8b1-143">（便不需要啟用立即訊息後端伺服器上的虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-143">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="ad8b1-144">事實上，它是建議使用，您不啟用立即訊息後端伺服器上）。立即訊息可以啟用用戶端存取伺服器上執行 Exchange 管理命令介面中的下列命令：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-144">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="ad8b1-145">根據預設，立即訊息時，會啟用您安裝 Outlook Web App;亦即 InstantMessagingEnabled 屬性設為 True。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-145">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True.</span></span> <span data-ttu-id="ad8b1-146">不過，您仍然必須執行才能的立即訊息類型設為 OCS 上述命令。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-146">However, you must still run the preceding command in order to set the instant messaging type to OCS.</span></span> <span data-ttu-id="ad8b1-147">根據預設，InstantMessagingType 設為 None。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-147">By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="ad8b1-148">您必須將下列兩行新增至 Outlook Web 應用程式 Web.config 檔案的下一步] (此檔案通常位於資料夾 c:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa)。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-148">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="ad8b1-149">這兩行應新增\<AppSettings\>節點中的 Web.config 檔案，以及此程序應該只在已安裝 Outlook Web App 的後端伺服器上執行：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-149">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="ad8b1-150">在上述範例中，IMCertificateThumbprint 的值必須是安裝在您的後端伺服器的 Exchange 2013 憑證的指紋。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-150">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="ad8b1-151">您可以從 Exchange 管理命令介面執行下列命令，以擷取該資訊：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-151">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="ad8b1-152">請注意，指派給 IMServerName 的值是 Outlook Web app 建立信任的應用程式集區所在的 Lync 伺服器集區的完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-152">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="ad8b1-153">您使用 Outlook Web App 的憑證必須由 Lync 伺服器信任的憑證。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-153">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="ad8b1-154">若要確定會在 Lync 伺服器和 Exchange 受信任憑證的其中一個方法是使用您的內部憑證授權單位建立憑證的信箱伺服器上，確定伺服器 FQDN 使用主體名稱，這個 FQDN 出現在 t他憑證替代名稱] 欄位。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-154">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="ad8b1-155">在建立憑證之後它可以再匯入到您的後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-155">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="ad8b1-156">最後結果就是相同的憑證用於兩種用途： 1) Exchange 整合通訊與 Lync Server 之間的通訊和，2） 的 Outlook Web App 和 Lync Server 之間的整合。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-156">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="ad8b1-157">之後您已更新您然後應該執行的 Exchange 後端伺服器上的下列命令，以便回收 Outlook Web 應用程式集區的 Web.config 檔案：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-157">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="ad8b1-158">如果回收作業成功，您會看到下列訊息在 Exchange 管理命令介面：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-158">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="ad8b1-159">**設定 Outlook Web App 信箱原則**</span><span class="sxs-lookup"><span data-stu-id="ad8b1-159">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="ad8b1-160">此時您可以使用下列命令來設定適當的 Outlook Web App 信箱原則 （或原則） 上的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-160">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies).</span></span> <span data-ttu-id="ad8b1-161">例如，在其中一部信箱伺服器，執行此命令可讓 im 預設原則：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-161">For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="ad8b1-162">與此命令可啟用立即訊息的所有 Outlook Web App 信箱原則：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-162">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="ad8b1-163">原則已啟用信箱後，再由該原則所管理的所有使用者都會都具有 Lync Server 與 Outlook Web App，提供的完整整合：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-163">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="ad8b1-164">使用者擁有的信箱位於 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-164">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="ad8b1-165">使用者已啟用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-165">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="ad8b1-166">使用者有有效的 SIP Proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-166">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="ad8b1-167">**停用 Outlook Web App 中的立即訊息**</span><span class="sxs-lookup"><span data-stu-id="ad8b1-167">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="ad8b1-168">如先前所述，立即訊息預設會啟用 Outlook Web App 中。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-168">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="ad8b1-169">這表示，如果您不執行 Lync Server 整合 Outlook Web App，使用者會看到空白狀態圖示和錯誤訊息每次登入 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-169">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="ad8b1-170">若要避免此問題，請使用下列 Exchange 管理命令介面命令來停用 Outlook web App 中的立即訊息：</span><span class="sxs-lookup"><span data-stu-id="ad8b1-170">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="ad8b1-171">**驗證與 Outlook Web App 的整合**</span><span class="sxs-lookup"><span data-stu-id="ad8b1-171">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="ad8b1-172">若要確認立即訊息與顯示狀態必須已經整合與 Outlook Web App，登入 Outlook Web App 2013https。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-172">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="ad8b1-173">在螢幕的右上角，您會看到您的 Exchange 顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-173">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="ad8b1-174">如果沒有您的名稱 （例如，綠色圖示表示您目前的狀態適用於） 旁顯示狀態圖示，表示您必須成功整合 Lync Server 與 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-174">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="ad8b1-175">在初始登入至 Outlook Web App 之後, 查看有 mailbox server 上已是否事件與事件識別碼 112 （來源為 MSExchange OWA） 寫入至事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-175">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="ad8b1-176">此事件會指出即時通訊端點管理員已順利初始化。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-176">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="ad8b1-177">若立即訊息未出現可運作然後，在信箱伺服器上，尋找 [c:] 資料夾中的記錄檔\\Program Files\\Microsoft\\Exchange 伺服器\\V15\\記錄\\OWA\\InstantMessaging。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-177">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="ad8b1-178">如果 [記錄] 或 [InstantMessaging 資料夾不存在，指出失敗整合。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-178">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="ad8b1-179">在此情況下，您可以使用裡包含 SIPStack 追蹤 （所有層級和所有旗標），再試，並判斷整合的失敗原因的 Lync 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ad8b1-179">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

