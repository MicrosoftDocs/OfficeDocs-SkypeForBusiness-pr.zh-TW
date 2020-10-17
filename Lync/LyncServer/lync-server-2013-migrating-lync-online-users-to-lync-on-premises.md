---
title: Lync Server 2013：將 Lync Online 使用者遷移至 Lync 內部部署
description: Lync Server 2013：將 Lync Online 使用者遷移至 Lync 內部部署。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrating Lync Online users to Lync on-premises
ms:assetid: 0e29605b-db2d-4cbf-b6a9-15db6b9fdabc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689115(v=OCS.15)
ms:contentKeyID: 62258120
ms.date: 11/13/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 620bc07def8e3c1f6b761c6398b452b4dbcd3b04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560999"
---
# <a name="migrating-lync-online-users-to-lync-on-premises-in-lync-server-2013"></a><span data-ttu-id="48499-103">將 Lync Online 使用者遷移至 lync Server 2013 中的 Lync 內部部署</span><span class="sxs-lookup"><span data-stu-id="48499-103">Migrating Lync Online users to Lync on-premises in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48499-104">_**主題上次修改日期：** 2015-11-13_</span><span class="sxs-lookup"><span data-stu-id="48499-104">_**Topic Last Modified:** 2015-11-13_</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="48499-105">在您部署 Lync 內部部署之前，只需要將已在 Lync Online 中啟用 Lync 的使用者帳戶遷移時，才需要執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="48499-105">These steps are necessary only for migrating user accounts that were originally enabled for Lync in Lync Online, before you deployed Lync on-premises.</span></span> <span data-ttu-id="48499-106">若要將原來啟用 Lync 內部部署的使用者移動，之後移至 Lync Online，請參閱 <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">在混合 Lync Server 2013 部署中管理使用者</A>。</span><span class="sxs-lookup"><span data-stu-id="48499-106">To move users who were originally enabled for Lync on-premises, then later moved to Lync Online, see <A href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</A>.</span></span><BR><span data-ttu-id="48499-107">此外，所有移動的使用者都必須擁有內部部署 Active Directory 中的帳戶。</span><span class="sxs-lookup"><span data-stu-id="48499-107">Additionally, all users being moved must have accounts in the on-premises Active Directory.</span></span>



</div>

<div>

## <a name="migrating-user-accounts-originally-enabled-in-lync-online-to-lync-on-premises"></a><span data-ttu-id="48499-108">將 Lync Online 中原來啟用的使用者帳戶遷移至 Lync On-Premises</span><span class="sxs-lookup"><span data-stu-id="48499-108">Migrating User Accounts Originally Enabled in Lync Online to Lync On-Premises</span></span>

1.  <span data-ttu-id="48499-109">首先，請確定您的組織已設定成混合式。</span><span class="sxs-lookup"><span data-stu-id="48499-109">First, make sure that your organization is configured for hybrid.</span></span>
    
      - <span data-ttu-id="48499-110">安裝 Azure Active Directory 同步作業工具。</span><span class="sxs-lookup"><span data-stu-id="48499-110">Install the Azure Active Directory Sync Tool.</span></span> <span data-ttu-id="48499-111">如需詳細資訊，請參閱 <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>。</span><span class="sxs-lookup"><span data-stu-id="48499-111">For more information, see <https://social.technet.microsoft.com/wiki/contents/articles/19098.howto-install-the-windows-azure-active-directory-sync-tool.aspx>.</span></span>
    
      - <span data-ttu-id="48499-112">若要讓您的使用者可以使用單一登入來進行 Lync Online，請安裝 Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx> 。</span><span class="sxs-lookup"><span data-stu-id="48499-112">To enable your users to use single sign-on for Lync Online, install Active Directory Federation Services <https://social.technet.microsoft.com/wiki/contents/articles/1011.active-directory-federation-services-ad-fs-overview.aspx>.</span></span>
    
      - <span data-ttu-id="48499-113">在您的內部部署中，在 Lync Server 管理命令介面中輸入下列 Cmdlet，以建立 Lync Online 的裝載提供者：</span><span class="sxs-lookup"><span data-stu-id="48499-113">On your on-premises deployment, in Lync Server Management Shell, type the following cmdlets to create the hosting provider for Lync Online:</span></span>
        
           ```PowerShell
           Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
           ```
        
           ```PowerShell
            New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
           ```

