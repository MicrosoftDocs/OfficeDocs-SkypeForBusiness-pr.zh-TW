---
title: 在商務用 Skype Server 上部署及設定行動性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文將逐步引導您設定現有的商務用 Skype Server 安裝, 以使用行動裝置服務, 讓您的行動裝置能夠利用商務用 Skype Server 行動裝置功能。
ms.openlocfilehash: 35b9ca6a69dc5add9331aa5399a59a572bdf6906
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193540"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="83c45-103">在商務用 Skype Server 上部署及設定行動性</span><span class="sxs-lookup"><span data-stu-id="83c45-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="83c45-104">本文將逐步引導您設定現有的商務用 Skype Server 安裝, 以使用行動裝置服務, 讓您的行動裝置能夠利用商務用 Skype Server 行動裝置功能。</span><span class="sxs-lookup"><span data-stu-id="83c45-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="83c45-105">在已複習[商務用 Skype server 文章的行動方案規劃](../plan-your-deployment/mobility.md)中, 您應該準備好繼續執行下列步驟, 將行動部署到您的商務用 skype Server 環境。</span><span class="sxs-lookup"><span data-stu-id="83c45-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="83c45-106">這些步驟如下所示 (這個表格中包含許可權清單):</span><span class="sxs-lookup"><span data-stu-id="83c45-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="83c45-107">**分**</span><span class="sxs-lookup"><span data-stu-id="83c45-107">**Phase**</span></span>|<span data-ttu-id="83c45-108">**許可權**</span><span class="sxs-lookup"><span data-stu-id="83c45-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="83c45-109">建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="83c45-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="83c45-110">網域管理員</span><span class="sxs-lookup"><span data-stu-id="83c45-110">Domain Admins</span></span>  <br/> <span data-ttu-id="83c45-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="83c45-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="83c45-112">修改憑證</span><span class="sxs-lookup"><span data-stu-id="83c45-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="83c45-113">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="83c45-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="83c45-114">設定反向 proxy</span><span class="sxs-lookup"><span data-stu-id="83c45-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="83c45-115">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="83c45-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="83c45-116">使用混合式部署設定自動探索以進行行動</span><span class="sxs-lookup"><span data-stu-id="83c45-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="83c45-117">網域管理員</span><span class="sxs-lookup"><span data-stu-id="83c45-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="83c45-118">測試行動部署</span><span class="sxs-lookup"><span data-stu-id="83c45-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="83c45-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="83c45-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="83c45-120">針對推播通知進行設定</span><span class="sxs-lookup"><span data-stu-id="83c45-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="83c45-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="83c45-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="83c45-122">設定行動原則</span><span class="sxs-lookup"><span data-stu-id="83c45-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="83c45-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="83c45-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="83c45-124">下列各節包含的步驟假設您已閱讀規劃主題。</span><span class="sxs-lookup"><span data-stu-id="83c45-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="83c45-125">如果有任何專案感到困惑, 請隨意查看其中的資訊。</span><span class="sxs-lookup"><span data-stu-id="83c45-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="83c45-126">MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="83c45-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="83c45-127">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="83c45-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="83c45-128">使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="83c45-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="83c45-129">建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="83c45-129">Create DNS records</span></span>
<span data-ttu-id="83c45-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="83c45-130"></span></span>

