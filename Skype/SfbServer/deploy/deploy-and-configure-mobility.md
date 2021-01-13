---
title: 為商務用 Skype Server 部署及設定行動性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文將引導您完成設定現有商務用 Skype Server 安裝的步驟，以使用行動性服務，讓行動裝置能夠利用商務用 Skype 伺服器行動功能。
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820893"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="2b5fd-103">為商務用 Skype Server 部署及設定行動性</span><span class="sxs-lookup"><span data-stu-id="2b5fd-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="2b5fd-104">本文將引導您完成設定現有商務用 Skype Server 安裝的步驟，以使用行動性服務，讓行動裝置能夠利用商務用 Skype 伺服器行動功能。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="2b5fd-105">已回顧 [商務用 Skype server 文章行動方案的計畫](../plan-your-deployment/mobility.md) ，您應該準備好繼續執行下列步驟，以將行動性部署到商務用 skype 伺服器環境中。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="2b5fd-106">步驟如下 (，我們會在此表格中包含許可權清單) ：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="2b5fd-107">**階段**</span><span class="sxs-lookup"><span data-stu-id="2b5fd-107">**Phase**</span></span>|<span data-ttu-id="2b5fd-108">**權限**</span><span class="sxs-lookup"><span data-stu-id="2b5fd-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="2b5fd-109">建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2b5fd-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="2b5fd-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="2b5fd-110">Domain Admins</span></span>  <br/> <span data-ttu-id="2b5fd-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="2b5fd-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="2b5fd-112">修改憑證</span><span class="sxs-lookup"><span data-stu-id="2b5fd-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="2b5fd-113">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="2b5fd-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="2b5fd-114">設定反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="2b5fd-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="2b5fd-115">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="2b5fd-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="2b5fd-116">設定具有混合式部署行動的自動探索</span><span class="sxs-lookup"><span data-stu-id="2b5fd-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="2b5fd-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="2b5fd-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="2b5fd-118">測試行動性部署</span><span class="sxs-lookup"><span data-stu-id="2b5fd-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="2b5fd-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b5fd-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="2b5fd-120">設定推入通知</span><span class="sxs-lookup"><span data-stu-id="2b5fd-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="2b5fd-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b5fd-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="2b5fd-122">設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="2b5fd-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="2b5fd-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b5fd-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="2b5fd-124">下列各節包含假設您已閱讀規劃主題的步驟。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="2b5fd-125">如果有任何混淆，請隨意查看資訊。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="2b5fd-126">MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="2b5fd-127">所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="2b5fd-128">具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="2b5fd-129">建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="2b5fd-129">Create DNS records</span></span>
<span data-ttu-id="2b5fd-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="2b5fd-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="2b5fd-131">您可能已經擁有商務用 Skype Server 環境的一部分，但是您必須建立下列記錄，才能讓「自動探索」運作：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="2b5fd-132">內部 DNS 記錄，以支援從組織網路內部連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="2b5fd-133">外部 (或公開) DNS 記錄，以支援從組織網路外部連線的行動使用者。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="2b5fd-134">這些記錄可以是 (主機) 名稱或 CNAME 記錄， (您不需要做這兩種，我們只會在這裡) 的所有步驟中包含步驟。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="2b5fd-135">建立內部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="2b5fd-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="2b5fd-136">登入您網路中的 DNS 伺服器，該伺服器是 **Domain Admins** 群組的成員，或是 **DnsAdmins** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="2b5fd-137">按一下 [ **開始**]，選擇 [系統 **管理工具** ] (您可能需要 **搜尋** 它（如果不是「開始」功能表中的選項）) ，然後按一下 [ **dns** ] 以開啟 [dns 管理] 嵌入式管理單元。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="2b5fd-138">在主控台視窗的左窗格中，您需要移至您的商務用 Skype 伺服器前端伺服器所在的網域，並展開其中的 **正向對應區域** 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="2b5fd-139">請花一點時間來查看您有下列哪一項：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="2b5fd-140">前端伺服器的任何主機 A 或 AAAA 記錄 (Standard 或 Enterprise) 或前端集區 (s) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="2b5fd-141">Director 或 Director 集區的任何主機 A 或 AAAA 記錄 (您在部署) 中的選用設定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="2b5fd-142">在您記下之後，請以滑鼠右鍵按一下 SIP 功能變數名稱，然後從功能表中選取 [ **新增別名 (CNAME)** 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="2b5fd-143">在 [ **別名名稱** ] 文字方塊中，輸入 lyncdiscoverinternal 的主機名稱，以供內部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="2b5fd-144">在 [ **目標主機的完整功能變數名稱 (FQDN**] 中，您必須輸入或流覽至前端集區的內部 WEB 服務 FQDN (或單一前端伺服器或 director) （在上述步驟4中識別）。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="2b5fd-145">輸入時，按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="2b5fd-146">您必須為商務用 Skype 伺服器環境中支援的每個 SIP 網域，在正向對應區域中建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="2b5fd-147">建立外部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="2b5fd-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="2b5fd-148">這些步驟是一般的，因為我們無法判斷可能使用的公用 DNS 提供者，但我們仍想要協助您。請使用可讓新 DNS 記錄的帳戶登入您的公用 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="2b5fd-149">在這個時間點，SIP 網域應該已存在於商務用 Skype Server 中。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="2b5fd-150">展開這個 SIP 網域的 **正向對應區域** ，或以其他方式開啟它。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="2b5fd-151">請花一點時間來查看您有下列哪一項：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="2b5fd-152">前端伺服器的任何主機 A 或 AAAA 記錄 (Standard 或 Enterprise) 或前端集區 (s) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="2b5fd-153">Director 或 Director 集區的任何主機 A 或 AAAA 記錄 (您在部署) 中的選用設定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="2b5fd-154">取得該資訊後，您就可以選取一個選項來建立 **新的別名 (CNAME)**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="2b5fd-155">現在您應該可以輸入 **別名**，您必須在這裡為外部自動探索服務 URL 輸入 lyncdiscover。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="2b5fd-156">接下來應該是一個區域，可在 **目標主機的 fqdn** 內輸入，這必須是前端集區的 FQDN (或單一前端伺服器的 fqdn，或是 director 集區或 director) （在上述步驟3中識別）。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="2b5fd-157">您可能需要儲存在這裡，或者，如果您需要在商務用 Skype 伺服器環境中的每個 SIP 網域的正向對應區域中建立其他 CNAME 記錄，您應該這麼做，但在您準備好後，請儲存您的工作。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="2b5fd-158">建立內部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="2b5fd-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="2b5fd-159">登入您網路中的 DNS 伺服器，該伺服器是 **Domain Admins** 群組的成員，或是 **DnsAdmins** 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="2b5fd-160">按一下 [ **開始**]，選擇 [系統 **管理工具** ] (您可能需要 **搜尋** 它（如果不是「開始」功能表中的選項）) ，然後按一下 [ **dns** ] 以開啟 [dns 管理] 嵌入式管理單元。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="2b5fd-161">在主控台視窗的左窗格中，您需要移至您的商務用 Skype 伺服器前端伺服器所在的網域，並展開其中的 **正向對應區域** 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="2b5fd-162">請花一點時間來查看您有下列哪一項：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="2b5fd-163">前端伺服器的任何主機 A 或 AAAA 記錄 (Standard 或 Enterprise) 或前端集區 (s) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="2b5fd-164">Director 或 Director 集區的任何主機 A 或 AAAA 記錄 (您在部署) 中的選用設定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="2b5fd-165">在您記下之後，請以滑鼠右鍵按一下 SIP 功能變數名稱，然後從功能表中選擇 [ **新增主機 (A 或 AAAA)** ]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="2b5fd-166">在 [ **名稱** ] 文字方塊中，輸入 lyncdiscoverinternal 的主機名稱，以供內部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="2b5fd-167">在 [ **IP 位址** ] 文字方塊中，輸入前端集區的內部 WEB 服務 IP 位址 (或單一前端伺服器，或是 director 集區或 director) （在上述步驟4中識別）。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="2b5fd-168">完成後，按一下 [ **新增主機**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="2b5fd-169">您必須為商務用 Skype 伺服器環境中支援的每個 SIP 網域，在正向對應區域中建立新的自動探索 A 或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="2b5fd-170">若要這麼做，請視需要重複步驟6-8。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="2b5fd-171">當您完成時，請按一下 [ **完成**]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="2b5fd-172">建立外部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="2b5fd-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="2b5fd-173">這些步驟是一般的，因為我們無法判斷可能使用的公用 DNS 提供者，但我們仍想要協助您。請使用可讓新 DNS 記錄的帳戶登入您的公用 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="2b5fd-174">在這個時間點，SIP 網域應該已存在於商務用 Skype Server 中。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="2b5fd-175">展開這個 SIP 網域的 **正向對應區域** ，或以其他方式開啟它。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="2b5fd-176">請花一點時間來查看您有下列哪一項：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="2b5fd-177">前端伺服器的任何主機 A 或 AAAA 記錄 (Standard 或 Enterprise) 或前端集區 (s) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="2b5fd-178">Director 或 Director 集區的任何主機 A 或 AAAA 記錄 (您在部署) 中的選用設定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="2b5fd-179">一旦您獲得資訊之後，您應該能夠選取選項來建立 **新的主機 a 或 AAAA**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="2b5fd-180">現在您應該可以輸入 **名稱**，您必須在這裡為外部自動探索服務 URL 輸入 lyncdiscover。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="2b5fd-181">接下來，您應該要有一個區域可在 **IP Addresss** 中輸入，這必須是前端集區的 IP (或單一前端伺服器，或是 director 集區或 director) （在上述步驟3中所識別）。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="2b5fd-182">您可能需要儲存在這裡，或者，如果您需要在每個 SIP 網域的正向對應區域中建立額外的 A 或 AAAA 記錄，以供商務用 Skype 伺服器環境使用，則應該這麼做，但在您準備好後，請儲存您的工作。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="2b5fd-183">修改憑證</span><span class="sxs-lookup"><span data-stu-id="2b5fd-183">Modify certificates</span></span>
<span data-ttu-id="2b5fd-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="2b5fd-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="2b5fd-185">如果您有關于如何規劃憑證的相關問題，我們已在我們為 [商務用 Skype Server 文章的行動方案](../plan-your-deployment/mobility.md) 中記錄這方面的問題。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="2b5fd-186">一旦您已複習好，我們會逐步引導您完成下列作業：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="2b5fd-187">我是否需要新的憑證？</span><span class="sxs-lookup"><span data-stu-id="2b5fd-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="2b5fd-188">從憑證授權單位單位 (CA) 要求新憑證。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="2b5fd-189">使用 PowerShell 來更新就地憑證和取代專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="2b5fd-190">使用 Microsoft Management Console 中的憑證管理憑證檢查憑證 (MMC) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="2b5fd-191">我是否需要新的憑證？</span><span class="sxs-lookup"><span data-stu-id="2b5fd-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="2b5fd-192">首先，您可能需要檢查並查看存在哪些憑證，以及是否有您所需的專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="2b5fd-193">若要這麼做，您必須使用本機系統管理員帳戶登入您的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="2b5fd-194">此帳戶可能也需要 (CA) 的許可權，才能執行這些步驟中的部分。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="2b5fd-195">開啟商務用 Skype Server 管理命令介面 (您可以使用「搜尋」來找出它是否已釘選到 [開始] 功能表或工作列) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="2b5fd-196">在您嘗試新增更新的憑證之前，您必須先知道哪些憑證已被指派，才是必要的做法。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="2b5fd-197">因此，在命令中輸入：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="2b5fd-198">步驟3中的資訊將是您獨有的。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="2b5fd-199">您必須查看此專案，以判斷您是否有多個專案指派的單一憑證，或是否已指派不同的憑證以供需要它們的不同元件使用。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="2b5fd-200">**Use** 參數會告訴您憑證的使用方式，以及 **指紋** 參數會告訴您，是否全部都是相同的憑證或多個證書。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="2b5fd-201">如果您在規劃區段中有建議的 SAN 專案，您就會是好事。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="2b5fd-202">如果不是，您必須要求新的憑證或多個憑證 (，視您的憑證授權單位) 設定而定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="2b5fd-203">從憑證授權單位單位 (CA 要求新憑證或憑證) </span><span class="sxs-lookup"><span data-stu-id="2b5fd-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="2b5fd-204">檢查您所擁有的 SAN 專案後，您會知道您已透過) 上的步驟進行檢查後，您有 **一個憑證** (，而且您已學到您沒有所有需要的專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="2b5fd-205">需要對您的 CA 進行新的憑證要求。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="2b5fd-206">開啟商務用 Skype 伺服器 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b5fd-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="2b5fd-207">若缺少自動探索服務 SAN (將-Ca 參數取代為您自己的憑證授權單位路徑) ：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="2b5fd-208">現在，如果您有多個 SIP 網域，您就無法使用 AllSipDomain 參數，如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="2b5fd-209">您必須改用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="2b5fd-210">當您使用 DomainName 參數時，您必須定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="2b5fd-211">範例會 (以您自己的憑證授權單位單位路徑取代-Ca 參數) ：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="2b5fd-212">或者，在您檢查您所擁有的 SAN 專案後，您就會發現有 **多個憑證** 沒有所有需要的專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="2b5fd-213">需要對您的 CA 進行新的憑證要求。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="2b5fd-214">開啟商務用 Skype 伺服器 PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b5fd-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="2b5fd-215">若缺少自動探索服務 SAN (將-Ca 參數取代為您自己的憑證授權單位路徑) ：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="2b5fd-216">現在，如果您有多個 SIP 網域，您就無法使用 AllSipDomain 參數，如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="2b5fd-217">您必須改用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="2b5fd-218">當您使用 DomainName 參數時，您必須定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="2b5fd-219">範例會 (以您自己的憑證授權單位單位路徑取代-Ca 參數) ：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="2b5fd-220">一旦 CA 產生新的憑證後，您就必須將其指派給他們。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="2b5fd-221">使用商務用 Skype Server 管理命令介面指派憑證</span><span class="sxs-lookup"><span data-stu-id="2b5fd-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="2b5fd-222">您必須執行下列 **其中一** 項，視您在上述「我需要新的認證」一節中找到的專案而定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="2b5fd-223">如果您擁有單一憑證 (指紋完全相同的憑證) 則需要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="2b5fd-224">如果您有不同的憑證 (指紋全都不同) ，請改為執行這項作業：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="2b5fd-225">在 Microsoft Management Console 中查看憑證 (MMC) </span><span class="sxs-lookup"><span data-stu-id="2b5fd-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="2b5fd-226">您可以選擇使用 MMC 的憑證嵌入式管理單元來查看憑證。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="2b5fd-227">只需在搜尋中輸入 MMC，它應會以應用程式選項形式彈出。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="2b5fd-228">若要新增憑證嵌入式管理單元，您 **必須按一下 [** 檔案]，然後按一下 [ **新增/移除嵌入式管理單元 ...** (] 或 [鍵盤 **快捷方式]** （) ）也可正常運作。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="2b5fd-229">您可以在左側窗格中選擇 [**憑證**]，然後在快顯視窗中選取它，然後按一下 [**電腦帳戶**]，然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="2b5fd-230">仍在快顯視窗中，在您所需查看的憑證所在的電腦上，只要您要執行此動作，否則請保留在 **本機電腦** 上的選取範圍。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="2b5fd-231">如果您是在遠端電腦上運作，請將選項按鈕變更為 **另一部電腦** ，然後輸入該電腦的 FQDN，或使用 [ **流覽]** 按鈕，透過 AD 搜尋該電腦。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="2b5fd-232">選取電腦之後，您需要在 [就緒時按一下 **[完成]** ，然後按一下 **[確定]** ，將嵌入式管理單元新增至 MMC。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="2b5fd-233">在 MMC 的左窗格中，展開 [ **憑證** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="2b5fd-234">同時展開 [ **個人** ] 資料夾，然後選取 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="2b5fd-235">這可讓您查看此存放區中的憑證。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="2b5fd-236">您需要找出您想要查看的憑證，並在其上按一下滑鼠右鍵，然後選擇 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2b5fd-237">如何知道這是哪一個憑證？</span><span class="sxs-lookup"><span data-stu-id="2b5fd-237">How do you know what certificate this is?</span></span> <span data-ttu-id="2b5fd-238">它應該是指派給伺服器陣列之所有專案的單一憑證，或者您可以針對不同的專案（如預設值、內部 Web 服務等）使用多個憑證，在這種情況下，您可能需要查看多個憑證。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="2b5fd-239">多個憑證會有相同的指紋。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="2b5fd-240">當您進入 **憑證** 視圖後，請選擇 [ **詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="2b5fd-241">這可讓您在選取 [主旨] 時查看憑證 **的主體** 名稱，並顯示指定的主體名稱和相關聯的屬性。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="2b5fd-242">您也需要檢查 **主體替代名稱** 專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="2b5fd-243">您會發現下列一或多項：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="2b5fd-244">此集區的集區名稱，如果這不是集區，則為單一伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="2b5fd-245">指派憑證的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="2b5fd-246">簡單 URL 記錄，通常是符合和撥入的。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="2b5fd-247">Web 服務的內部及 Web 服務外部名稱 (例如，webpool01.contoso.net、webpool01.contoso.com) ，其依據拓撲產生器和透過 ridden Web 服務選取範圍內的選擇。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="2b5fd-248">如果已指派，則 lyncdiscover。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2b5fd-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="2b5fd-249">和 lyncdiscoverinternal。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2b5fd-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="2b5fd-250">記錄。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-250">records.</span></span>
    
     <span data-ttu-id="2b5fd-251">如果您有一個以上指派的 (請檢查多個憑證。) 以上的附注。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="2b5fd-252">因此，如果您找到 lyncdiscover。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2b5fd-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="2b5fd-253">和 lyncdiscoverinternal。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="2b5fd-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="2b5fd-254">您已設定此記錄。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-254">records, you've got this configured already.</span></span> <span data-ttu-id="2b5fd-255">您可以關閉 MMC。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="2b5fd-256">若未指派，您將需要 (以上所述的新憑證要求) 或您必須將其安裝後的要求 (我們建議針對該) 執行上述 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="2b5fd-257">設定反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="2b5fd-257">Configure the reverse proxy</span></span>
<span data-ttu-id="2b5fd-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="2b5fd-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="2b5fd-259">下列步驟並不是完全遵循。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="2b5fd-260">這是因為在舊版本的產品中，我們已引導您完成，例如設定威脅管理閘道 (TMG) ，但如果您沒有使用該功能，則必須從那裡使用您自己的版本。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="2b5fd-261">TMG 不再是由 Microsoft 做為產品提供，如果您仍然需要加以設定，則可以查看 [Lync Server 2013 的步驟](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="2b5fd-262">不過，下列資訊的目的應該更普遍有用，即使沒有任何方法可以提供每個反向 proxy 的特定逐步步驟。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="2b5fd-263">我們有兩個主要考慮事項：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="2b5fd-264">您是否要透過 HTTPS (執行初始自動探索要求，我們建議) ？</span><span class="sxs-lookup"><span data-stu-id="2b5fd-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="2b5fd-265">如果您有 web 發佈規則，您必須加以修改。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="2b5fd-266">如果您還沒有網路發佈規則，則必須加以建立。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="2b5fd-267">如果您是透過 HTTP 進行初始自動探索要求，您也必須建立或修改該規則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b5fd-268">**重要事項** Proxy 超時值是一個數位，會因部署而異。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="2b5fd-269">您應該監視您的部署，並修改用戶端的最佳體驗值。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="2b5fd-270">您可以將值設為低200。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="2b5fd-271">如果您在環境中支援 Lync 行動用戶端，則應該將值設為960，以允許來自 Office 365 的推播通知超時，其超時值為900。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="2b5fd-272">您很可能需要增加超時值，以避免用戶端在值太低時中斷連線，或在用戶端中斷連線後，如果經由 proxy 的連線不會中斷連線，則降低數目。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="2b5fd-273">監視及設定環境的一般功能是判斷此值適當設定的唯一準確方式。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="2b5fd-274">為外部自動探索 SAN 和 URL 修改現有的 web 發行規則</span><span class="sxs-lookup"><span data-stu-id="2b5fd-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="2b5fd-275">開啟反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="2b5fd-276">您需要找出您的 web 發行規則，然後選擇 [編輯] 選項 (它可能位於功能表或索引標籤上，視您的反向 proxy 設定) 而定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="2b5fd-277">應該會有一個區域，指出此 web 發行規則的套用目標。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="2b5fd-278">您必須修改傳入網站或網站要求的此規則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="2b5fd-279">您即將 **加入** 新的專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="2b5fd-280">輸入自動探索網站的名稱 (我們將使用的範例是 lyncdiscover.contoso.com) ]，然後根據您的反向 proxy 格式，按一下 **[確定] 或 [** **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="2b5fd-281">您的新憑證可能具有「自動探索」 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="2b5fd-282">必須同時安裝和設定，以根據您的反向 proxy 設定進行使用。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="2b5fd-283">設定完成時，請務必儲存所有專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="2b5fd-284">如果反向 proxy 具有 **測試** 功能，請使用它，以確保一切運作正常。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="2b5fd-285">現在，如果您在環境中有 Director 或 Director 集區，您可能需要重複這些步驟。 (這意味著您有第二個規則) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="2b5fd-286">建立外部自動探索 URL 的 web 發行規則</span><span class="sxs-lookup"><span data-stu-id="2b5fd-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="2b5fd-287">開啟反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="2b5fd-288">您需要找出在介面中建立 web 發行規則的位置，然後選擇 [ **新增** ] 或 [ **建立** ] 選項 (它可能位於功能表或索引標籤上，視您的反向 proxy 設定) 而定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="2b5fd-289">您正在尋找選項來建立新的 web 發行規則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="2b5fd-290">一般來說，您必須輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="2b5fd-291">**名稱**：規則的名稱</span><span class="sxs-lookup"><span data-stu-id="2b5fd-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="2b5fd-292">**規則動作**：在此情況下，它是一個 **允許** 規則，您可以透過您的反向 proxy 進行某項處理。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="2b5fd-293">您所選擇的 **發佈** 規則或選項，就是 **單一網站或負載平衡器**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="2b5fd-294">這必須是 **SSL** 才能進行外部存取，請選擇該選項。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="2b5fd-295">您將需要發行 **內部發佈** 的路徑，然後在前端集區的負載平衡 (器上輸入外部 Web 服務的 fqdn，如果您有一個) ，就會 sfb_pool01 一個範例（如有一個）。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="2b5fd-296">您應輸入 **/\\** _ 作為要發佈的路徑，但您也需要將原始的主機標頭轉寄給您。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="2b5fd-297">**公用或外部名稱** 詳細資料或資訊都有一個選項。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="2b5fd-298">您可以在此位置輸入：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="2b5fd-299">**接受要求**，但應為功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="2b5fd-300">您應輸入 lyncdiscover 的 **名稱** **。**</span><span class="sxs-lookup"><span data-stu-id="2b5fd-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="2b5fd-301"><sipdomain> (這是) 的外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="2b5fd-302">現在，如果您要為前端集區上的外部 Web 服務 URL 建立規則，您必須在前端集區上輸入外部 Web 服務的 FQDN (例如，lyncwebextpool01.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="2b5fd-303">將會有 **路徑** 選項，您必須在 **/\\** 這裡輸入 _。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-303">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="2b5fd-304">您必須使用最新的公開憑證，選取 [SSL 接聽程式 *]*。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-304">You'll need to select a _ *SSL Listener*\* with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="2b5fd-305">**驗證委派** 應設定為 [ **不委派**]，但 **應** 允許直接用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="2b5fd-306">規則應設定為 [ **所有使用者**]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="2b5fd-307">這應該是您建立此規則所需的所有資訊，並可讓您繼續。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="2b5fd-308">您必須確定 **原始的主機標頭** 已轉寄。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="2b5fd-309">**網頁伺服器** 埠也必須設定，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="2b5fd-310">將 **要求重新導向至 HTTP 埠**，埠號碼應該是 **8080**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="2b5fd-311">將 **要求重新導向至 SSL 埠**，埠號碼應該是 **4443**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="2b5fd-312">設定好任何專案時，您必須儲存或套用這些專案，然後您將需要測試規則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="2b5fd-313">建立埠80的 web 發行規則 (選用) </span><span class="sxs-lookup"><span data-stu-id="2b5fd-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="2b5fd-314">開啟反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="2b5fd-315">您需要找出在介面中建立 web 發行規則的位置，然後選擇 [ **新增** ] 或 [ **建立** ] 選項 (它可能位於功能表或索引標籤上，視您的反向 proxy 設定) 而定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="2b5fd-316">您正在尋找選項來建立新的 web 發行規則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="2b5fd-317">一般來說，您必須輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="2b5fd-318">**名稱**：規則的名稱</span><span class="sxs-lookup"><span data-stu-id="2b5fd-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="2b5fd-319">**規則動作**：在此情況下，它是一個 **允許** 規則，您可以透過您的反向 proxy 進行某項處理。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="2b5fd-320">您所選擇的 **發佈** 規則或選項，就是 **單一網站或負載平衡器**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="2b5fd-321">這必須是不安全的連線， **才能連線至發佈的網頁伺服器或伺服器** 陣列。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="2b5fd-322">您將需要發行 **內部發佈** 的路徑，並輸入前端集區之負載平衡器之 **VIP 位址** 的 FQDN，例如，sfb_pool01 為 contoso。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="2b5fd-323">您應輸入 **/\\** _ 作為要發佈的路徑，但您也需要將原始的主機標頭轉寄給您。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="2b5fd-324">**公用或外部名稱** 詳細資料或資訊都有一個選項。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="2b5fd-325">您可以在此位置輸入：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="2b5fd-326">**接受要求**，但應為功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="2b5fd-327">您應輸入 lyncdiscover 的 **名稱** **。**</span><span class="sxs-lookup"><span data-stu-id="2b5fd-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="2b5fd-328"><sipdomain> (這是) 的外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="2b5fd-329">將會有 **路徑** 選項，您必須在 **/\\** 這裡輸入 _。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-329">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="2b5fd-330">您必須選取網頁接聽程式，或允許您的反向 proxy 為您建立一個攔截器。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="2b5fd-331">_ *驗證委派*\* 應該設定為 [ **不委派**]，但 **不** 允許直接的用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-331">_ *Authentication Delegation*\* should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="2b5fd-332">規則應設定為 [ **所有使用者**]。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="2b5fd-333">這應該是您建立此規則所需的所有資訊，並可讓您繼續。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="2b5fd-334">需要設定 **網頁伺服器** 埠，您需要執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="2b5fd-335">將 **要求重新導向至 HTTP 埠**，埠號碼應該是 **8080**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="2b5fd-336">將 **要求重新導向至 SSL 埠**，埠號碼應該是 **4443**。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="2b5fd-337">設定好任何專案時，您必須儲存或套用這些專案，然後您將需要測試規則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="2b5fd-338">設定具有混合式部署行動的自動探索</span><span class="sxs-lookup"><span data-stu-id="2b5fd-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="2b5fd-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="2b5fd-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="2b5fd-340">商務用 Skype Server 中的混合式環境是結合內部部署和 O365 環境的環境。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="2b5fd-341">當您在混合式環境中使用商務用 Skype 伺服器時，自動探索服務必須能夠從這些環境中尋找使用者。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="2b5fd-342">若要讓行動用戶端探索使用者所在的位置，必須使用新的統一資源定位器 (URL) ，來設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="2b5fd-343">步驟如下：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-343">The steps are:</span></span>
  
1. <span data-ttu-id="2b5fd-344">開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="2b5fd-345">執行下列動作以取得商務用 Skype 伺服器環境之屬性 **ProxyFQDN** 的值：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="2b5fd-346">然後，在命令介面視窗中，執行：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="2b5fd-347">其中 [identity] 以共用 SIP 位址空間的功能變數名稱取代。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="2b5fd-348">測試行動性部署</span><span class="sxs-lookup"><span data-stu-id="2b5fd-348">Test your Mobility deployment</span></span>
<span data-ttu-id="2b5fd-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="2b5fd-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="2b5fd-350">一旦您已部署商務用 Skype Server 行動服務和商務用 Skype Server 自動探索服務，您就會想要執行測試交易，以確定您的部署正確運作。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="2b5fd-351">您可以執行 **Test-CsUcwaConference** ，以測試兩位使用者在會議中建立、加入和通訊的能力。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="2b5fd-352">您需要有兩位使用者 (實際或測試) 及其完整認證，才能進行此項測試。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="2b5fd-353">此命令會同時適用于商務用 Skype 用戶端和 Lync Server 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="2b5fd-354">在商務用 Skype Server 2015 上的 Lync Server 2010 用戶端，您必須執行 **Test-CsMcxP2PIM** 以進行測試。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="2b5fd-355">您的 Lync Server 2010 使用者仍必須是實際使用者或預先定義的測試使用者，而且您將需要其密碼認證。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="2b5fd-356">MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="2b5fd-357">所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="2b5fd-358">具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="2b5fd-359">測試會議的商務用 Skype 和 Lync 2013 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="2b5fd-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="2b5fd-360">在安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的任何電腦上，以 **CsAdministrator** 角色成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="2b5fd-361">啟動 **商務用 Skype Server 管理命令** 介面 (您可以在 [搜尋] 中輸入名稱或移至 [ **所有程式** ]，然後選擇) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="2b5fd-362">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="2b5fd-363">您也可以在腳本中設定認證，並將認證傳遞至 test Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="2b5fd-364">我們有下列範例。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="2b5fd-365">測試 Lync 2010 行動用戶端的會議</span><span class="sxs-lookup"><span data-stu-id="2b5fd-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="2b5fd-366">MCX (行動服務) 支援舊版行動用戶端，商務用 Skype Server 2019 不再提供支援。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="2b5fd-367">所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="2b5fd-368">具有使用 MCX 之舊版用戶端的使用者，必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="2b5fd-369">在安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的任何電腦上，以 **CsAdministrator** 角色成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="2b5fd-370">啟動 **商務用 Skype Server 管理命令** 介面 (您可以在 [搜尋] 中輸入名稱或移至 [ **所有程式** ]，然後選擇) 。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="2b5fd-371">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="2b5fd-372">您也可以在腳本中設定認證，並將認證傳遞至 test Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="2b5fd-373">我們有下列範例。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="2b5fd-374">若要進一步複查命令過程，您可以取出 [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 和 [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-374">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="2b5fd-375">設定推入通知</span><span class="sxs-lookup"><span data-stu-id="2b5fd-375">Configure for push notifications</span></span>
<span data-ttu-id="2b5fd-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="2b5fd-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="2b5fd-377">即使當 Skype 或 Lync 應用程式非使用中時，也可以將「徽章」、圖示或警示形式的推播通知傳送至行動裝置。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="2b5fd-378">但什麼是推播通知？</span><span class="sxs-lookup"><span data-stu-id="2b5fd-378">But what are push notifications?</span></span> <span data-ttu-id="2b5fd-379">它們是事件警示，例如新的或錯過的 IM 邀請，或是收到的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="2b5fd-380">商務用 Skype Server 行動服務會將這些通知傳送至雲端式商務用 Skype Server 推播通知服務，然後在 Windows Phone 使用者 (MSNS) 中傳送通知給 Microsoft 推播通知服務。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="2b5fd-381">這項功能並不會從 Lync Server 2013 變更，但如果您有商務用 Skype 伺服器，則會想要執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="2b5fd-382">若為商務用 Skype Server Edge Server，請新增主機服務提供者、Microsoft 商務用 Skype Online，然後在您的組織和商務用 Skype Online 之間設定裝載提供者同盟。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="2b5fd-383">執行 **Set-CsPushNotificationConfiguration** Cmdlet 以啟用推播通知。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="2b5fd-384">依預設，推播通知會關閉。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="2b5fd-385">測試同盟設定及推播通知。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="2b5fd-386">設定適用于推播通知的商務用 Skype Edge Server</span><span class="sxs-lookup"><span data-stu-id="2b5fd-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="2b5fd-387">使用 **CsAdministrator** 角色成員的帳戶登入，安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="2b5fd-388">啟動 **商務用 Skype Server 管理命令** 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2b5fd-389">新增商務用 Skype Server online 主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="2b5fd-390">範例：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="2b5fd-391">您不可以有多個與單一主機服務提供者的同盟關聯。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="2b5fd-392">因此，如果您已設定與 sipfed.online.lync.com 具有同盟關聯的裝載提供者，請勿為其新增其他主機服務提供者，即使主機服務的身分識別是 SkypeOnline 以外的其他專案。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="2b5fd-393">在商務用 Skype Online 中，設定組織與推播通知服務之間的主機服務同盟同盟。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="2b5fd-394">您必須在命令列上輸入：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="2b5fd-395">啟用推播通知</span><span class="sxs-lookup"><span data-stu-id="2b5fd-395">Enable push notifications</span></span>

1. <span data-ttu-id="2b5fd-396">使用 **CsAdministrator** 角色成員的帳戶登入，安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="2b5fd-397">啟動 **商務用 Skype Server 管理命令** 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2b5fd-398">啟用推播通知：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="2b5fd-399">啟用同盟：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="2b5fd-400">測試同盟及推播通知</span><span class="sxs-lookup"><span data-stu-id="2b5fd-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="2b5fd-401">使用 **CsAdministrator** 角色成員的帳戶登入，安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="2b5fd-402">啟動 **商務用 Skype Server 管理命令** 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2b5fd-403">測試同盟設定：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="2b5fd-404">範例：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="2b5fd-405">測試推播通知：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="2b5fd-406">範例：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="2b5fd-407">設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="2b5fd-407">Configure Mobility policy</span></span>
<span data-ttu-id="2b5fd-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="2b5fd-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="2b5fd-409">您具備商務用 Skype 伺服器的功能，可決定誰可以使用行動服務、撥打您的行動、透過 IP 語音 (VoIP) 或影片，以及 VoIP 或影片是否需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="2b5fd-410">「透過公司通話」可讓行動使用者在撥打和接聽電話時使用其公司電話號碼，而不是其行動電話號碼。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="2b5fd-411">該行另一端的人員不會看到行動使用者的蜂窩電話號碼，並可讓行動使用者避免撥出的電話費用。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="2b5fd-412">當您設定 VoIP 和影片時，使用者可以採取或撥打 VoIP 通話和影片。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="2b5fd-413">[WiFi 使用狀況] 設定會決定使用者的行動裝置是否需要透過行動電話資料網路使用 WiFi 網路。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="2b5fd-414">行動性、呼叫方式，以及 VoIP 和影片功能預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="2b5fd-415">需要停用 WiFi VoIP 和影片的設定。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="2b5fd-416">系統管理員可以變更全域、依網站，或由使用者變更此功能。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="2b5fd-417">若要能夠透過工作使用行動功能及通話，使用者必須：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="2b5fd-418">啟用商務用 Skype 伺服器</span><span class="sxs-lookup"><span data-stu-id="2b5fd-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="2b5fd-419">已啟用 Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="2b5fd-420">指派 **EnableMobility** 選項設定為 **True** 的行動原則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="2b5fd-421">若要讓使用者能夠使用「從公司撥號」，他們也必須：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="2b5fd-422">已指定已選取 [ **啟用同時振鈴電話** ] 選項的語音原則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="2b5fd-423">指派 **EnableOutsideVoice** 設定為 **True** 的行動性原則。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2b5fd-424">未啟用 Enterprise Voice 的使用者可以使用行動裝置，在行動裝置上使用 [按一下以加入] 連結，在行動裝置上使用 [按一下以加入會議]，如果為其相關聯的語音原則設定適當的選項，即可使用其行動裝置 VoIP 進行通話或加入會議。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="2b5fd-425">規劃主題中有更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="2b5fd-426">修改全域行動性原則</span><span class="sxs-lookup"><span data-stu-id="2b5fd-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="2b5fd-427">使用 **CsAdministrator** 角色成員的帳戶登入，安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="2b5fd-428">啟動 **商務用 Skype Server 管理命令** 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2b5fd-429">透過輸入下列專案，關閉行動及透過工作撥打的電話：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="2b5fd-430">您可以在不關閉行動存取的情況下，關閉工作的來電。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="2b5fd-431">不過，您不能關閉行動性，也不會關閉「從公司通話」。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="2b5fd-432">如需詳細資訊，請參閱 [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-432">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="2b5fd-433">依網站修改行動性原則</span><span class="sxs-lookup"><span data-stu-id="2b5fd-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="2b5fd-434">使用 **CsAdministrator** 角色成員的帳戶登入，安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="2b5fd-435">啟動 **商務用 Skype Server 管理命令** 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2b5fd-436">您可以建立網站層級原則、關閉 VoIP 和影片、啟用 IP 音訊的「需要」 WiFi，以及要求透過網站 WiFi 的 IP 影片。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="2b5fd-437">類型：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="2b5fd-438">若要深入瞭解，請參閱 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-438">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="2b5fd-439">依使用者修改行動性原則</span><span class="sxs-lookup"><span data-stu-id="2b5fd-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="2b5fd-440">使用 **CsAdministrator** 角色成員的帳戶登入，安裝 **商務用 Skype Server 管理命令** 介面和 **ocscore.msi** 的電腦。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="2b5fd-441">啟動 **商務用 Skype Server 管理命令** 介面。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="2b5fd-442">建立使用者層級的行動性原則，關閉行動能力，並依使用者進行呼叫。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="2b5fd-443">類型：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="2b5fd-444">範例資料的進一步範例：</span><span class="sxs-lookup"><span data-stu-id="2b5fd-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="2b5fd-445">您可以在不關閉行動存取的情況下，關閉工作的來電。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="2b5fd-446">不過，您不能關閉行動性，也不會關閉「從公司通話」。</span><span class="sxs-lookup"><span data-stu-id="2b5fd-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