2.  <span data-ttu-id="48499-114">請確認，在您的內部部署 Edge Server 上，您的憑證鏈可以啟用與 Lync Online 的連線，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="48499-114">Confirm that, on your on-premises Edge Servers, you have the certificate chain that enables connection to Lync Online, as shown in the following table.</span></span> <span data-ttu-id="48499-115">您可以在這裡下載此連結： https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span><span class="sxs-lookup"><span data-stu-id="48499-115">You can download this chain here: https://support.office.com/article/office-365-certificate-chains-0c03e6b3-e73f-4316-9e2b-bf4091ae96bb</span></span>


    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="48499-116">認證</span><span class="sxs-lookup"><span data-stu-id="48499-116">Certificate</span></span></th>
    <th><span data-ttu-id="48499-117">憑證儲存區</span><span class="sxs-lookup"><span data-stu-id="48499-117">Certificate Store</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="48499-118">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="48499-118">Baltimore CyberTrust Root</span></span></p></td>
    <td><p><span data-ttu-id="48499-119">受信任的根 CA</span><span class="sxs-lookup"><span data-stu-id="48499-119">Trusted Root CA</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="48499-120">Microsoft Internet 核證機關 (新 CA 憑證) </span><span class="sxs-lookup"><span data-stu-id="48499-120">Microsoft Internet Authority (New CA certificate)</span></span></p></td>
    <td><p><span data-ttu-id="48499-121">中間 CA</span><span class="sxs-lookup"><span data-stu-id="48499-121">Intermediate CA</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="48499-122">MSIT)  (新發出 CA2 的機器驗證 CA2</span><span class="sxs-lookup"><span data-stu-id="48499-122">MSIT Machine Auth CA2 (New Issuing CA2)</span></span></p></td>
    <td><p><span data-ttu-id="48499-123">中間 CA</span><span class="sxs-lookup"><span data-stu-id="48499-123">Intermediate CA</span></span></p></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="48499-124">在您的內部部署 Active Directory 中，針對 Lync 內部部署啟用受影響的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="48499-124">In your on-premises Active Directory, enable the affected user accounts for Lync on-premises.</span></span> <span data-ttu-id="48499-125">您可以輸入下列 Cmdlet，為個別使用者執行這項操作：</span><span class="sxs-lookup"><span data-stu-id="48499-125">You can do this for an individual user by typing the following cmdlet:</span></span>
    
        Enable-CsUser
        -Identity "username" 
        -SipAddress "sip: username@contoso.com"
        -HostingProviderProxyFqdn "sipfed.online.lync.com"
    
    <span data-ttu-id="48499-126">或者，您也可以建立從檔案讀取使用者名稱的腳本，並將其提供給 Enable-CsUser Cmdlet 的輸入：</span><span class="sxs-lookup"><span data-stu-id="48499-126">Or you can create a script that reads user names from a file and provides them as input to the Enable-CsUser cmdlet:</span></span>
    
        Enable-CsUser
        -Identity $Identity 
        -SipAddress $SipAddress 
        -HostingProviderProxyFqdn "sipfed.online.lync.com"

4.  <span data-ttu-id="48499-127">執行 DirSync，以同步處理 Lync Online 使用者與更新的 Lync 內部部署使用者。</span><span class="sxs-lookup"><span data-stu-id="48499-127">Run DirSync to sync the Lync Online users with the updated Lync on-premises users.</span></span>

5.  <span data-ttu-id="48499-128">更新一些 DNS 記錄，以將所有 SIP 流量定向至 Lync 內部部署：</span><span class="sxs-lookup"><span data-stu-id="48499-128">Update some DNS records to direct all SIP traffic to Lync on-premises:</span></span>
    
      - <span data-ttu-id="48499-129">更新 **Lyncdiscover.contoso.com** A 記錄，使其指向內部部署反向 proxy 伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="48499-129">Update the **lyncdiscover.contoso.com** A record to point to the FQDN of the on-premises reverse proxy server.</span></span>
    
      - <span data-ttu-id="48499-130">更新 \*\*\* \_ sip *。 \_tls.contoso.com*\* SRV 記錄，以解析至 Lync 內部部署的 Access Edge service 的公用 IP 或 VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="48499-130">Update the \***\_sip\*.\_tls.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="48499-131">更新 \*\*\* \_ sipfederationtls *。 \_tcp.contoso.com*\* SRV 記錄，以解析至 Lync 內部部署的 Access Edge service 的公用 IP 或 VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="48499-131">Update the \***\_sipfederationtls\*.\_tcp.contoso.com** SRV record to resolve to the public IP or VIP address of the Access Edge service of Lync on-premises.</span></span>
    
      - <span data-ttu-id="48499-132">如果您的組織使用的分割 DNS (有時稱為「分裂-大腦 DNS」 ) ，請確定透過內部 DNS 區域解析名稱的使用者會定向至前端集區。</span><span class="sxs-lookup"><span data-stu-id="48499-132">If your organization uses split DNS (sometimes called “split-brain DNS”), make sure that users resolving names through the internal DNS zone are directed to the Front End Pool.</span></span>

6.  <span data-ttu-id="48499-133">輸入 `Get-CsUser` Cmdlet 以檢查您將會移動之使用者的一些屬性。</span><span class="sxs-lookup"><span data-stu-id="48499-133">Type the `Get-CsUser` cmdlet to check some properties about the users you’ll be moving.</span></span> <span data-ttu-id="48499-134">您想確定 HostingProviderProxyFQDN 已設定為 `"sipfed.online.lync.com"` ，且 SIP 位址設定正確。</span><span class="sxs-lookup"><span data-stu-id="48499-134">You want to make sure that the HostingProviderProxyFQDN is set to `"sipfed.online.lync.com"` and that the SIP addresses are set correctly.</span></span>

7.  <span data-ttu-id="48499-135">將 Lync Online 使用者移至 Lync 內部部署。</span><span class="sxs-lookup"><span data-stu-id="48499-135">Move Lync Online users to Lync on-premises.</span></span>
    
    <span data-ttu-id="48499-136">若要移動單一使用者，請輸入：</span><span class="sxs-lookup"><span data-stu-id="48499-136">To move a single user, type this:</span></span>
    
       ```PowerShell
       $cred = Get-Credential
       ```
    
       ```PowerShell
       Move-CsUser -Identity <username>@contoso.com -Target "<fe-pool>.contoso.com" -Credential $cred -HostedMigrationOverrideURL <URL>
       ```
    
    <span data-ttu-id="48499-137">您可以使用 **get-csuser** 指令程式和– Filter 參數來移動多位使用者，以選取具有特定屬性的使用者。</span><span class="sxs-lookup"><span data-stu-id="48499-137">You can move multiple users by using the **Get-CsUSer** cmdlet with the –Filter parameter to select the users with a specific property.</span></span> <span data-ttu-id="48499-138">例如，您可以透過篩選 {主控提供者– eq "sipfed.online.lync.om"} 來選取所有的 Lync Online 使用者。</span><span class="sxs-lookup"><span data-stu-id="48499-138">For example, you could select all Lync Online users by filtering for {Hosting Provider –eq “sipfed.online.lync.om”}.</span></span> <span data-ttu-id="48499-139">然後，您可以將傳回的使用者輸送至 **get-csuser** Cmdlet，如下所示。</span><span class="sxs-lookup"><span data-stu-id="48499-139">You can then pipe the returned users to the **Move-CsUSer** cmdlet, as shown below.</span></span>
    
        Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com" -Credential $creds -HostedMigrationOverrideURL <URL>
    
    <span data-ttu-id="48499-140">針對 **HostedMigrationOverrideUrl** 參數所指定的 url 格式，必須是正在執行裝載遷移服務之集區的 url，格式如下： *Https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc*。</span><span class="sxs-lookup"><span data-stu-id="48499-140">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: *Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc*.</span></span>
    
    <span data-ttu-id="48499-141">您可以透過查看 Microsoft 365 或 Office 365 組織帳戶的 Lync Online 控制台 URL，來決定主控遷移服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="48499-141">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>
    
    <div>
    
    ## <a name="to-determine-the-hosted-migration-service-url-for-your-organizaton"></a><span data-ttu-id="48499-142">決定 organizaton 的主控遷移服務 URL</span><span class="sxs-lookup"><span data-stu-id="48499-142">To determine the Hosted Migration Service URL for your organizaton</span></span>
    
    1.  <span data-ttu-id="48499-143">以管理員身分登入您的 Microsoft 365 或 Office 365 組織。</span><span class="sxs-lookup"><span data-stu-id="48499-143">Log in to your Microsoft 365 or Office 365 organization as an administrator.</span></span>
    
    2.  <span data-ttu-id="48499-144">開啟 **Lync 系統管理中心**。</span><span class="sxs-lookup"><span data-stu-id="48499-144">Open the **Lync admin center**.</span></span>
    
    3.  <span data-ttu-id="48499-145">在 [ **Lync 系統管理中心** ] 顯示時，選取 [位址] 列中的 URL，並將其複製到 **lync.com**。</span><span class="sxs-lookup"><span data-stu-id="48499-145">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="48499-146">URL 的範例類似下列所示：</span><span class="sxs-lookup"><span data-stu-id="48499-146">An example URL looks similar to the following:</span></span>
        
        `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`
    
    4.  <span data-ttu-id="48499-147">使用系統**管理員**取代 URL 中的**webdir** ，產生下列結果：</span><span class="sxs-lookup"><span data-stu-id="48499-147">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
        
        `https://admin0a.online.lync.com`
    
    5.  <span data-ttu-id="48499-148">在 URL: **/HostedMigration/hostedmigrationservice.svc**中附加下列字串。</span><span class="sxs-lookup"><span data-stu-id="48499-148">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
        
        <span data-ttu-id="48499-149">產生的 URL （ **HostedMigrationOverrideUrl**的值）應如下所示：</span><span class="sxs-lookup"><span data-stu-id="48499-149">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
        
        `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    </div>
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="48499-150">Rtcxds 資料庫之交易記錄檔的預設大小上限為 16 GB。</span><span class="sxs-lookup"><span data-stu-id="48499-150">The default maximum size for transaction log files of the rtcxds database is 16 GB.</span></span> <span data-ttu-id="48499-151">如果您同時移動大量的使用者，尤其是當您已啟用鏡像，這樣做可能會不夠大。</span><span class="sxs-lookup"><span data-stu-id="48499-151">This might not be big enough if you’re moving a large number of users at once, especially if you have mirroring enabled.</span></span> <span data-ttu-id="48499-152">若要解決此問題，您可以定期增加檔案大小或備份記錄檔。</span><span class="sxs-lookup"><span data-stu-id="48499-152">To get around this you can increase the file size or back up the log files regularly.</span></span> <span data-ttu-id="48499-153">如需詳細資訊，請參閱 <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A> 。</span><span class="sxs-lookup"><span data-stu-id="48499-153">For more information, see <A class=uri href="https://support.microsoft.com/kb/2756725">https://support.microsoft.com/kb/2756725</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="48499-154">這是選擇性的步驟。</span><span class="sxs-lookup"><span data-stu-id="48499-154">This is an optional step.</span></span> <span data-ttu-id="48499-155">如果您需要與 Exchange 2013 線上整合，您必須使用其他主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="48499-155">If you need to integrate with Exchange 2013 Online, you need to use an additional hosting provider.</span></span> <span data-ttu-id="48499-156">如需詳細資訊，請參閱設定 [內部部署 Lync Server 2013 與 Exchange Online 整合](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="48499-156">For details, see [Configuring on-premises Lync Server 2013 integration with Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md).</span></span>

9.  <span data-ttu-id="48499-157">現在已移動使用者。</span><span class="sxs-lookup"><span data-stu-id="48499-157">The users are now moved.</span></span> <span data-ttu-id="48499-158">若要檢查使用者在下表中顯示的屬性是否具有正確的值，請輸入此 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="48499-158">To check that a user has correct values for the attributes shown in the following table, type this cmdlet:</span></span>
    
        Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="48499-159">Active Directory 屬性</span><span class="sxs-lookup"><span data-stu-id="48499-159">Active Directory attribute</span></span></th>
    <th><span data-ttu-id="48499-160">屬性名稱</span><span class="sxs-lookup"><span data-stu-id="48499-160">Attribute name</span></span></th>
    <th><span data-ttu-id="48499-161">正確的 Lync Online 使用者值</span><span class="sxs-lookup"><span data-stu-id="48499-161">Correct value for Lync Online user</span></span></th>
    <th><span data-ttu-id="48499-162">正確的 Lync 使用者-內部部署使用者值</span><span class="sxs-lookup"><span data-stu-id="48499-162">Correct value for Lync on–premises users</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="48499-163">msRTCSIP DeploymentLocator</span><span class="sxs-lookup"><span data-stu-id="48499-163">msRTCSIP-DeploymentLocator</span></span></p></td>
    <td><p><span data-ttu-id="48499-164">HostingProvider</span><span class="sxs-lookup"><span data-stu-id="48499-164">HostingProvider</span></span></p></td>
    <td><p><span data-ttu-id="48499-165">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="48499-165">sipfed.online.lync.com</span></span></p></td>
    <td><p><span data-ttu-id="48499-166">DNS-SRV</span><span class="sxs-lookup"><span data-stu-id="48499-166">SRV:</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="48499-167">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="48499-167">msRTCSIP-PrimaryUserAddress</span></span></p></td>
    <td><p><span data-ttu-id="48499-168">SIPAddress</span><span class="sxs-lookup"><span data-stu-id="48499-168">SIPAddress</span></span></p></td>
    <td><p><span data-ttu-id="48499-169">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="48499-169">sip:userName@contoso.com</span></span></p></td>
    <td><p><span data-ttu-id="48499-170">sip:userName@contoso.com</span><span class="sxs-lookup"><span data-stu-id="48499-170">sip:userName@contoso.com</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="48499-171">msRTCSIP-UserEnabled</span><span class="sxs-lookup"><span data-stu-id="48499-171">msRTCSIP-UserEnabled</span></span></p></td>
    <td><p><span data-ttu-id="48499-172">啟用</span><span class="sxs-lookup"><span data-stu-id="48499-172">Enabled</span></span></p></td>
    <td><p><span data-ttu-id="48499-173">True</span><span class="sxs-lookup"><span data-stu-id="48499-173">True</span></span></p></td>
    <td><p><span data-ttu-id="48499-174">True</span><span class="sxs-lookup"><span data-stu-id="48499-174">True</span></span></p></td>
    </tr>
    </tbody>
    </table>


10. <span data-ttu-id="48499-175">已移動的每個使用者都必須登入 Lync，然後重新登入。</span><span class="sxs-lookup"><span data-stu-id="48499-175">Each user who has been moved will need to log out of Lync, then log back in.</span></span> <span data-ttu-id="48499-176">當他們登入時，應驗證他們的連絡人清單，並視需要新增連絡人。</span><span class="sxs-lookup"><span data-stu-id="48499-176">When they log in they should verify their contact lists, and add contacts if needed.</span></span>
    
    <span data-ttu-id="48499-177">請注意，排定的會議不會從 Lync Online 遷移至 Lync 內部部署。</span><span class="sxs-lookup"><span data-stu-id="48499-177">Note that scheduled meetings are not migrated from Lync Online to Lync on-premises.</span></span> <span data-ttu-id="48499-178">使用者在移動這些會議之後，將需要重新排定。</span><span class="sxs-lookup"><span data-stu-id="48499-178">Users will need to reschedule these meetings after being moved.</span></span>
    
    <span data-ttu-id="48499-179">在更新 DNS 記錄，並將所有使用者定向至內部部署後，HostingProvider 屬性會指示 Lync 使用者使用 SRV 記錄，或將其指引至線上提供者 "sipfed.online.lync.com"。</span><span class="sxs-lookup"><span data-stu-id="48499-179">After the DNS records are updated and all users are directed to On premise, the HostingProvider attribute directs the Lync user to either use SRV records or direct them to the Online provider “sipfed.online.lync.com.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