<span data-ttu-id="83c45-131">您可能已經將這些元件儲存在商務用 Skype Server 環境中, 但您必須建立下列記錄, 才能讓「自動完成」工作:</span><span class="sxs-lookup"><span data-stu-id="83c45-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="83c45-132">內部 DNS 記錄可支援從貴組織的網路內部連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="83c45-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="83c45-133">外部 (或公用) DNS 記錄, 以支援從組織網路外部連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="83c45-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="83c45-134">這些記錄可以是 (主機) 名稱或 CNAME 記錄 (您不需要同時進行), 我們只會在這裡加入所有專案的步驟。</span><span class="sxs-lookup"><span data-stu-id="83c45-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="83c45-135">建立內部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="83c45-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="83c45-136">登入您網路中擁有**Domain Admins**群組或**DnsAdmins**群組成員的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="83c45-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="83c45-137">按一下 [**開始**], 選擇 [**管理工具**] (如果不是 [開始] 功能表中的選項, 您可能需要進行**搜尋**), 然後按一下 [ **dns** ] 以開啟 [dns 管理] 管理單元。</span><span class="sxs-lookup"><span data-stu-id="83c45-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="83c45-138">在主控台視窗的左窗格中, 您需要移至商務用 Skype Server 前端伺服器所在的網域, 然後展開其中的**正向查閱區域**。</span><span class="sxs-lookup"><span data-stu-id="83c45-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="83c45-139">請花點時間來查看下列哪一項:</span><span class="sxs-lookup"><span data-stu-id="83c45-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="83c45-140">前端伺服器的任何主機 A 或 AAAA 記錄 (標準或企業) 或頂層端池 (s)。</span><span class="sxs-lookup"><span data-stu-id="83c45-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="83c45-141">主管或主管池的任何主機 A 或 AAAA 記錄 (您在部署中可能會有的選用配置)。</span><span class="sxs-lookup"><span data-stu-id="83c45-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="83c45-142">一旦您記下這個名稱, 請以滑鼠右鍵按一下您的 SIP 功能變數名稱, 然後從功能表選擇 [**新增別名 (CNAME)** ]。</span><span class="sxs-lookup"><span data-stu-id="83c45-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="83c45-143">在 [**別名名稱**] 文字方塊中, 輸入您的主機名稱 lyncdiscoverinternal, 以取得內部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="83c45-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="83c45-144">在**完整的功能變數名稱 (目標主機的 FQDN**) 中, 您必須輸入或流覽至您的前臺主機池 (或單一前端伺服器, 或主管池或控制器) 的內部 WEB 服務 FQDN (在上述步驟4中發現)。</span><span class="sxs-lookup"><span data-stu-id="83c45-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="83c45-145">輸入時, 按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="83c45-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="83c45-146">您必須在 [轉寄查閱區域] 中針對商務用 Skype Server 環境中支援的每個 SIP 網域, 建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="83c45-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="83c45-147">建立外部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="83c45-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="83c45-148">這些步驟是一般的, 因為我們無法判斷您可能正在使用哪個公用 DNS 提供者, 但我們仍想協助您解決。請登入您的公用 DNS 提供者, 並將能夠在該處建立新的 DNS 記錄的帳戶。</span><span class="sxs-lookup"><span data-stu-id="83c45-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="83c45-149">在這個時間點, 商務用 Skype Server 應該已經存在一個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="83c45-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="83c45-150">展開此 SIP 網域的**正向查閱區域**, 或以其他方式開啟它。</span><span class="sxs-lookup"><span data-stu-id="83c45-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="83c45-151">請花點時間來查看下列哪一項:</span><span class="sxs-lookup"><span data-stu-id="83c45-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="83c45-152">前端伺服器的任何主機 A 或 AAAA 記錄 (標準或企業) 或頂層端池 (s)。</span><span class="sxs-lookup"><span data-stu-id="83c45-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="83c45-153">主管或主管池的任何主機 A 或 AAAA 記錄 (您在部署中可能會有的選用配置)。</span><span class="sxs-lookup"><span data-stu-id="83c45-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="83c45-154">取得該資訊之後, 您就應該能夠選取建立**新別名 (CNAME)** 的選項。</span><span class="sxs-lookup"><span data-stu-id="83c45-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="83c45-155">現在, 您應該可以輸入**別名**, 您必須在這裡輸入 lyncdiscover, 以取得外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="83c45-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="83c45-156">接下來, 應該有一個區域可在**目標主機的 FQDN**中輸入, 這將必須是您的前端池 (或單一前端伺服器, 或主管池或控制器) 的 fqdn (在上述步驟3中發現)。</span><span class="sxs-lookup"><span data-stu-id="83c45-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="83c45-157">您可能需要儲存在這裡, 或者, 如果您需要在商務用 Skype Server 環境中的每個 SIP 網域的轉寄查閱區域中建立其他 CNAME 記錄, 您應該這樣做, 但準備好後, 請儲存您的工作。</span><span class="sxs-lookup"><span data-stu-id="83c45-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="83c45-158">建立內部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="83c45-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="83c45-159">登入您網路中擁有**Domain Admins**群組或**DnsAdmins**群組成員的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="83c45-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="83c45-160">按一下 [**開始**], 選擇 [**管理工具**] (如果不是 [開始] 功能表中的選項, 您可能需要進行**搜尋**), 然後按一下 [ **dns** ] 以開啟 [dns 管理] 管理單元。</span><span class="sxs-lookup"><span data-stu-id="83c45-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="83c45-161">在主控台視窗的左窗格中, 您需要移至商務用 Skype Server 前端伺服器所在的網域, 然後展開其中的**正向查閱區域**。</span><span class="sxs-lookup"><span data-stu-id="83c45-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="83c45-162">請花點時間來查看下列哪一項:</span><span class="sxs-lookup"><span data-stu-id="83c45-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="83c45-163">前端伺服器的任何主機 A 或 AAAA 記錄 (標準或企業) 或頂層端池 (s)。</span><span class="sxs-lookup"><span data-stu-id="83c45-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="83c45-164">主管或主管池的任何主機 A 或 AAAA 記錄 (您在部署中可能會有的選用配置)。</span><span class="sxs-lookup"><span data-stu-id="83c45-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="83c45-165">一旦您記下這個名稱, 請以滑鼠右鍵按一下您的 SIP 功能變數名稱, 然後從功能表選擇 [**新增主機 (A 或 AAAA)** ]。</span><span class="sxs-lookup"><span data-stu-id="83c45-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="83c45-166">在 [**名稱**] 文字方塊中, 為您的主機名稱輸入 lyncdiscoverinternal, 以取得內部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="83c45-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="83c45-167">在 [ **IP 位址**] 文字方塊中, 輸入您的 [前端] 池 (或 [單一前端伺服器] 或 [控制器池]) 的內部 WEB 服務 IP 位址 (在上述步驟4中標出)。</span><span class="sxs-lookup"><span data-stu-id="83c45-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="83c45-168">完成後, 請按一下 [**新增主機**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="83c45-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="83c45-169">您需要針對商務用 Skype Server 環境中支援的每個 SIP 域, 在轉寄查閱區域中建立新的自動探索 A 或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="83c45-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="83c45-170">若要這麼做, 請視需要重複步驟6-8。</span><span class="sxs-lookup"><span data-stu-id="83c45-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="83c45-171">完成後, 請按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="83c45-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="83c45-172">建立外部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="83c45-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="83c45-173">這些步驟是一般的, 因為我們無法判斷您可能正在使用哪個公用 DNS 提供者, 但我們仍想協助您解決。請登入您的公用 DNS 提供者, 並將能夠在該處建立新的 DNS 記錄的帳戶。</span><span class="sxs-lookup"><span data-stu-id="83c45-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="83c45-174">在這個時間點, 商務用 Skype Server 應該已經存在一個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="83c45-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="83c45-175">展開此 SIP 網域的**正向查閱區域**, 或以其他方式開啟它。</span><span class="sxs-lookup"><span data-stu-id="83c45-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="83c45-176">請花點時間來查看下列哪一項:</span><span class="sxs-lookup"><span data-stu-id="83c45-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="83c45-177">前端伺服器的任何主機 A 或 AAAA 記錄 (標準或企業) 或頂層端池 (s)。</span><span class="sxs-lookup"><span data-stu-id="83c45-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="83c45-178">主管或主管池的任何主機 A 或 AAAA 記錄 (您在部署中可能會有的選用配置)。</span><span class="sxs-lookup"><span data-stu-id="83c45-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="83c45-179">取得該資訊之後, 您就應該能夠選取建立**新主機 a 或 AAAA**的選項。</span><span class="sxs-lookup"><span data-stu-id="83c45-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="83c45-180">現在, 您應該可以輸入**名稱**, 您必須在這裡輸入 lyncdiscover, 以取得外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="83c45-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="83c45-181">接下來, 您必須在**Ip Addresss**中輸入一個區域, 才能在上述步驟3中找到您的前端池 (或單一前端伺服器, 或主管池或控制器) 的 IP。</span><span class="sxs-lookup"><span data-stu-id="83c45-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="83c45-182">您可能需要儲存在這裡, 或者, 如果您需要在每個 SIP 網域的轉寄查閱區域中, 為您的商務用 Skype Server 環境建立額外的 A 或 AAAA 記錄, 您應該這樣做, 但在您準備好後, 儲存您的工作。</span><span class="sxs-lookup"><span data-stu-id="83c45-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="83c45-183">修改憑證</span><span class="sxs-lookup"><span data-stu-id="83c45-183">Modify certificates</span></span>
<span data-ttu-id="83c45-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="83c45-184"></span></span>

