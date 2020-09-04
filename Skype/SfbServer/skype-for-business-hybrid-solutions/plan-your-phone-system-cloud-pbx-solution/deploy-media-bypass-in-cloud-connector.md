---
title: 在雲端連接器 Edition 中部署媒體旁路
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
description: 閱讀此主題以瞭解使用雲端連接器 Edition 版本2.0 和更新版本部署媒體旁路的步驟。
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359309"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a><span data-ttu-id="0e512-103">在雲端連接器 Edition 中部署媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0e512-103">Deploy media bypass in Cloud Connector Edition</span></span>
 
> [!Important]
> <span data-ttu-id="0e512-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="0e512-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="0e512-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="0e512-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="0e512-106">閱讀此主題以瞭解使用雲端連接器 Edition 版本2.0 和更新版本部署媒體旁路的步驟。</span><span class="sxs-lookup"><span data-stu-id="0e512-106">Read this topic to learn about steps to deploy media bypass with Cloud Connector Edition version 2.0 and later.</span></span> 
  
<span data-ttu-id="0e512-107">媒體旁路可讓用戶端直接將媒體傳送到公用交換電話網路 (PSTN) 下一個躍點（閘道或會話邊界控制器 (SBC) ），並從媒體路徑中消除雲端連接器版本元件。</span><span class="sxs-lookup"><span data-stu-id="0e512-107">Media bypass allows a client to send media directly to the Public Switched Telephone Network (PSTN) next hop—a gateway or Session Border Controller (SBC)—and eliminate the Cloud Connector Edition component from the media path.</span></span> <span data-ttu-id="0e512-108">另請參閱 [規劃雲端連接器 Edition 中的媒體旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。</span><span class="sxs-lookup"><span data-stu-id="0e512-108">See also [Plan for media bypass in Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).</span></span>
  
## <a name="enable-media-bypass"></a><span data-ttu-id="0e512-109">啟用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0e512-109">Enable media bypass</span></span>

<span data-ttu-id="0e512-110">若要啟用媒體旁路，您必須設定媒體旁路 web 服務的 DNS 名稱，並在租使用者設定中開啟媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="0e512-110">To enable media bypass, you must configure the DNS name of the media bypass web service and turn on media bypass in the tenant configuration.</span></span> <span data-ttu-id="0e512-111">媒體旁路 web 服務會自動在每家的轉送伺服器上進行部署。</span><span class="sxs-lookup"><span data-stu-id="0e512-111">The media bypass web service deploys automatically on every Mediation Server.</span></span> <span data-ttu-id="0e512-112">租使用者管理員必須為混合語音服務 (網站) 挑選名稱，而且此名稱應來自為混合式語音註冊的 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="0e512-112">A tenant administrator must pick a name for a hybrid voice service (site), and this name should be from a SIP domain registered for hybrid voice.</span></span> <span data-ttu-id="0e512-113">不管用戶端位置為何，所有雲端連接器裝置和所有 PSTN 網站上的服務名稱應該都相同。</span><span class="sxs-lookup"><span data-stu-id="0e512-113">The service name should be the same across all Cloud Connector appliances and all PSTN sites regardless of the client location.</span></span> <span data-ttu-id="0e512-114">Web 服務應該只可在網路內部使用。</span><span class="sxs-lookup"><span data-stu-id="0e512-114">The web service should only be available internally on the network.</span></span>
  
<span data-ttu-id="0e512-115">租使用者管理員必須在內部實際執行 Active Directory 中設定 DNS A 記錄。</span><span class="sxs-lookup"><span data-stu-id="0e512-115">A tenant administrator must configure a DNS A record in the internal production Active Directory.</span></span> <span data-ttu-id="0e512-116">如果您有複雜的多網站環境，請參閱 [範例範例：在複雜的多網站環境中，媒體旁路網站 DNS 記錄](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="0e512-116">If you have a complex multi-site environment, see the example in [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span> <span data-ttu-id="0e512-117">DNS 記錄應該只解析內部網路用戶端;不應為外部網路用戶端解析。</span><span class="sxs-lookup"><span data-stu-id="0e512-117">The DNS record should only resolve for internal network clients; it should not resolve for external network clients.</span></span>
  
<span data-ttu-id="0e512-118">設定 DNS 之後，使用遠端 PowerShell 搭配商務用 Skype 系統管理員認證，連線至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="0e512-118">After configuring DNS, connect to Skype for Business Online by using remote PowerShell with Skype for Business Administrator credentials.</span></span> <span data-ttu-id="0e512-119">如需詳細資訊，請參閱 [設定您的電腦以進行 Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) 。</span><span class="sxs-lookup"><span data-stu-id="0e512-119">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) .</span></span>
  
<span data-ttu-id="0e512-120">在 PowerShell 會話中，輸入下列命令以啟用媒體旁路：</span><span class="sxs-lookup"><span data-stu-id="0e512-120">In the PowerShell session, enter the following commands to enable media bypass:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="0e512-121">啟用媒體旁路是兩個步驟的處理常式。</span><span class="sxs-lookup"><span data-stu-id="0e512-121">Enabling media bypass is a two-step process.</span></span> <span data-ttu-id="0e512-122">CsNetworkMedia Cmdlet 不會立即儲存新的設定。它只會在記憶體中建立設定。</span><span class="sxs-lookup"><span data-stu-id="0e512-122">The New-CsNetworkMedia cmdlet does not immediately save the new configuration; it only creates the settings in memory.</span></span> <span data-ttu-id="0e512-123">此 Cmdlet 所建立的物件必須儲存在變數中，然後指定給網路設定的 MediaBypassSettings 屬性。</span><span class="sxs-lookup"><span data-stu-id="0e512-123">The object created by this cmdlet must be saved to a variable, and then assigned to the MediaBypassSettings property of the network configuration.</span></span> <span data-ttu-id="0e512-124">如需詳細資訊，請參閱 [範例：在複雜的多網站環境中媒體旁路網站 DNS 記錄](deploy-media-bypass-in-cloud-connector.md#Example)。</span><span class="sxs-lookup"><span data-stu-id="0e512-124">For more information, see [Example: media bypass web site DNS records in complex multi-site environments](deploy-media-bypass-in-cloud-connector.md#Example).</span></span>
  
<span data-ttu-id="0e512-125">在內部部署和線上元件之間進行的複寫可能需要長達24小時，所以 Microsoft 建議您先執行必要的命令，再啟用使用者。</span><span class="sxs-lookup"><span data-stu-id="0e512-125">The replication between the on-premises and online components can take up to 24 hours, so Microsoft recommends that you run the necessary commands before enabling users.</span></span>
  
## <a name="confirm-media-bypass-settings"></a><span data-ttu-id="0e512-126">確認媒體旁路設定</span><span class="sxs-lookup"><span data-stu-id="0e512-126">Confirm media bypass settings</span></span>

<span data-ttu-id="0e512-127">您可以檢查媒體旁路設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0e512-127">You can check the media bypass settings as follows.</span></span> 
  
<span data-ttu-id="0e512-128">若要檢查您租使用者集區的線上複寫，請在遠端 PowerShell: 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0e512-128">To check online replication to your tenant pool, run the following command in remote PowerShell:</span></span>
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="0e512-129">若要檢查內部部署的複寫，請連線至雲端連接器轉送伺服器，在 PowerShell 中執行下列命令，並確認 Enabled = True 和 AlwaysBypass = True</span><span class="sxs-lookup"><span data-stu-id="0e512-129">To check the on-premises replication, connect to the Cloud Connector Mediation servers, run the following command in PowerShell, and confirm that Enabled=True and AlwaysBypass=True</span></span>
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="0e512-130">若要檢查用戶端設定，請登出商務用 Skype 用戶端，並重新登入，並確認用戶端已接收到服務 URL，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e512-130">To check the client settings, sign out of the Skype for Business client, sign back in, and confirm that the client has received the service URL as follows:</span></span>
  
1. <span data-ttu-id="0e512-131">開啟%appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog。</span><span class="sxs-lookup"><span data-stu-id="0e512-131">Open %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog.</span></span> 
    
2. <span data-ttu-id="0e512-132">搜尋 hybridconfigserviceinternalurl 並確認 URL 與您定義的 URL 相符。</span><span class="sxs-lookup"><span data-stu-id="0e512-132">Search for hybridconfigserviceinternalurl and confirm the URL matches the one you defined.</span></span>
    
## <a name="change-media-bypass-parameters"></a><span data-ttu-id="0e512-133">變更媒體旁路參數</span><span class="sxs-lookup"><span data-stu-id="0e512-133">Change media bypass parameters</span></span>

<span data-ttu-id="0e512-134">租使用者管理員可以執行下列 Cmdlet，以變更 web 服務的 DNS 名稱：</span><span class="sxs-lookup"><span data-stu-id="0e512-134">Tenant administrators are able to change the DNS name of the web service by running the following cmdlet:</span></span>
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> <span data-ttu-id="0e512-135">用戶端需要登出並登入以取得新的服務名稱並辨識變更。</span><span class="sxs-lookup"><span data-stu-id="0e512-135">Clients need to sign out and sign in to get the new service name and recognize the change.</span></span> 
  
## <a name="temporarily-disable-media-bypass"></a><span data-ttu-id="0e512-136">暫時停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0e512-136">Temporarily disable media bypass</span></span>

<span data-ttu-id="0e512-137">此案例可能會對疑難排解或維護十分有用。</span><span class="sxs-lookup"><span data-stu-id="0e512-137">This scenario might be useful for troubleshooting or maintenance.</span></span> <span data-ttu-id="0e512-138">若要停用服務，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0e512-138">To disable the service, run the following cmdlets:</span></span>
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

<span data-ttu-id="0e512-139">進行變更之後，可能需要一些時間才能將變更複寫到所有雲端連接器。</span><span class="sxs-lookup"><span data-stu-id="0e512-139">After making the change, it could take some time for changes to replicate to all Cloud Connectors.</span></span> <span data-ttu-id="0e512-140">若要檢查複寫的狀態，請在雲端連接器轉送伺服器的 PowerShell 中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0e512-140">To check the status of replication, run the following cmdlet in PowerShell on Cloud Connector Mediation servers:</span></span> 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

<span data-ttu-id="0e512-141">在變更複寫之後，轉送伺服器上的 web 服務會開始拒絕媒體旁路服務的用戶端要求。</span><span class="sxs-lookup"><span data-stu-id="0e512-141">After the changes replicate, the web service on the Mediation Server will start rejecting client requests for the media bypass service.</span></span>
  
## <a name="disable-media-bypass-permanently"></a><span data-ttu-id="0e512-142">永久停用媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0e512-142">Disable media bypass permanently</span></span>

<span data-ttu-id="0e512-143">若要永久停用媒體旁路，租使用者管理員必須執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0e512-143">To permanently disable media bypass, a tenant administrator needs to run the following commands:</span></span> 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

<span data-ttu-id="0e512-144">系統管理員也需要從內部 DNS 伺服器移除媒體旁路的網頁位址。</span><span class="sxs-lookup"><span data-stu-id="0e512-144">An administrator will also need to remove the web addresses for media bypass from internal DNS servers.</span></span> <span data-ttu-id="0e512-145">進行變更之後，可能需要一些時間才能將變更複寫到所有雲端連接器裝置。</span><span class="sxs-lookup"><span data-stu-id="0e512-145">After making the change, it could take some time for changes to replicate to all Cloud Connector appliances.</span></span> 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a><span data-ttu-id="0e512-146">範例：在複雜的多網站環境中，媒體旁路網站 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="0e512-146">Example: media bypass web site DNS records in complex multi-site environments</span></span>
<span data-ttu-id="0e512-147"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="0e512-147"><a name="Example"> </a></span></span>

<span data-ttu-id="0e512-148">用戶端將從內部 DNS 伺服器接收媒體旁路 web 服務的網址。</span><span class="sxs-lookup"><span data-stu-id="0e512-148">Clients will receive the web address of the media bypass web service from an internal DNS server.</span></span> <span data-ttu-id="0e512-149">所有雲端連接器裝置和雲端連接器 PSTN 網站上的 web 服務名稱都是相同的。</span><span class="sxs-lookup"><span data-stu-id="0e512-149">The name of the web service will be the same across all Cloud Connector appliances and Cloud Connector PSTN sites.</span></span> <span data-ttu-id="0e512-150">在複雜的多網站環境中，我們建議您針對地理位置的流量管理使用 Windows 2016 DNS 原則，讓用戶端可以重新導向至其網路的本機 web 服務。</span><span class="sxs-lookup"><span data-stu-id="0e512-150">In a complex multi-site environment, we recommend using the Windows 2016 DNS Policy for Geo-Location Based Traffic Management, so clients can be redirected to the web service which is local for their network.</span></span> 
  
<span data-ttu-id="0e512-151">有關 Windows 2016 DNS 原則的詳細資訊，請參閱 [使用 DNS 原則進行地理位置的流量管理與主要伺服器](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)。</span><span class="sxs-lookup"><span data-stu-id="0e512-151">Fore more information about Windows 2016 DNS Policies, see [Use DNS Policy for Geo-Location Based Traffic Management with Primary Servers](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location).</span></span>
  
<span data-ttu-id="0e512-152">以下是針對地理位置流量管理使用 Windows 2016 DNS 原則之公司的設定範例。</span><span class="sxs-lookup"><span data-stu-id="0e512-152">The following is an example of configuration for a company with several sites using Windows 2016 DNS Policy for Geo-Location Based Traffic Management.</span></span>
  
<span data-ttu-id="0e512-153">旁路服務的名稱是 "hybridvoice.adatum.biz"。</span><span class="sxs-lookup"><span data-stu-id="0e512-153">The name for the bypass service is 'hybridvoice.adatum.biz'.</span></span>
  
<span data-ttu-id="0e512-154">阿姆斯特丹中的網站有四個 Cloud Connector 裝置，已使用下列轉送伺服器 IP 位址進行部署：</span><span class="sxs-lookup"><span data-stu-id="0e512-154">The site in Amsterdam has four Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="0e512-155">192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="0e512-155">192.168.1.45</span></span>
    
- <span data-ttu-id="0e512-156">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="0e512-156">192.168.1.46</span></span>
    
- <span data-ttu-id="0e512-157">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="0e512-157">192.168.1.47</span></span>
    
- <span data-ttu-id="0e512-158">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="0e512-158">192.168.1.48</span></span>
    
<span data-ttu-id="0e512-159">西雅圖的網站有三個雲端連接器裝置，已使用下列轉送伺服器 IP 位址進行部署：</span><span class="sxs-lookup"><span data-stu-id="0e512-159">The site in Seattle has three Cloud Connector appliances deployed with the following Mediation Server IP addresses:</span></span>
  
- <span data-ttu-id="0e512-160">10.10.1.8</span><span class="sxs-lookup"><span data-stu-id="0e512-160">10.10.1.8</span></span>
    
- <span data-ttu-id="0e512-161">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="0e512-161">10.10.1.9</span></span>
    
- <span data-ttu-id="0e512-162">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="0e512-162">10.10.1.10</span></span>
    
<span data-ttu-id="0e512-163">使用地理位置的流量管理，DNS 伺服器的設定如下：</span><span class="sxs-lookup"><span data-stu-id="0e512-163">Using Geo-Location Based Traffic Management, the DNS servers would be configured as follows:</span></span>
  
1. <span data-ttu-id="0e512-164">為阿姆斯特丹和西雅圖子網建立 DNS 用戶端子網。</span><span class="sxs-lookup"><span data-stu-id="0e512-164">Create DNS Client Subnets for both the Amsterdam and Seattle subnets.</span></span>
    
2. <span data-ttu-id="0e512-165">為阿姆斯特丹和西雅圖建立 adatum.biz 的 DNS 區域範圍。</span><span class="sxs-lookup"><span data-stu-id="0e512-165">Create DNS Zone Scopes for adatum.biz for both Amsterdam and Seattle.</span></span>
    
3. <span data-ttu-id="0e512-166">在每個 DNS 區域範圍中建立 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="0e512-166">Create DNS records in each DNS Zone Scope.</span></span>
    
    <span data-ttu-id="0e512-167">阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="0e512-167">Amsterdam</span></span>
    
   - <span data-ttu-id="0e512-168">輸入 A;</span><span class="sxs-lookup"><span data-stu-id="0e512-168">Type A;</span></span>
    
   - <span data-ttu-id="0e512-169">Name： adatum.biz DNS 區域中的 hybridvoice</span><span class="sxs-lookup"><span data-stu-id="0e512-169">Name : hybridvoice in the adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="0e512-170">目標：192.168.1.45</span><span class="sxs-lookup"><span data-stu-id="0e512-170">Target: 192.168.1.45</span></span>
    
     <span data-ttu-id="0e512-171">建立其他轉送伺服器的其他記錄</span><span class="sxs-lookup"><span data-stu-id="0e512-171">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="0e512-172">192.168.1.46</span><span class="sxs-lookup"><span data-stu-id="0e512-172">192.168.1.46</span></span>
    
   - <span data-ttu-id="0e512-173">192.168.1.47</span><span class="sxs-lookup"><span data-stu-id="0e512-173">192.168.1.47</span></span>
    
   - <span data-ttu-id="0e512-174">192.168.1.48</span><span class="sxs-lookup"><span data-stu-id="0e512-174">192.168.1.48</span></span>
    
     <span data-ttu-id="0e512-175">西雅圖</span><span class="sxs-lookup"><span data-stu-id="0e512-175">Seattle</span></span>
    
   - <span data-ttu-id="0e512-176">輸入</span><span class="sxs-lookup"><span data-stu-id="0e512-176">Type A</span></span>
    
   - <span data-ttu-id="0e512-177">名稱： hybridvoice in adatum.biz DNS 區域</span><span class="sxs-lookup"><span data-stu-id="0e512-177">Name : hybridvoice in adatum.biz DNS zone</span></span>
    
   - <span data-ttu-id="0e512-178">目標：10.10.1。8</span><span class="sxs-lookup"><span data-stu-id="0e512-178">Target: 10.10.1.8</span></span>
    
     <span data-ttu-id="0e512-179">建立其他轉送伺服器的其他記錄</span><span class="sxs-lookup"><span data-stu-id="0e512-179">Create additional records for additional mediation servers</span></span>
    
   - <span data-ttu-id="0e512-180">10.10.1.9</span><span class="sxs-lookup"><span data-stu-id="0e512-180">10.10.1.9</span></span>
    
   - <span data-ttu-id="0e512-181">10.10.1.10</span><span class="sxs-lookup"><span data-stu-id="0e512-181">10.10.1.10</span></span>
    
4. <span data-ttu-id="0e512-182">建立將用戶端子網上連至適當區域範圍的 DNS 原則，以確保所需的 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="0e512-182">Create the DNS policy that connects the client subnets to the appropriate zone scopes to ensure desired DNS resolution.</span></span>
    
<span data-ttu-id="0e512-183">此時，從阿姆斯特丹子網進行 DNS 查詢的用戶端將會傳回192.168.1.45、192.168.1.46、192.168.1.47 和192.168.1.48 位址，而建立相同查詢表單西雅圖的用戶端將會傳回10.10.1.8、10.10.1.9 和10.10.1.10。</span><span class="sxs-lookup"><span data-stu-id="0e512-183">At this point, clients making DNS queries from the Amsterdam subnet for hybridvoice.adatum.biz will return the 192.168.1.45, 192.168.1.46, 192.168.1.47 and 192.168.1.48 addresses, while clients making the same query form Seattle will return 10.10.1.8, 10.10.1.9 and 10.10.1.10.</span></span>

> [!NOTE]
> <span data-ttu-id="0e512-184">如果 CCE 裝置似乎沒有取得更新的設定，請查看裝置是否可以透過遠端 PowerShell 聯繫租使用者。</span><span class="sxs-lookup"><span data-stu-id="0e512-184">If the CCE appliance doesn't seem to be getting the updated settings, check to see if the appliance is able to contact the tenant via remote PowerShell.</span></span> <span data-ttu-id="0e512-185">您可以使用 [遠端 PowerShell] 以 CsHybridPSTNAppliance 檢查裝置狀態，或在 CCE 主機上使用 PowerShell，檢查 CcApplianceStatus 的狀態。</span><span class="sxs-lookup"><span data-stu-id="0e512-185">You can use Remote PowerShell to check appliance status with Get-CsHybridPSTNAppliance or use PowerShell on the CCE host to check status with Get-CcApplianceStatus.</span></span>

  
## <a name="see-also"></a><span data-ttu-id="0e512-186">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0e512-186">See also</span></span>
<span data-ttu-id="0e512-187"><a name="Example"> </a></span><span class="sxs-lookup"><span data-stu-id="0e512-187"><a name="Example"> </a></span></span>

[<span data-ttu-id="0e512-188">規劃 Cloud Connector Edition 中的媒體旁路</span><span class="sxs-lookup"><span data-stu-id="0e512-188">Plan for media bypass in Cloud Connector Edition</span></span>](plan-for-media-bypass-in-cloud-connector-edition.md)
