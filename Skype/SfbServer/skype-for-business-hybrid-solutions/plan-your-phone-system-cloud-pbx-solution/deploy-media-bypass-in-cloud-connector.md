---
title: 在雲端連接器版本中部署媒體旁路
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: 請閱讀本主題，以瞭解使用雲端連接器版本2.0 和更新版本部署媒體旁路的步驟。
ms.openlocfilehash: 771d3a7294fde38b032e4cd9a281f70156280d3a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802343"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="4886a-103">在雲端連接器版本中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="4886a-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
<span data-ttu-id="4886a-104">請閱讀本主題，以瞭解使用雲端連接器版本2.0 和更新版本部署媒體旁路的步驟。</span><span class="sxs-lookup"><span data-stu-id="4886a-104">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="4886a-105">「媒體旁路」可讓用戶端直接傳送媒體至公用交換式電話網絡（PSTN）的下一個躍點（閘道或會話邊界控制器（SBC）），並從媒體路徑中消除雲端連接器版本元件。</span><span class="sxs-lookup"><span data-stu-id="4886a-105">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="4886a-106">另請參閱[在雲端連接器版本中使用媒體旁路方案](plan-for-media-bypass-in-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="4886a-106">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="4886a-107">啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="4886a-107">Enable media bypass</span></span>

<span data-ttu-id="4886a-108">若要啟用媒體旁路，您必須設定媒體旁路 web 服務的 DNS 名稱，並在租使用者配置中開啟 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="4886a-108">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="4886a-109">媒體旁路 web 服務會自動在每個中繼伺服器上進行部署。</span><span class="sxs-lookup"><span data-stu-id="4886a-109">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="4886a-110">租使用者管理員必須挑選混合式語音服務（網站）的名稱，且此名稱應該來自已註冊為混合式語音的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="4886a-110">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="4886a-111">不論用戶端位置為何，所有雲端連接器裝置和所有 PSTN 網站上的服務名稱應該都是相同的。</span><span class="sxs-lookup"><span data-stu-id="4886a-111">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="4886a-112">Web 服務只能在網路內部使用。</span><span class="sxs-lookup"><span data-stu-id="4886a-112">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="4886a-113">租使用者管理員必須在內部生產 Active Directory 中設定 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="4886a-113">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="4886a-114">如果您有複雜的多網站環境，請參閱範例：在[複雜的多網站環境中，媒體略過網站的 DNS 記錄](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="4886a-114">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="4886a-115">DNS 記錄應該只解析內部網路用戶端;它不應該解析外部網路用戶端。</span><span class="sxs-lookup"><span data-stu-id="4886a-115">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="4886a-116">在設定 DNS 之後，使用與商務用 Skype 系統管理員認證的遠端 PowerShell，連線到商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="4886a-116">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="4886a-117">如需詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="4886a-117">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="4886a-118">在 PowerShell 會話中，輸入下列命令以啟用媒體旁路：</span><span class="sxs-lookup"><span data-stu-id="4886a-118">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="4886a-119">啟用媒體旁路的程式分為兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="4886a-119">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="4886a-120">新的-CsNetworkMedia Cmdlet 不會立即儲存新的設定;它只會在記憶體中建立設定。</span><span class="sxs-lookup"><span data-stu-id="4886a-120">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="4886a-121">由此 Cmdlet 建立的物件必須儲存到變數，然後指派給網路設定的 MediaBypassSettings 屬性。</span><span class="sxs-lookup"><span data-stu-id="4886a-121">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="4886a-122">如需詳細資訊，請參閱[範例：在複雜的多網站環境中，媒體略過網站的 DNS 記錄](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="4886a-122">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="4886a-123">內部部署與線上元件之間的複製可能需要長達24小時，因此 Microsoft 建議您在啟用使用者之前先執行必要的命令。</span><span class="sxs-lookup"><span data-stu-id="4886a-123">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="4886a-124">確認媒體旁路設定</span><span class="sxs-lookup"><span data-stu-id="4886a-124">Confirm media bypass settings</span></span>

<span data-ttu-id="4886a-125">您可以檢查媒體旁路設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4886a-125">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="4886a-126">若要在您的租使用者池中檢查線上複製，請在遠端 PowerShell 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4886a-126">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4886a-127">若要檢查內部部署的複製，請連線到雲端連接器轉送伺服器，在 PowerShell 中執行下列命令，並確認 Enabled = True 和 AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="4886a-127">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4886a-128">若要檢查用戶端設定，請登出商務用 Skype 用戶端，重新登入，然後確認用戶端已收到服務 URL，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4886a-128">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="4886a-129">開啟%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。</span><span class="sxs-lookup"><span data-stu-id="4886a-129">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="4886a-130">搜尋 hybridconfigserviceinternalurl 並確認 URL 與您所定義的 URL 相符。</span><span class="sxs-lookup"><span data-stu-id="4886a-130">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="4886a-131">變更媒體旁路參數</span><span class="sxs-lookup"><span data-stu-id="4886a-131">Change media bypass parameters</span></span>

<span data-ttu-id="4886a-132">租使用者管理員可以執行下列 Cmdlet 來變更 web 服務的 DNS 名稱：</span><span class="sxs-lookup"><span data-stu-id="4886a-132">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="4886a-133">用戶端需要登出並登入以取得新的服務名稱並辨識變更。</span><span class="sxs-lookup"><span data-stu-id="4886a-133">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="4886a-134">暫時停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="4886a-134">Temporarily disable media bypass</span></span>

<span data-ttu-id="4886a-135">這個案例對於疑難排解或維護可能很有用。</span><span class="sxs-lookup"><span data-stu-id="4886a-135">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="4886a-136">若要停用服務，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4886a-136">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="4886a-137">變更之後，將變更複製到所有雲端連接器可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="4886a-137">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="4886a-138">若要檢查複製狀態，請在雲端連接器中繼伺服器上的 PowerShell 中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4886a-138">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="4886a-139">複製變更之後，中繼伺服器上的 web 服務就會開始拒絕媒體旁路服務的用戶端要求。</span><span class="sxs-lookup"><span data-stu-id="4886a-139">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="4886a-140">永久停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="4886a-140">Disable media bypass permanently</span></span>

<span data-ttu-id="4886a-141">若要永久停用媒體旁路，租使用者管理員必須執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4886a-141">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="4886a-142">系統管理員也必須從內部 DNS 伺服器移除 [媒體旁路] 的網址。</span><span class="sxs-lookup"><span data-stu-id="4886a-142">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="4886a-143">進行變更之後，將變更複製到所有雲端連接器裝置可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="4886a-143">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="4886a-144">範例：在複雜的多網站環境中，媒體略過網站的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="4886a-144">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="4886a-145"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="4886a-145"><a name="Example"> </a></span></span>

<span data-ttu-id="4886a-146">用戶端會從內部 DNS 伺服器接收媒體旁路 web 服務的網址。</span><span class="sxs-lookup"><span data-stu-id="4886a-146">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="4886a-147">在所有雲端連接器裝置和雲端連接器 PSTN 網站上，web 服務的名稱都是相同的。</span><span class="sxs-lookup"><span data-stu-id="4886a-147">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="4886a-148">在複雜的多網站環境中，我們建議您針對地理位置的流量管理使用 Windows 2016 DNS 原則，讓用戶端可以重新導向到網路的本機服務。</span><span class="sxs-lookup"><span data-stu-id="4886a-148">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="4886a-149">如需有關 Windows 2016 DNS 原則的詳細資訊，請參閱[在主要伺服器上使用地理位置的流量管理的 DNS 原則](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)。</span><span class="sxs-lookup"><span data-stu-id="4886a-149">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="4886a-150">下列是具有多個網站之公司的配置範例，這些網站使用針對地理位置的流量管理進行的 Windows 2016 DNS 原則。</span><span class="sxs-lookup"><span data-stu-id="4886a-150">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="4886a-151">略過服務的名稱為「hybridvoice.adatum.biz」。</span><span class="sxs-lookup"><span data-stu-id="4886a-151">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="4886a-152">[阿姆斯特丹] 中的網站有四個雲端連接器裝置，且已使用下列中繼伺服器 IP 位址進行部署：</span><span class="sxs-lookup"><span data-stu-id="4886a-152">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="4886a-153">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="4886a-153">192.168.1.45</span></span>
    
- <span data-ttu-id="4886a-154">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="4886a-154">192.168.1.46</span></span>
    
- <span data-ttu-id="4886a-155">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="4886a-155">192.168.1.47</span></span>
    
- <span data-ttu-id="4886a-156">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="4886a-156">192.168.1.48</span></span>
    
<span data-ttu-id="4886a-157">西雅圖中的網站有三個部署了下列中繼伺服器 IP 位址的雲端連接器裝置：</span><span class="sxs-lookup"><span data-stu-id="4886a-157">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="4886a-158">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="4886a-158">10.10.1.8</span></span>
    
- <span data-ttu-id="4886a-159">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="4886a-159">10.10.1.9</span></span>
    
- <span data-ttu-id="4886a-160">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="4886a-160">10.10.1.10</span></span>
    
<span data-ttu-id="4886a-161">使用以地理位置為基礎的流量管理，DNS 伺服器的設定方式如下：</span><span class="sxs-lookup"><span data-stu-id="4886a-161">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="4886a-162">為阿姆斯特丹和西雅圖子網建立 DNS 用戶端子網。</span><span class="sxs-lookup"><span data-stu-id="4886a-162">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="4886a-163">為阿姆斯特丹和西雅圖的 adatum.biz 建立 DNS 區域範圍。</span><span class="sxs-lookup"><span data-stu-id="4886a-163">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="4886a-164">在每個 DNS 區域範圍中建立 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="4886a-164">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="4886a-165">阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="4886a-165">Amsterdam</span></span>
    
   - <span data-ttu-id="4886a-166">鍵入 A;</span><span class="sxs-lookup"><span data-stu-id="4886a-166">Type A;</span></span>
    
   - <span data-ttu-id="4886a-167">Adatum.biz DNS 區域中的名稱： hybridvoice</span><span class="sxs-lookup"><span data-stu-id="4886a-167">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="4886a-168">目標：192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="4886a-168">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="4886a-169">建立其他中繼伺服器的其他記錄</span><span class="sxs-lookup"><span data-stu-id="4886a-169">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="4886a-170">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="4886a-170">192.168.1.46</span></span>
    
   - <span data-ttu-id="4886a-171">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="4886a-171">192.168.1.47</span></span>
    
   - <span data-ttu-id="4886a-172">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="4886a-172">192.168.1.48</span></span>
    
     <span data-ttu-id="4886a-173">西雅圖</span><span class="sxs-lookup"><span data-stu-id="4886a-173">Seattle</span></span>
    
   - <span data-ttu-id="4886a-174">輸入</span><span class="sxs-lookup"><span data-stu-id="4886a-174">Type A</span></span>
    
   - <span data-ttu-id="4886a-175">Name： hybridvoice adatum.biz DNS 區域</span><span class="sxs-lookup"><span data-stu-id="4886a-175">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="4886a-176">目標：10.10.1。8</span><span class="sxs-lookup"><span data-stu-id="4886a-176">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="4886a-177">建立其他中繼伺服器的其他記錄</span><span class="sxs-lookup"><span data-stu-id="4886a-177">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="4886a-178">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="4886a-178">10.10.1.9</span></span>
    
   - <span data-ttu-id="4886a-179">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="4886a-179">10.10.1.10</span></span>
    
4. <span data-ttu-id="4886a-180">建立將用戶端子網連接至適當區域範圍的 DNS 原則，以確保所需的 DNS 解析度。</span><span class="sxs-lookup"><span data-stu-id="4886a-180">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="4886a-181">此時，從阿姆斯特丹子網上進行 DNS 查詢的用戶端將會傳回192.168.1.45、192.168.1.46、192.168.1.47 和192.168.1.48 位址，而用戶端建立相同的查詢表單時，會傳回10.10.1.8，10.10.1.9 和10.10.1.10。</span><span class="sxs-lookup"><span data-stu-id="4886a-181">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="4886a-182">如果 CCE 裝置看起來沒有取得更新的設定，請檢查裝置能否透過遠端 PowerShell 與租使用者取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="4886a-182">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="4886a-183">您可以在 CCE 主機上使用 [遠端 PowerShell] 來檢查裝置狀態，以取得 CsHybridPSTNAppliance 或使用 PowerShell，以 CcApplianceStatus 來檢查狀態。</span><span class="sxs-lookup"><span data-stu-id="4886a-183">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="4886a-184">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4886a-184">See also</span></span>
<span data-ttu-id="4886a-185"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="4886a-185"><a name="Example"> </a></span></span>

[<span data-ttu-id="4886a-186">規劃 Cloud Connector Edition 中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="4886a-186">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