<span data-ttu-id="83c45-185">如果您有關于證書規劃的問題, 我們已在[針對商務用 Skype Server 文章的行動方案](../plan-your-deployment/mobility.md)中記錄這些問題。</span><span class="sxs-lookup"><span data-stu-id="83c45-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="83c45-186">審查完畢之後, 我們會逐步引導您完成下列作業:</span><span class="sxs-lookup"><span data-stu-id="83c45-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="83c45-187">我需要新的憑證嗎？</span><span class="sxs-lookup"><span data-stu-id="83c45-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="83c45-188">從您的憑證授權單位 (CA) 要求新的憑證。</span><span class="sxs-lookup"><span data-stu-id="83c45-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="83c45-189">使用 PowerShell 的替換更新您的就地憑證。</span><span class="sxs-lookup"><span data-stu-id="83c45-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="83c45-190">使用 Microsoft 管理主控台 (MMC) 中的 [憑證] 管理單元檢查憑證。</span><span class="sxs-lookup"><span data-stu-id="83c45-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="83c45-191">我需要新的憑證嗎？</span><span class="sxs-lookup"><span data-stu-id="83c45-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="83c45-192">首先, 您可能需要檢查並查看有哪些憑證, 以及他們是否擁有您所需的專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="83c45-193">若要這樣做, 您必須使用本機系統管理員帳戶登入商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="83c45-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="83c45-194">此帳戶也可能需要擁有頒發憑證授權單位 (CA) 的許可權, 才能執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="83c45-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="83c45-195">開啟商務用 Skype Server 管理命令介面 (如果您沒有將它釘選到 [開始] 功能表或工作列), 您可以使用 [搜尋] 來尋找它。</span><span class="sxs-lookup"><span data-stu-id="83c45-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="83c45-196">在您嘗試新增已更新的憑證之前, 您必須先瞭解已指派的憑證才是必要的。</span><span class="sxs-lookup"><span data-stu-id="83c45-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="83c45-197">在命令中, 輸入:</span><span class="sxs-lookup"><span data-stu-id="83c45-197">So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="83c45-198">步驟3中的資訊將對您而言是唯一的。</span><span class="sxs-lookup"><span data-stu-id="83c45-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="83c45-199">您需要查看它, 以判斷您是否有已指派給多個專案的單一憑證, 或是否有指派給其他需要不同元件的憑證。</span><span class="sxs-lookup"><span data-stu-id="83c45-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="83c45-200">**Use**參數會告知您證書的使用方式, 而**指紋**參數會告知您是否為相同的憑證或多個證書。</span><span class="sxs-lookup"><span data-stu-id="83c45-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="83c45-201">如果您在 [規劃] 區段中有建議的 SAN 專案, 您就大功告成了。</span><span class="sxs-lookup"><span data-stu-id="83c45-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="83c45-202">如果不是, 您必須從您的憑證頒發機構要求新的憑證或多個憑證 (視您的設定而定)。</span><span class="sxs-lookup"><span data-stu-id="83c45-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="83c45-203">從您的憑證頒發機構 (CA) 要求新憑證或憑證</span><span class="sxs-lookup"><span data-stu-id="83c45-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="83c45-204">在您檢查並查看您擁有哪些 SAN 專案之後, 您會知道您有**單一憑證**(透過上述步驟檢查之後), 而且您已學到您沒有所有所需的專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="83c45-205">需要對您的 CA 進行新的憑證要求。</span><span class="sxs-lookup"><span data-stu-id="83c45-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="83c45-206">開啟您的商務用 Skype Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="83c45-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="83c45-207">針對遺失的自動探索服務 SAN (將-Ca 參數取代為您自己的憑證授權單位路徑):</span><span class="sxs-lookup"><span data-stu-id="83c45-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="83c45-208">現在, 如果您有多個 SIP 網域, 就無法使用 AllSipDomain 參數, 如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="83c45-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="83c45-209">您必須改為使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="83c45-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="83c45-210">當您使用 DomainName 參數時, 您必須為 lyncdiscoverinternal 和 lyncdiscover 記錄定義 FQDN。</span><span class="sxs-lookup"><span data-stu-id="83c45-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="83c45-211">例如, 將-Ca 參數取代為您自己的憑證授權單位路徑):</span><span class="sxs-lookup"><span data-stu-id="83c45-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="83c45-212">或者, 在您檢查並查看您擁有哪些 SAN 專案之後, 您發現您有**多個憑證**沒有您所需的所有專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="83c45-213">需要對您的 CA 進行新的憑證要求。</span><span class="sxs-lookup"><span data-stu-id="83c45-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="83c45-214">開啟您的商務用 Skype Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="83c45-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="83c45-215">針對遺失的自動探索服務 SAN (將-Ca 參數取代為您自己的憑證授權單位路徑):</span><span class="sxs-lookup"><span data-stu-id="83c45-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="83c45-216">現在, 如果您有多個 SIP 網域, 就無法使用 AllSipDomain 參數, 如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="83c45-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="83c45-217">您必須改為使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="83c45-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="83c45-218">當您使用 DomainName 參數時, 您必須為 lyncdiscoverinternal 和 lyncdiscover 記錄定義 FQDN。</span><span class="sxs-lookup"><span data-stu-id="83c45-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="83c45-219">範例就是 (將-Ca 參數取代為您自己的憑證授權單位路徑):</span><span class="sxs-lookup"><span data-stu-id="83c45-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="83c45-220">一旦 CA 產生新憑證之後, 您就必須指派給他們。</span><span class="sxs-lookup"><span data-stu-id="83c45-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="83c45-221">使用商務用 Skype Server Management 命令介面指派憑證</span><span class="sxs-lookup"><span data-stu-id="83c45-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="83c45-222">您必須執行下列**其中一**項, 才能視您在上述 [我需要新認證] 區段中找到的內容而定。</span><span class="sxs-lookup"><span data-stu-id="83c45-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="83c45-223">如果您的所有專案都有單一憑證 (指紋完全相同), 則必須執行以下動作:</span><span class="sxs-lookup"><span data-stu-id="83c45-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="83c45-224">如果您有不同的憑證 (指紋全都不一樣), 請改為執行此動作:</span><span class="sxs-lookup"><span data-stu-id="83c45-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="83c45-225">在 Microsoft 管理主控台 (MMC) 中查看憑證</span><span class="sxs-lookup"><span data-stu-id="83c45-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="83c45-226">您可以選擇使用 MMC 的 [憑證] 管理單元來查看您的憑證。</span><span class="sxs-lookup"><span data-stu-id="83c45-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="83c45-227">只要在搜尋中輸入 MMC, 就應該將它作為應用程式選項彈出。</span><span class="sxs-lookup"><span data-stu-id="83c45-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="83c45-228">若要新增 [憑證] 管理單元, 您需要按一下 [ \*\*\*\* 檔案], 然後按一下 [**新增/移除管理單元 ...** ]。(或鍵盤快速鍵**Ctrl + M**也會起作用)。</span><span class="sxs-lookup"><span data-stu-id="83c45-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="83c45-229">[**憑證**] 是左窗格中的一個選項, 選取它, 然後在快捷視窗中選取 [**電腦帳戶**], 然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="83c45-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="83c45-230">在快顯視窗中, 您的所有可能性都是在您需要查看之憑證的電腦上執行此動作, 所以請在**本機電腦**上保留選取狀態 (如果有的話)。</span><span class="sxs-lookup"><span data-stu-id="83c45-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="83c45-231">如果您是在遠端電腦上工作, 請將選項按鈕變更為**另一部電腦**, 然後輸入該電腦的 FQDN, 或使用 **[流覽]** 按鈕, 透過廣告搜尋該電腦。</span><span class="sxs-lookup"><span data-stu-id="83c45-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="83c45-232">選取電腦之後, 您必須在 [就緒] 後按一下 **[完成]** , 然後按一下 **[確定]** , 將該管理單元新增至 MMC。</span><span class="sxs-lookup"><span data-stu-id="83c45-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="83c45-233">展開 MMC 左側窗格中的 [**憑證**] 區段。</span><span class="sxs-lookup"><span data-stu-id="83c45-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="83c45-234">同時展開 [**個人**] 資料夾, 然後選取 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="83c45-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="83c45-235">這可讓您查看此存放區中的憑證。</span><span class="sxs-lookup"><span data-stu-id="83c45-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="83c45-236">您必須找出您想要查看的憑證, 然後以滑鼠右鍵按一下它, 然後選擇 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="83c45-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="83c45-237">如何知道這是哪一種證書？</span><span class="sxs-lookup"><span data-stu-id="83c45-237">How do you know what certificate this is?</span></span> <span data-ttu-id="83c45-238">它應該是指派給您伺服器陣列所有專案的單一憑證, 或者您可能會有多個憑證的不同專案 (例如預設、內部 Web 服務等)。在這種情況下, 您可能需要查看多個憑證。</span><span class="sxs-lookup"><span data-stu-id="83c45-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="83c45-239">多個憑證將擁有相同的指紋。</span><span class="sxs-lookup"><span data-stu-id="83c45-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="83c45-240">移至 [**憑證**] 視圖之後, 請選擇 [**詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="83c45-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="83c45-241">這可讓您在選取 [ **subject**] 時查看憑證受領人名稱, 並顯示指派的主體名稱和相關聯的屬性。</span><span class="sxs-lookup"><span data-stu-id="83c45-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="83c45-242">您也需要檢查 [Subject]**替換名稱**專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="83c45-243">您會發現下列一或多個專案:</span><span class="sxs-lookup"><span data-stu-id="83c45-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="83c45-244">此池的 [池名稱], 如果這不是「池」, 則是單一伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="83c45-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="83c45-245">證書指派的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="83c45-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="83c45-246">簡單的 URL 記錄, 通常是符合和撥入。</span><span class="sxs-lookup"><span data-stu-id="83c45-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="83c45-247">Web 服務內部和 Web 服務外部名稱 (例如 webpool01.contoso.net、webpool01.contoso.com), 根據拓撲建立器和跨 ridden Web 服務選擇中的選擇進行。</span><span class="sxs-lookup"><span data-stu-id="83c45-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="83c45-248">如果已指定, 則 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄。</span><span class="sxs-lookup"><span data-stu-id="83c45-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="83c45-249">如果您有多個指派的憑證, 您必須檢查多個憑證 (請選取上述記事)。</span><span class="sxs-lookup"><span data-stu-id="83c45-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="83c45-250">因此, 如果您找到 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄, 您已經設定好了。</span><span class="sxs-lookup"><span data-stu-id="83c45-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="83c45-251">您可以關閉 MMC。</span><span class="sxs-lookup"><span data-stu-id="83c45-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="83c45-252">如果未指派, 您必須建立新的憑證要求 (請見上述說明), 或者您必須安裝其後續授權 (我們建議您這麼做的 PowerShell 如下)。</span><span class="sxs-lookup"><span data-stu-id="83c45-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="83c45-253">設定反向 proxy</span><span class="sxs-lookup"><span data-stu-id="83c45-253">Configure the reverse proxy</span></span>
<span data-ttu-id="83c45-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="83c45-254"></span></span>

<span data-ttu-id="83c45-255">下列步驟並不是完全遵循的步驟。</span><span class="sxs-lookup"><span data-stu-id="83c45-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="83c45-256">這是因為在早期版本的產品中, 我們已逐步說明如何設定威脅管理閘道 (TMG), 如果您沒有使用這項功能, 您就必須從該處處理您自己的版本。</span><span class="sxs-lookup"><span data-stu-id="83c45-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="83c45-257">在 Microsoft 不會再將 TMG 提供給產品, 如果您仍需要進行設定, 您可以查看[Lync Server 2013 的步驟](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="83c45-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="83c45-258">但是, 下列資訊的預期更常見, 即使沒有任何辦法, 我們也可以針對每個反向 proxy 提供特定的逐步逐步步驟。</span><span class="sxs-lookup"><span data-stu-id="83c45-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="83c45-259">我們主要要考慮兩件事:</span><span class="sxs-lookup"><span data-stu-id="83c45-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="83c45-260">您是否要在 HTTPS 上使用初始自動探索要求 (我們建議這麼做)？</span><span class="sxs-lookup"><span data-stu-id="83c45-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="83c45-261">如果您有 web 發佈規則, 您必須進行修改。</span><span class="sxs-lookup"><span data-stu-id="83c45-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="83c45-262">如果您還沒有網路發佈規則, 您需要建立它。</span><span class="sxs-lookup"><span data-stu-id="83c45-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="83c45-263">如果您是通過 HTTP 進行初始自動探索要求, 則您也需要建立或修改該規則。</span><span class="sxs-lookup"><span data-stu-id="83c45-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="83c45-264">**重要**Proxy 超時值是一個數位, 不會因部署而異。</span><span class="sxs-lookup"><span data-stu-id="83c45-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="83c45-265">您應該監視您的部署並修改用戶端最佳體驗的價值。</span><span class="sxs-lookup"><span data-stu-id="83c45-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="83c45-266">您可以將值設為 [低] 與200。</span><span class="sxs-lookup"><span data-stu-id="83c45-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="83c45-267">如果您是在您的環境中支援 Lync 行動用戶端, 則應該將此值設定為 960, 以允許來自 Office 365 的推播通知超時, 其超時值為900。</span><span class="sxs-lookup"><span data-stu-id="83c45-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="83c45-268">您很可能需要增加超時值, 以避免用戶端在值太低時中斷連線, 或在用戶端中斷連線後, 如果透過 proxy 連線, 則將數位減少 (長時間)。</span><span class="sxs-lookup"><span data-stu-id="83c45-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="83c45-269">針對您的環境, 監視及設定一般的方式是判斷此值適當設定的唯一正確方法。</span><span class="sxs-lookup"><span data-stu-id="83c45-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="83c45-270">修改外部自動探索 SAN 與 URL 的現有 web 發佈規則</span><span class="sxs-lookup"><span data-stu-id="83c45-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="83c45-271">開啟您的反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="83c45-272">您必須找出您的 web 發佈規則, 然後選擇 [編輯] 選項 (它可能位於功能表或索引標籤上, 視您的反向 proxy 設定而定)。</span><span class="sxs-lookup"><span data-stu-id="83c45-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="83c45-273">應該有一個區域, 指出該 web 發佈規則的套用位置。</span><span class="sxs-lookup"><span data-stu-id="83c45-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="83c45-274">您需要針對內送網站或網站的要求修改這個規則。</span><span class="sxs-lookup"><span data-stu-id="83c45-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="83c45-275">您要新增新\*\*\*\* 的專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="83c45-276">輸入自動探索網站的名稱 (我們將使用的範例是 lyncdiscover.contoso.com), 然後根據您的反向 proxy 的格式, 按一下 **[確定] 或 [** **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="83c45-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="83c45-277">您可能有新的憑證, 且其中有 [自動探索] SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="83c45-278">還需要安裝, 並根據您的反向 proxy 設定來設定使用。</span><span class="sxs-lookup"><span data-stu-id="83c45-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="83c45-279">完成設定後, 請務必儲存所有專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="83c45-280">如果您的反向 proxy 擁有**測試**功能, 請使用它, 以確保一切正常運作。</span><span class="sxs-lookup"><span data-stu-id="83c45-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="83c45-281">現在, 如果您的環境中有控制器或主管池, 您可能需要重複這些步驟 (這會表示您有第二個規則)。</span><span class="sxs-lookup"><span data-stu-id="83c45-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="83c45-282">建立外部自動探索 URL 的 web 發佈規則</span><span class="sxs-lookup"><span data-stu-id="83c45-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="83c45-283">開啟您的反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="83c45-284">您需要在介面中尋找您建立 web 發佈規則的位置, 然後選擇 [**新增**] 或 [**建立**] 選項 (可能位於功能表或索引標籤上, 視您的反向 proxy 設定而定)。</span><span class="sxs-lookup"><span data-stu-id="83c45-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="83c45-285">您正在尋找建立新的 web 發佈規則的選項。</span><span class="sxs-lookup"><span data-stu-id="83c45-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="83c45-286">通常, 您必須輸入下列資訊:</span><span class="sxs-lookup"><span data-stu-id="83c45-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="83c45-287">**Name (名稱**): 規則的名稱</span><span class="sxs-lookup"><span data-stu-id="83c45-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="83c45-288">**規則動作**: 在這種情況下, 它是一個**允許**規則, 您可以透過您的反向 proxy 來傳送某個專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="83c45-289">您所選擇的**發佈**規則或選項就是**單一網站或負載平衡器**。</span><span class="sxs-lookup"><span data-stu-id="83c45-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="83c45-290">這必須是外部存取的**SSL** , 請選擇該選項。</span><span class="sxs-lookup"><span data-stu-id="83c45-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="83c45-291">您必須發佈**內部發佈**的路徑, 然後在您的前臺端池的負載平衡器 (或控制器池的負載平衡器 (如果有的話) 的 fqdn) 中輸入外部 Web 服務的 fqdn (如果有的話), 就會 sfb_ 範例。pool01。</span><span class="sxs-lookup"><span data-stu-id="83c45-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="83c45-292">您應該輸入\*\* / \*\*\* 作為您要發佈的路徑, 但也必須**轉寄原始主機標頭**。</span><span class="sxs-lookup"><span data-stu-id="83c45-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="83c45-293">系統會提供**公用或外部名稱**詳細資料或資訊的選項。</span><span class="sxs-lookup"><span data-stu-id="83c45-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="83c45-294">您可以在此輸入以下位置:</span><span class="sxs-lookup"><span data-stu-id="83c45-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="83c45-295">**接受要求**, 但它應該用於功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="83c45-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="83c45-296">在**名稱**中, 您應該輸入**lyncdiscover。**</span><span class="sxs-lookup"><span data-stu-id="83c45-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="83c45-297"><sipdomain>(這是外部自動探索服務 URL)。</span><span class="sxs-lookup"><span data-stu-id="83c45-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="83c45-298">現在, 如果您是在 [前端] 池上為 [外部 Web 服務] URL 建立規則, 您必須在您的前端池 (例如, lyncwebextpool01.contoso.com) 輸入外部 Web 服務的 FQDN (例如,)。</span><span class="sxs-lookup"><span data-stu-id="83c45-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="83c45-299">將會有一個**路徑**選項, 您必須在這裡輸入\*\* / \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83c45-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="83c45-300">您必須使用最新的公用憑證選取**SSL 監聽**程式。</span><span class="sxs-lookup"><span data-stu-id="83c45-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="83c45-301">**驗證委派**應該設定為 [**無委派**], 但**應該**允許直接用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="83c45-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="83c45-302">規則應該設定為 [**所有使用者**]。</span><span class="sxs-lookup"><span data-stu-id="83c45-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="83c45-303">這應該是建立此規則所需的所有資訊, 並可讓您繼續進行。</span><span class="sxs-lookup"><span data-stu-id="83c45-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="83c45-304">您必須確保**原始主機標頭**已轉寄。</span><span class="sxs-lookup"><span data-stu-id="83c45-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="83c45-305">**網頁伺服器**埠也必須設定, 您必須執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="83c45-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="83c45-306">**將要求重新導向至 HTTP 埠**, 埠號碼應該是**8080**。</span><span class="sxs-lookup"><span data-stu-id="83c45-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="83c45-307">**將要求重新導向至 SSL 埠**, 埠號碼應該是**4443**。</span><span class="sxs-lookup"><span data-stu-id="83c45-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="83c45-308">完成所有設定之後, 您必須儲存或套用這些專案, 然後您就會想要測試規則。</span><span class="sxs-lookup"><span data-stu-id="83c45-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="83c45-309">建立埠80的網路發佈規則 (選用)</span><span class="sxs-lookup"><span data-stu-id="83c45-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="83c45-310">開啟您的反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="83c45-311">您需要在介面中尋找您建立 web 發佈規則的位置, 然後選擇 [**新增**] 或 [**建立**] 選項 (可能位於功能表或索引標籤上, 視您的反向 proxy 設定而定)。</span><span class="sxs-lookup"><span data-stu-id="83c45-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="83c45-312">您正在尋找建立新的 web 發佈規則的選項。</span><span class="sxs-lookup"><span data-stu-id="83c45-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="83c45-313">通常, 您必須輸入下列資訊:</span><span class="sxs-lookup"><span data-stu-id="83c45-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="83c45-314">**Name (名稱**): 規則的名稱</span><span class="sxs-lookup"><span data-stu-id="83c45-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="83c45-315">**規則動作**: 在這種情況下, 它是一個**允許**規則, 您可以透過您的反向 proxy 來傳送某個專案。</span><span class="sxs-lookup"><span data-stu-id="83c45-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="83c45-316">您所選擇的**發佈**規則或選項就是**單一網站或負載平衡器**。</span><span class="sxs-lookup"><span data-stu-id="83c45-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="83c45-317">這必須是**不安全的連線才能連線到已發佈的 Web 服務器或伺服器**陣列。</span><span class="sxs-lookup"><span data-stu-id="83c45-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="83c45-318">您需要發佈**內部發佈**的路徑, 並輸入您的前臺池負載平衡器之**VIP 位址**的 FQDN, 例如, sfb_pool01 為 [contoso.]。</span><span class="sxs-lookup"><span data-stu-id="83c45-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="83c45-319">您應該輸入\*\* / \*\*\* 作為您要發佈的路徑, 但也必須**轉寄原始主機標頭**。</span><span class="sxs-lookup"><span data-stu-id="83c45-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="83c45-320">系統會提供**公用或外部名稱**詳細資料或資訊的選項。</span><span class="sxs-lookup"><span data-stu-id="83c45-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="83c45-321">您可以在此輸入以下位置:</span><span class="sxs-lookup"><span data-stu-id="83c45-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="83c45-322">**接受要求**, 但它應該用於功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="83c45-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="83c45-323">在**名稱**中, 您應該輸入**lyncdiscover。**</span><span class="sxs-lookup"><span data-stu-id="83c45-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="83c45-324"><sipdomain>(這是外部自動探索服務 URL)。</span><span class="sxs-lookup"><span data-stu-id="83c45-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="83c45-325">將會有一個**路徑**選項, 您必須在這裡輸入\*\* / \*\*\*。</span><span class="sxs-lookup"><span data-stu-id="83c45-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="83c45-326">您必須選取網頁監聽程式, 或允許您的反向 proxy 為您建立一個。</span><span class="sxs-lookup"><span data-stu-id="83c45-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="83c45-327">**驗證委派**應該設定為 [**無委派**], 但**不應**允許直接用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="83c45-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="83c45-328">規則應該設定為 [**所有使用者**]。</span><span class="sxs-lookup"><span data-stu-id="83c45-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="83c45-329">這應該是建立此規則所需的所有資訊, 並可讓您繼續進行。</span><span class="sxs-lookup"><span data-stu-id="83c45-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="83c45-330">需要設定**Web 服務器**埠, 您必須執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="83c45-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="83c45-331">**將要求重新導向至 HTTP 埠**, 埠號碼應該是**8080**。</span><span class="sxs-lookup"><span data-stu-id="83c45-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="83c45-332">**將要求重新導向至 SSL 埠**, 埠號碼應該是**4443**。</span><span class="sxs-lookup"><span data-stu-id="83c45-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="83c45-333">完成所有設定之後, 您必須儲存或套用這些專案, 然後您就會想要測試規則。</span><span class="sxs-lookup"><span data-stu-id="83c45-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="83c45-334">使用混合式部署設定自動探索以進行行動</span><span class="sxs-lookup"><span data-stu-id="83c45-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="83c45-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="83c45-335"></span></span>

<span data-ttu-id="83c45-336">商務用 Skype Server 的混合式環境是結合內部部署與 O365 環境的環境。</span><span class="sxs-lookup"><span data-stu-id="83c45-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="83c45-337">當您在混合式環境中使用商務用 Skype 伺服器時, 自動探索服務必須能夠從上述任一種環境中找出使用者。</span><span class="sxs-lookup"><span data-stu-id="83c45-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="83c45-338">若要讓行動用戶端發現使用者的位置, 必須使用新的統一資源定位器 (URL) 來設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="83c45-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="83c45-339">步驟如下:</span><span class="sxs-lookup"><span data-stu-id="83c45-339">The steps are:</span></span>
  
1. <span data-ttu-id="83c45-340">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="83c45-341">執行下列動作以取得商務用 Skype Server 環境的屬性**ProxyFQDN**值:</span><span class="sxs-lookup"><span data-stu-id="83c45-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="83c45-342">接著, 仍在 [shell] 視窗中執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="83c45-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="83c45-343">其中 [身分識別] 會以共用的 SIP 位址空間的功能變數名稱取代。</span><span class="sxs-lookup"><span data-stu-id="83c45-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="83c45-344">測試行動部署</span><span class="sxs-lookup"><span data-stu-id="83c45-344">Test your Mobility deployment</span></span>
<span data-ttu-id="83c45-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="83c45-345"></span></span>

<span data-ttu-id="83c45-346">一旦您部署商務用 Skype Server 行動服務和商務用 Skype Server 自動探索服務之後, 您就會想要執行測試事務, 以確保您的部署能正常運作。</span><span class="sxs-lookup"><span data-stu-id="83c45-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="83c45-347">您可以執行**測試 CsUcwaConference** , 以測試兩位使用者在會議中建立、加入和溝通的能力。</span><span class="sxs-lookup"><span data-stu-id="83c45-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="83c45-348">您將需要兩位使用者 (real 或 test) 及完整的認證, 才能執行這項測試。</span><span class="sxs-lookup"><span data-stu-id="83c45-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="83c45-349">此命令將適用于商務用 Skype 用戶端和 Lync Server 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="83c45-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="83c45-350">在商務用 Skype Server 2015 上的 Lync Server 2010 用戶端, 您必須執行**測試 CsMcxP2PIM**以進行測試。</span><span class="sxs-lookup"><span data-stu-id="83c45-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="83c45-351">您的 Lync Server 2010 使用者仍必須是實際的使用者, 或是預先定義的測試使用者, 您需要其密碼認證。</span><span class="sxs-lookup"><span data-stu-id="83c45-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="83c45-352">MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="83c45-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="83c45-353">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="83c45-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="83c45-354">使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="83c45-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="83c45-355">針對商務用 Skype 和 Lync 2013 行動用戶端測試會議</span><span class="sxs-lookup"><span data-stu-id="83c45-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="83c45-356">在安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的任何電腦上, 以**CsAdministrator**角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="83c45-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="83c45-357">啟動**商務用 Skype Server 管理命令**介面 (您可以在 [搜尋] 中輸入名稱, 或 [移至**所有程式**] 並加以選擇)。</span><span class="sxs-lookup"><span data-stu-id="83c45-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="83c45-358">在命令列中, 輸入:</span><span class="sxs-lookup"><span data-stu-id="83c45-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="83c45-359">您也可以在腳本中設定認證, 並將其傳遞給 test Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="83c45-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="83c45-360">我們有一個範例, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="83c45-360">We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="83c45-361">測試 Lync 2010 行動用戶端的會議</span><span class="sxs-lookup"><span data-stu-id="83c45-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="83c45-362">MCX (行動服務) 對舊版行動用戶端的支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="83c45-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="83c45-363">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API (UCWA) 來支援立即訊息 (IM)、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="83c45-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="83c45-364">使用 MCX 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="83c45-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="83c45-365">在安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的任何電腦上, 以**CsAdministrator**角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="83c45-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="83c45-366">啟動**商務用 Skype Server 管理命令**介面 (您可以在 [搜尋] 中輸入名稱, 或 [移至**所有程式**] 並加以選擇)。</span><span class="sxs-lookup"><span data-stu-id="83c45-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="83c45-367">在命令列中, 輸入:</span><span class="sxs-lookup"><span data-stu-id="83c45-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="83c45-368">您也可以在腳本中設定認證, 並將其傳遞給 test Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="83c45-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="83c45-369">我們有一個範例, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="83c45-369">We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="83c45-370">若要進一步回顧命令程式, 您可以查看 CsUcwaConference 和[Test CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)的[測試](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="83c45-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="83c45-371">針對推播通知進行設定</span><span class="sxs-lookup"><span data-stu-id="83c45-371">Configure for push notifications</span></span>
<span data-ttu-id="83c45-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="83c45-372"></span></span>

<span data-ttu-id="83c45-373">您可以傳送徽章、圖示或通知等形式的推播通知, 即使 Skype 或 Lync app 不在使用中, 也能傳送到行動裝置。</span><span class="sxs-lookup"><span data-stu-id="83c45-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="83c45-374">但什麼是推播通知？</span><span class="sxs-lookup"><span data-stu-id="83c45-374">But what are push notifications?</span></span> <span data-ttu-id="83c45-375">它們是事件警示, 例如新的或未接的 IM 邀請, 或接收到的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="83c45-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="83c45-376">商務用 Skype Server 行動服務將這些通知傳送到雲端型 Skype for business Server 推播通知服務, 然後將通知傳送到 Windows Phone 使用者的 Microsoft 推播通知服務 (MSNS)。</span><span class="sxs-lookup"><span data-stu-id="83c45-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="83c45-377">此功能不會在 Lync Server 2013 中保持不變, 但如果您有商務用 Skype 伺服器, 您會想要執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="83c45-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="83c45-378">針對商務用 Skype Server Edge 伺服器, 新增新的主機服務提供者、Microsoft 商務用 Skype Online, 然後設定貴組織與商務用 Skype Online 之間的託管提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="83c45-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="83c45-379">執行**CsPushNotificationConfiguration** Cmdlet 來啟用推播通知。</span><span class="sxs-lookup"><span data-stu-id="83c45-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="83c45-380">依預設, 推播通知會關閉。</span><span class="sxs-lookup"><span data-stu-id="83c45-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="83c45-381">測試您的同盟設定和推播通知。</span><span class="sxs-lookup"><span data-stu-id="83c45-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="83c45-382">設定您的商務用 Skype Edge 伺服器以取得推播通知</span><span class="sxs-lookup"><span data-stu-id="83c45-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="83c45-383">[登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。</span><span class="sxs-lookup"><span data-stu-id="83c45-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="83c45-384">啟動**商務用 Skype Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="83c45-385">新增商務用 Skype Server online 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="83c45-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="83c45-386">例如:</span><span class="sxs-lookup"><span data-stu-id="83c45-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="83c45-387">您不能有一個以上的同盟關聯與單一主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="83c45-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="83c45-388">因此, 如果您已設定與 sipfed.online.lync.com 有同盟關聯的主機服務提供者, 請不要為它新增另一個主機服務提供者, 即使主機提供者的身分識別是 SkypeOnline 以外的其他。</span><span class="sxs-lookup"><span data-stu-id="83c45-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="83c45-389">在您的組織與商務用 Skype Online 的 [推播通知服務] 中設定託管提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="83c45-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="83c45-390">在命令列中, 您必須輸入:</span><span class="sxs-lookup"><span data-stu-id="83c45-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="83c45-391">啟用推播通知</span><span class="sxs-lookup"><span data-stu-id="83c45-391">Enable push notifications</span></span>

1. <span data-ttu-id="83c45-392">[登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。</span><span class="sxs-lookup"><span data-stu-id="83c45-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="83c45-393">啟動**商務用 Skype Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="83c45-394">啟用推播通知:</span><span class="sxs-lookup"><span data-stu-id="83c45-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="83c45-395">啟用同盟:</span><span class="sxs-lookup"><span data-stu-id="83c45-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="83c45-396">測試同盟與推播通知</span><span class="sxs-lookup"><span data-stu-id="83c45-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="83c45-397">[登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。</span><span class="sxs-lookup"><span data-stu-id="83c45-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="83c45-398">啟動**商務用 Skype Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="83c45-399">測試同盟設定:</span><span class="sxs-lookup"><span data-stu-id="83c45-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="83c45-400">例如:</span><span class="sxs-lookup"><span data-stu-id="83c45-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="83c45-401">測試推播通知:</span><span class="sxs-lookup"><span data-stu-id="83c45-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="83c45-402">例如:</span><span class="sxs-lookup"><span data-stu-id="83c45-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="83c45-403">設定行動原則</span><span class="sxs-lookup"><span data-stu-id="83c45-403">Configure Mobility policy</span></span>
<span data-ttu-id="83c45-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="83c45-404"></span></span>

<span data-ttu-id="83c45-405">您可以使用商務用 Skype 伺服器來決定誰可以使用行動服務、透過公司通話、透過 IP (VoIP) 或影片撥打電話, 以及 VoIP 或視頻是否需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="83c45-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="83c45-406">[透過公司通話] 可讓行動使用者在撥打電話和接聽電話時, 使用公司電話號碼, 而不是行動電話號碼。</span><span class="sxs-lookup"><span data-stu-id="83c45-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="83c45-407">該行另一端的人員不會看到行動使用者的手機號碼, 而是讓行動使用者避免撥出電話費。</span><span class="sxs-lookup"><span data-stu-id="83c45-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="83c45-408">當您設定 VoIP 和影片時, 使用者可以進行 VoIP 通話及進行音訊。</span><span class="sxs-lookup"><span data-stu-id="83c45-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="83c45-409">WiFi 使用的設定會決定是否需要使用者的行動裝置, 才能透過行動資料網路使用 WiFi 網路。</span><span class="sxs-lookup"><span data-stu-id="83c45-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="83c45-410">行動性、透過公司通話, 以及 VoIP 及視頻功能預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="83c45-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="83c45-411">已停用 [VoIP] 和 [影片] 的 [需要 WiFi] 設定。</span><span class="sxs-lookup"><span data-stu-id="83c45-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="83c45-412">系統管理員能夠變更 (全域、依網站或使用者)。</span><span class="sxs-lookup"><span data-stu-id="83c45-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="83c45-413">若要能夠使用行動功能及透過公司通話, 使用者必須:</span><span class="sxs-lookup"><span data-stu-id="83c45-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="83c45-414">針對商務用 Skype Server 啟用</span><span class="sxs-lookup"><span data-stu-id="83c45-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="83c45-415">已啟用企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="83c45-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="83c45-416">指派 [ **EnableMobility** ] 選項設定為**True**的行動原則。</span><span class="sxs-lookup"><span data-stu-id="83c45-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="83c45-417">若要讓使用者能夠透過工作使用通話, 他們也必須:</span><span class="sxs-lookup"><span data-stu-id="83c45-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="83c45-418">已指派已選取 [**啟用同時撥打電話**] 選項的語音原則。</span><span class="sxs-lookup"><span data-stu-id="83c45-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="83c45-419">已指派**EnableOutsideVoice**設定為**True**的行動原則。</span><span class="sxs-lookup"><span data-stu-id="83c45-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="83c45-420">未啟用企業語音的使用者可以使用行動裝置來撥打 Skype VoIP 通話, 或在行動裝置上使用 [按一下以加入] 連結來加入會議 (如果已針對其相關的語音原則設定適當的選項)且.</span><span class="sxs-lookup"><span data-stu-id="83c45-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="83c45-421">規劃主題中有更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="83c45-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="83c45-422">修改全域行動原則</span><span class="sxs-lookup"><span data-stu-id="83c45-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="83c45-423">[登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。</span><span class="sxs-lookup"><span data-stu-id="83c45-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="83c45-424">啟動**商務用 Skype Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="83c45-425">輸入以下內容, 即可關閉行動及透過工作全域通話的存取權:</span><span class="sxs-lookup"><span data-stu-id="83c45-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="83c45-426">您可以透過工作關閉通話, 而不需關閉行動存取權。</span><span class="sxs-lookup"><span data-stu-id="83c45-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="83c45-427">但是, 您也無法關閉行動, 也不需要關閉透過工作進行通話。</span><span class="sxs-lookup"><span data-stu-id="83c45-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="83c45-428">如需詳細資訊, 請參閱[CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="83c45-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="83c45-429">依網站修改行動原則</span><span class="sxs-lookup"><span data-stu-id="83c45-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="83c45-430">[登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。</span><span class="sxs-lookup"><span data-stu-id="83c45-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="83c45-431">啟動**商務用 Skype Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="83c45-432">您可以建立網站層級原則、關閉 VoIP 及影片、啟用 [IP 音訊需提供 WiFi], 以及需要 IP 視頻的 WiFi。</span><span class="sxs-lookup"><span data-stu-id="83c45-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="83c45-433">輸入</span><span class="sxs-lookup"><span data-stu-id="83c45-433">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="83c45-434">深入瞭解[新的 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="83c45-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="83c45-435">依使用者修改行動原則</span><span class="sxs-lookup"><span data-stu-id="83c45-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="83c45-436">[登入]: 帳戶是**CsAdministrator**角色的成員, 也就是安裝**商務用 Skype Server Management 命令**介面和**Ocscore**的電腦。</span><span class="sxs-lookup"><span data-stu-id="83c45-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="83c45-437">啟動**商務用 Skype Server 管理命令**介面。</span><span class="sxs-lookup"><span data-stu-id="83c45-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="83c45-438">建立使用者層級行動原則, 並透過使用者的工作關閉行動與通話。</span><span class="sxs-lookup"><span data-stu-id="83c45-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="83c45-439">輸入</span><span class="sxs-lookup"><span data-stu-id="83c45-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="83c45-440">範例資料的進一步範例:</span><span class="sxs-lookup"><span data-stu-id="83c45-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="83c45-441">您可以透過工作關閉通話, 而不需關閉行動存取權。</span><span class="sxs-lookup"><span data-stu-id="83c45-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="83c45-442">但是, 您也無法關閉行動, 也不需要關閉透過工作進行通話。</span><span class="sxs-lookup"><span data-stu-id="83c45-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

