---
title: 部署及設定 Mobility skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: 本文將引導您設定要使用的行動性服務，可讓您能夠利用 Skype for Business Server 行動功能的行動裝置現有 Skype for Business Server 安裝的步驟。
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029064"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="79da9-103">部署及設定 Mobility skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79da9-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="79da9-104">本文將引導您設定要使用的行動性服務，可讓您能夠利用 Skype for Business Server 行動功能的行動裝置現有 Skype for Business Server 安裝的步驟。</span><span class="sxs-lookup"><span data-stu-id="79da9-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="79da9-105">需要檢閱[Mobility for Skype for Business Server 規劃](../plan-your-deployment/mobility.md)文章，您應該準備好繼續進行下列步驟來部署到您 Skype for Business 伺服器環境的行動性。</span><span class="sxs-lookup"><span data-stu-id="79da9-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="79da9-106">以下是步驟 （與我們正在此表格中包含的權限清單）：</span><span class="sxs-lookup"><span data-stu-id="79da9-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="79da9-107">**階段**</span><span class="sxs-lookup"><span data-stu-id="79da9-107">**Phase**</span></span>|<span data-ttu-id="79da9-108">**權限**</span><span class="sxs-lookup"><span data-stu-id="79da9-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="79da9-109">建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="79da9-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="79da9-110">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="79da9-110">Domain Admins</span></span>  <br/> <span data-ttu-id="79da9-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="79da9-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="79da9-112">修改憑證</span><span class="sxs-lookup"><span data-stu-id="79da9-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="79da9-113">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="79da9-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="79da9-114">設定反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="79da9-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="79da9-115">本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="79da9-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="79da9-116">使用混合式部署設定行動的自動探索</span><span class="sxs-lookup"><span data-stu-id="79da9-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="79da9-117">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="79da9-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="79da9-118">測試行動性部署</span><span class="sxs-lookup"><span data-stu-id="79da9-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="79da9-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="79da9-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="79da9-120">設定推入通知</span><span class="sxs-lookup"><span data-stu-id="79da9-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="79da9-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="79da9-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="79da9-122">設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="79da9-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="79da9-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="79da9-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="79da9-124">下列各節包含步驟假設您已閱讀規劃主題。</span><span class="sxs-lookup"><span data-stu-id="79da9-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="79da9-125">如果任何項目令人困惑您，請隨意簽出所包含的資訊。</span><span class="sxs-lookup"><span data-stu-id="79da9-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="79da9-126">MCX (Mobility Service) 支援舊版的行動用戶端已不再提供 skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="79da9-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="79da9-127">所有目前的 Skype for Business 行動用戶端已使用 Unified Communications Web API (UCWA) 來支援立即訊息 (IM)、 目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="79da9-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="79da9-128">使用舊版用戶端使用 MCX 使用者必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="79da9-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="79da9-129">建立 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="79da9-129">Create DNS records</span></span>
<span data-ttu-id="79da9-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="79da9-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="79da9-131">您可能已經具備這些一部分您 Skype for Business Server 環境中，但您需要建立自動探索運作的下列記錄：</span><span class="sxs-lookup"><span data-stu-id="79da9-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="79da9-132">內部 DNS 記錄，以支援行動裝置正在從網際網路連接貴組織的網路內的使用者。</span><span class="sxs-lookup"><span data-stu-id="79da9-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="79da9-133">外部 （或公用） DNS 記錄支援行動裝置正在從網際網路連接您的組織網路外的使用者。</span><span class="sxs-lookup"><span data-stu-id="79da9-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="79da9-134">這些記錄可以是其中一個 A （主機） 名稱或 CNAME 記錄 （您不必使兩者，我們正在只包括步驟以下所有內容）。</span><span class="sxs-lookup"><span data-stu-id="79da9-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="79da9-135">建立內部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="79da9-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="79da9-136">登入網路的**Domain Admins**群組成員或**DnsAdmins**群組中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="79da9-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="79da9-137">按一下 [**啟動**] （您可能需要**搜尋**，如果它不是關閉 [開始] 功能表選項） 選擇**系統管理工具**]，然後按一下 [ **DNS** ] 以開啟 DNS 管理] 嵌入式管理單元。</span><span class="sxs-lookup"><span data-stu-id="79da9-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="79da9-138">在主控台視窗的左側窗格中，您必須移至該網域的首頁您 skype for Business Server 前端伺服器，並依序展開 [**正向對應區域**那里。</span><span class="sxs-lookup"><span data-stu-id="79da9-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="79da9-139">花些時間若要查看您有的下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="79da9-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="79da9-140">任何主機 A 或 AAAA 記錄您的前端伺服器 （Standard 或 Enterprise） 或前端集區。</span><span class="sxs-lookup"><span data-stu-id="79da9-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="79da9-141">任何主機 A 或 AAAA 記錄為 Director 或 Director 集區 （選擇性的設定，您可能需要您部署中）。</span><span class="sxs-lookup"><span data-stu-id="79da9-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="79da9-142">一旦您已記下此，您的 SIP 網域名稱上按一下滑鼠右鍵，然後從功能表中選擇 [**新別名 (CNAME)** 。</span><span class="sxs-lookup"><span data-stu-id="79da9-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="79da9-143">在 [**別名名稱**] 文字方塊中，輸入 lyncdiscoverinternal 主機名稱，內部自動探索服務 url。</span><span class="sxs-lookup"><span data-stu-id="79da9-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="79da9-144">在 [**完整的網域名稱 (目標主機的 FQDN**，您需要輸入或瀏覽至前端集區 （或單一前端伺服器，或 Director 集區或 Director），在上面的步驟 4 中識別的內部 Web 服務 FQDN。</span><span class="sxs-lookup"><span data-stu-id="79da9-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="79da9-145">這輸入時，請按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="79da9-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="79da9-146">您需要在您 Skype for Business Server 環境中支援的每個 SIP 網域的正向對應區域中建立新的自動探索 CNAME 記錄。</span><span class="sxs-lookup"><span data-stu-id="79da9-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="79da9-147">建立外部 DNS CNAME 記錄</span><span class="sxs-lookup"><span data-stu-id="79da9-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="79da9-148">這些步驟是通用的因為我們無法判斷您可能使用，哪些公用 DNS 提供者，但是我們仍要協助解決。請登入帳戶，將能夠讓新的 DNS 記錄有您公用 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="79da9-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="79da9-149">在目前，SIP 網域應該已經存在那里 skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="79da9-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="79da9-150">依序展開 [**正向對應區域**此 SIP 網域，或否則開啟它。</span><span class="sxs-lookup"><span data-stu-id="79da9-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="79da9-151">花些時間若要查看您有的下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="79da9-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="79da9-152">任何主機 A 或 AAAA 記錄您的前端伺服器 （Standard 或 Enterprise） 或前端集區。</span><span class="sxs-lookup"><span data-stu-id="79da9-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="79da9-153">任何主機 A 或 AAAA 記錄為 Director 或 Director 集區 （選擇性的設定，您可能需要您部署中）。</span><span class="sxs-lookup"><span data-stu-id="79da9-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="79da9-154">一旦您有該資訊時，您應該可以選取 [建立**新別名 (CNAME)**] 選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="79da9-155">現在您應該能夠輸入**別名**，您需要輸入 lyncdiscover 以下外部自動探索服務 url。</span><span class="sxs-lookup"><span data-stu-id="79da9-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="79da9-156">接下來應該區域，以輸入在 [**目標主機的 FQDN**，這必須是前端集區 （或單一前端伺服器，或 Director 集區或 Director），在步驟 3 上述中識別的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="79da9-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="79da9-157">您可能需要將儲存在這裡，或如果您需要在您 Skype for Business Server 環境中每個 SIP 網域的正向對應區域中建立額外 CNAME 記錄，您應該這麼做，但一旦您已準備就緒，儲存您的工作。</span><span class="sxs-lookup"><span data-stu-id="79da9-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="79da9-158">建立內部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="79da9-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="79da9-159">登入網路的**Domain Admins**群組成員或**DnsAdmins**群組中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="79da9-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="79da9-160">按一下 [**啟動**] （您可能需要**搜尋**，如果它不是關閉 [開始] 功能表選項） 選擇**系統管理工具**]，然後按一下 [ **DNS** ] 以開啟 DNS 管理] 嵌入式管理單元。</span><span class="sxs-lookup"><span data-stu-id="79da9-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="79da9-161">在主控台視窗的左側窗格中，您必須移至該網域的首頁您 skype for Business Server 前端伺服器，並依序展開 [**正向對應區域**那里。</span><span class="sxs-lookup"><span data-stu-id="79da9-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="79da9-162">花些時間若要查看您有的下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="79da9-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="79da9-163">任何主機 A 或 AAAA 記錄您的前端伺服器 （Standard 或 Enterprise） 或前端集區。</span><span class="sxs-lookup"><span data-stu-id="79da9-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="79da9-164">任何主機 A 或 AAAA 記錄為 Director 或 Director 集區 （選擇性的設定，您可能需要您部署中）。</span><span class="sxs-lookup"><span data-stu-id="79da9-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="79da9-165">一旦您已記下此，您的 SIP 網域名稱上按一下滑鼠右鍵，然後從功能表中選擇 [**新增主機 （A 或 AAAA）** 。</span><span class="sxs-lookup"><span data-stu-id="79da9-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="79da9-166">在 [**名稱**] 文字方塊中，輸入 lyncdiscoverinternal 主機名稱，內部自動探索服務 url。</span><span class="sxs-lookup"><span data-stu-id="79da9-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="79da9-167">在 [ **IP 位址**] 文字方塊中，上述步驟 4 中所識別類型您前端集區] （或單一前端伺服器，或 Director 集區或 Director） 的內部 Web 服務 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="79da9-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="79da9-168">完成時，請按一下 [**新增主機**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="79da9-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="79da9-169">您需要在您 Skype for Business Server 環境中支援的每個 SIP 網域的正向對應區域中建立新的自動探索 A 或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="79da9-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="79da9-170">若要這麼做，請重複步驟 6-8 為所需的次數。</span><span class="sxs-lookup"><span data-stu-id="79da9-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="79da9-171">當您完成時，按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="79da9-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="79da9-172">建立外部 DNS A 記錄</span><span class="sxs-lookup"><span data-stu-id="79da9-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="79da9-173">這些步驟是通用的因為我們無法判斷您可能使用，哪些公用 DNS 提供者，但是我們仍要協助解決。請登入帳戶，將能夠讓新的 DNS 記錄有您公用 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="79da9-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="79da9-174">在目前，SIP 網域應該已經存在那里 skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="79da9-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="79da9-175">依序展開 [**正向對應區域**此 SIP 網域，或否則開啟它。</span><span class="sxs-lookup"><span data-stu-id="79da9-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="79da9-176">花些時間若要查看您有的下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="79da9-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="79da9-177">任何主機 A 或 AAAA 記錄您的前端伺服器 （Standard 或 Enterprise） 或前端集區。</span><span class="sxs-lookup"><span data-stu-id="79da9-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="79da9-178">任何主機 A 或 AAAA 記錄為 Director 或 Director 集區 （選擇性的設定，您可能需要您部署中）。</span><span class="sxs-lookup"><span data-stu-id="79da9-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="79da9-179">一旦您有該資訊，您應該可以選取 [建立**新的主機 A 或 AAAA**選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="79da9-180">現在您應該能夠輸入**名稱**，您需要輸入 lyncdiscover 以下外部自動探索服務 url。</span><span class="sxs-lookup"><span data-stu-id="79da9-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="79da9-181">接下來應該區域，以在**IP 位址**中輸入，這必須是前端集區 （或單一前端伺服器，或 Director 集區或 Director），上述步驟 3 中所識別的 IP。</span><span class="sxs-lookup"><span data-stu-id="79da9-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="79da9-182">您可能需要將儲存在這裡，或如果您需要建立其他 A 或 AAAA 記錄之每個 SIP 網域的正向對應區域的您 Skype for Business Server 環境，您應該這麼做，請但一次您已準備就緒，儲存您的工作。</span><span class="sxs-lookup"><span data-stu-id="79da9-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="79da9-183">修改憑證</span><span class="sxs-lookup"><span data-stu-id="79da9-183">Modify certificates</span></span>
<span data-ttu-id="79da9-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="79da9-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="79da9-185">如果您有關於規劃周圍憑證的問題，我們已經記錄，我們[Mobility for Skype for Business Server 規劃](../plan-your-deployment/mobility.md)文件中。</span><span class="sxs-lookup"><span data-stu-id="79da9-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="79da9-186">一旦您已檢閱所，我們將引導您完成下列：</span><span class="sxs-lookup"><span data-stu-id="79da9-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="79da9-187">是否需要新的憑證？</span><span class="sxs-lookup"><span data-stu-id="79da9-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="79da9-188">要求新憑證從憑證授權單位 (CA)。</span><span class="sxs-lookup"><span data-stu-id="79da9-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="79da9-189">使用 PowerShell 取代更新就地憑證。</span><span class="sxs-lookup"><span data-stu-id="79da9-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="79da9-190">檢查 Microsoft Management Console (MMC) 中使用 [憑證嵌入式管理單元的憑證。</span><span class="sxs-lookup"><span data-stu-id="79da9-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="79da9-191">是否需要新的憑證？</span><span class="sxs-lookup"><span data-stu-id="79da9-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="79da9-192">首先，您可能需要檢查，並查看哪些憑證就地，並決定有您需要的項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="79da9-193">若要這麼做，您需要使用具備本機系統管理員帳戶登入您 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="79da9-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="79da9-194">此帳戶可能也需要有權限若要發行的憑證授權單位 (CA)，其中某些步驟。</span><span class="sxs-lookup"><span data-stu-id="79da9-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="79da9-195">開啟 Skype for Business Server 管理命令介面 （您可以使用搜尋找到它，如果您不需要它釘選到 [開始] 功能表中] 或 [工作] 列）。</span><span class="sxs-lookup"><span data-stu-id="79da9-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="79da9-196">它會移至是不可或缺的要知道哪些憑證必須獲指派您嘗試加入已更新的憑證之前。</span><span class="sxs-lookup"><span data-stu-id="79da9-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="79da9-197">因此在命令中，輸入：</span><span class="sxs-lookup"><span data-stu-id="79da9-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="79da9-198">步驟 3 中的資訊將會是您唯一的。</span><span class="sxs-lookup"><span data-stu-id="79da9-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="79da9-199">您要尋找它至判斷如果您有單一憑證已指派給多個項目，或是否有不同的憑證指派給需要之不同元件。</span><span class="sxs-lookup"><span data-stu-id="79da9-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="79da9-200">**使用**參數會告訴您如何使用的憑證，以及**Thumbprint**參數會告訴您如果是相同的所有憑證，或多個憑證。</span><span class="sxs-lookup"><span data-stu-id="79da9-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="79da9-201">如果您有建議在我們的計劃] 區段的 SAN 項目，您已準備好。</span><span class="sxs-lookup"><span data-stu-id="79da9-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="79da9-202">如果不是，您必須從您的憑證授權單位要求新憑證或多個憑證 （根據您的設定）。</span><span class="sxs-lookup"><span data-stu-id="79da9-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="79da9-203">要求新憑證或憑證，您的憑證授權單位 (CA)</span><span class="sxs-lookup"><span data-stu-id="79da9-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="79da9-204">您已檢查，以查看您有哪些 SAN 項目之後，您會知道您有一個**單一憑證**（在檢查之後上述步驟透過），並學會您不需要您需要的所有項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="79da9-205">新憑證要求，必須對您的 CA。</span><span class="sxs-lookup"><span data-stu-id="79da9-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="79da9-206">開啟您 Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="79da9-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="79da9-207">針對遺漏自動探索服務 SAN (英文） （將-Ca 參數取代您自己的憑證授權單位的路徑）：</span><span class="sxs-lookup"><span data-stu-id="79da9-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="79da9-208">現在，如果您有多個 SIP 網域，您無法使用 AllSipDomain 參數，如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="79da9-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="79da9-209">您必須改為使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="79da9-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="79da9-210">當您使用 DomainName 參數時，您已取得最新產品定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="79da9-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="79da9-211">範例為 （將-Ca 參數取代您自己的憑證授權單位的路徑）：</span><span class="sxs-lookup"><span data-stu-id="79da9-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="79da9-212">或者，您已檢查，以查看您有哪些 SAN 項目之後，您找到您有**多個憑證**不具有您需要的所有項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="79da9-213">新憑證要求，必須對您的 CA。</span><span class="sxs-lookup"><span data-stu-id="79da9-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="79da9-214">開啟您 Skype for Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="79da9-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="79da9-215">針對遺漏自動探索服務 SAN (英文） （將-Ca 參數取代您自己的憑證授權單位的路徑）：</span><span class="sxs-lookup"><span data-stu-id="79da9-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="79da9-216">現在，如果您有多個 SIP 網域，您無法使用 AllSipDomain 參數，如上述範例所示。</span><span class="sxs-lookup"><span data-stu-id="79da9-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="79da9-217">您必須改為使用 DomainName 參數。</span><span class="sxs-lookup"><span data-stu-id="79da9-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="79da9-218">當您使用 DomainName 參數時，您已取得最新產品定義 lyncdiscoverinternal 和 lyncdiscover 記錄的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="79da9-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="79da9-219">範例包括 （使用您自己的憑證授權單位路徑取代-Ca 參數）：</span><span class="sxs-lookup"><span data-stu-id="79da9-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="79da9-220">一旦已經由 CA 所產生的新憑證，您要需要指派給他們。</span><span class="sxs-lookup"><span data-stu-id="79da9-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="79da9-221">指派使用 Skype for Business Server 管理命令介面的憑證</span><span class="sxs-lookup"><span data-stu-id="79da9-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="79da9-222">根據所找到 [不要在我需要新上述的認證] 區段，您需要執行**一**項動作。</span><span class="sxs-lookup"><span data-stu-id="79da9-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="79da9-223">如果您有單一憑證 （憑證碼皆相同） 的所有項目則您需要執行此程序：</span><span class="sxs-lookup"><span data-stu-id="79da9-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="79da9-224">如果您有不同的憑證 （憑證碼為完全不同） 中的物件，請改為這執行：</span><span class="sxs-lookup"><span data-stu-id="79da9-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="79da9-225">檢視憑證在 Microsoft Management Console (MMC)</span><span class="sxs-lookup"><span data-stu-id="79da9-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="79da9-226">您可以選擇来查看您使用 [憑證嵌入式管理單元 MMC 的憑證。</span><span class="sxs-lookup"><span data-stu-id="79da9-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="79da9-227">只是將搜尋輸入 MMC，它應該 pop 為應用程式] 選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="79da9-228">若要新增 [憑證嵌入式管理單元，您需要按一下 [**檔案**]，然後**新增/移除嵌入式管理單元-英吋..** （或鍵盤快速鍵**Ctrl + M**也可以運作）。</span><span class="sxs-lookup"><span data-stu-id="79da9-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="79da9-229">**憑證**會是在左窗格中的選項，請在快顯視窗，然後**下一步**中選取它，然後**電腦帳戶**。</span><span class="sxs-lookup"><span data-stu-id="79da9-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="79da9-230">仍在快顯視窗中，在所有的可能性您正在執行此動作具有首頁需的憑證，以查看，因此請保持到**本機電腦**上選取範圍如果是這樣的電腦上。</span><span class="sxs-lookup"><span data-stu-id="79da9-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="79da9-231">如果您正在遠端電腦上，變更為**另一部電腦**的 [選項] 按鈕，然後輸入該電腦的 FQDN 或使用 [**瀏覽**] 按鈕來搜尋 AD 透過該電腦。</span><span class="sxs-lookup"><span data-stu-id="79da9-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="79da9-232">選取之電腦之後, 您需要按一下 [**完成**]，準備好時，然後 **[確定]** 嵌入式管理單元新增至 MMC。</span><span class="sxs-lookup"><span data-stu-id="79da9-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="79da9-233">依序展開 [**憑證**] 區段中，在 MMC 的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="79da9-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="79da9-234">展開 [**個人**] 資料夾，然後再選取 [**憑證**。</span><span class="sxs-lookup"><span data-stu-id="79da9-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="79da9-235">這可讓您查看此存放區中的憑證。</span><span class="sxs-lookup"><span data-stu-id="79da9-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="79da9-236">您需要找出您想要檢視，請將憑證上按一下滑鼠右鍵，然後選擇 [**開啟**。</span><span class="sxs-lookup"><span data-stu-id="79da9-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79da9-237">您要如何知道這是什麼憑證？</span><span class="sxs-lookup"><span data-stu-id="79da9-237">How do you know what certificate this is?</span></span> <span data-ttu-id="79da9-238">它應該是指派給每個伺服器陣列，項目可以是單一憑證或您可能會有不同的項目，例如預設、 內部 Web 服務等的多個憑證，在這種情況下，您可能需要查看多個憑證。</span><span class="sxs-lookup"><span data-stu-id="79da9-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="79da9-239">多個憑證會有相同的憑證指紋。</span><span class="sxs-lookup"><span data-stu-id="79da9-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="79da9-240">一旦您已取得至 [**憑證**] 檢視，選擇 [**詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="79da9-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="79da9-241">這可讓您查看憑證主體名稱，當您選取**主旨**，並會顯示指派的主體名稱及相關聯的內容。</span><span class="sxs-lookup"><span data-stu-id="79da9-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="79da9-242">您也需要檢查的**主體替代名稱**項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="79da9-243">您會發現下列一或多個動作：</span><span class="sxs-lookup"><span data-stu-id="79da9-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="79da9-244">此集區的集區名稱或單一伺服器名稱，如果這不是集區。</span><span class="sxs-lookup"><span data-stu-id="79da9-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="79da9-245">將憑證指派給伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="79da9-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="79da9-246">簡單 URL 記錄，通常為 meet 和 dialin。</span><span class="sxs-lookup"><span data-stu-id="79da9-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="79da9-247">Web 服務內部和 Web 服務外部名稱 （例如，webpool01.contoso.net、 webpool01.contoso.com），根據所做的選擇在拓撲產生器和覆寫的 Web 服務選擇而定。</span><span class="sxs-lookup"><span data-stu-id="79da9-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="79da9-248">如果已經指派，lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄。</span><span class="sxs-lookup"><span data-stu-id="79da9-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="79da9-249">您需要檢查多個憑證，如果您有多個指派 （檢查上面的附註）。</span><span class="sxs-lookup"><span data-stu-id="79da9-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="79da9-250">因此，如果您發現 lyncdiscover。\<sipdomain\>和 lyncdiscoverinternal。\<sipdomain\>記錄，您是否已取得最新產品這已設定。</span><span class="sxs-lookup"><span data-stu-id="79da9-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="79da9-251">您可以關閉 [MMC。</span><span class="sxs-lookup"><span data-stu-id="79da9-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="79da9-252">如果未指派給他們，則需要進行新的憑證要求 （上面所述） 或您需要進行安裝後的要求 (我們建議下列 PowerShell 上方，)。</span><span class="sxs-lookup"><span data-stu-id="79da9-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="79da9-253">設定反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="79da9-253">Configure the reverse proxy</span></span>
<span data-ttu-id="79da9-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="79da9-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="79da9-255">下列步驟並不代表完全後面。</span><span class="sxs-lookup"><span data-stu-id="79da9-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="79da9-256">這是產品的因為在舊版，我們會受到您透過，例如設定 Threat Management Gateway (TMG)，且如果您未使用的您必須找出您自己從該處的版本。</span><span class="sxs-lookup"><span data-stu-id="79da9-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="79da9-257">TMG 不再提供是由 Microsoft 產品中，為，如果您仍然需要將其設定，您可以查看[Lync Server 2013 的步驟](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="79da9-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="79da9-258">但是，下列資訊的目的是更通常有幫助，即使沒有我們可以提供特定的逐步解說步驟剔除有每個反向 proxy 的方法。</span><span class="sxs-lookup"><span data-stu-id="79da9-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="79da9-259">我們有兩個主要的考量事項：</span><span class="sxs-lookup"><span data-stu-id="79da9-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="79da9-260">您進行初始自動探索要求 over HTTPS （其中建議使用）？</span><span class="sxs-lookup"><span data-stu-id="79da9-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="79da9-261">如果您有 web 發行規則，您需要對其進行修改。</span><span class="sxs-lookup"><span data-stu-id="79da9-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="79da9-262">如果您沒有 web 發行規則，您必須建立它。</span><span class="sxs-lookup"><span data-stu-id="79da9-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="79da9-263">如果您透過 HTTP 進行初始自動探索要求，您將需要建立或修改該規則也。</span><span class="sxs-lookup"><span data-stu-id="79da9-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="79da9-264">**重要**Proxy 逾時值是而部署的數字。</span><span class="sxs-lookup"><span data-stu-id="79da9-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="79da9-265">您應該監視您的部署，並修改用戶端的最佳體驗的值。</span><span class="sxs-lookup"><span data-stu-id="79da9-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="79da9-266">您可以將值設定為 200。</span><span class="sxs-lookup"><span data-stu-id="79da9-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="79da9-267">如果您要支援 Lync 行動用戶端環境中，您應該 960 可用於推入通知逾時設定從 Office 365 有 900 的逾時值設定值。</span><span class="sxs-lookup"><span data-stu-id="79da9-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="79da9-268">很有可能需要增加以避免用戶端的逾時值中斷連線時的值是太低，或如果通過 proxy 的連線，請不要中斷，但清除長時間後已中斷連線的用戶端減少數目。</span><span class="sxs-lookup"><span data-stu-id="79da9-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="79da9-269">監視及基準為何平常為您的環境是只精確的方法來決定適當的設定，此值。</span><span class="sxs-lookup"><span data-stu-id="79da9-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="79da9-270">修改現有的 web 發行規則外部自動探索 SAN 及 URL</span><span class="sxs-lookup"><span data-stu-id="79da9-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="79da9-271">開啟您的反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="79da9-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="79da9-272">您需要找出您的 web 發行規則，並選擇 [編輯] 選項 （可能為功能表或根據您的反向 proxy 設定] 索引標籤）。</span><span class="sxs-lookup"><span data-stu-id="79da9-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="79da9-273">應該會指出這個網頁發行規則會套用至某個區域。</span><span class="sxs-lookup"><span data-stu-id="79da9-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="79da9-274">您要修改此規則的連入的網站的要求。</span><span class="sxs-lookup"><span data-stu-id="79da9-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="79da9-275">您要**新增**新的項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="79da9-276">輸入您網站的名稱自動探索 （我們將使用此範例會為 lyncdiscover.contoso.com），然後按一下 **[確定]** 或 [**儲存**，根據您的反向 proxy 的格式。</span><span class="sxs-lookup"><span data-stu-id="79da9-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="79da9-277">您可能需要新的憑證中有自動探索 SAN 項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="79da9-278">需要一併安裝和設定用於根據您的反向 proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="79da9-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="79da9-279">請務必先完成組態時儲存所有項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="79da9-280">如果您的反向 proxy 已**測試**的功能，請使用它來確定一切正常運作。</span><span class="sxs-lookup"><span data-stu-id="79da9-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="79da9-281">現在，您可能需要重複這些步驟，如果您有 Director 或 Director 集區中您的環境 （這表示您有第二個規則）。</span><span class="sxs-lookup"><span data-stu-id="79da9-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="79da9-282">外部自動探索 url 建立 web 發行規則</span><span class="sxs-lookup"><span data-stu-id="79da9-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="79da9-283">開啟您的反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="79da9-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="79da9-284">您需要找出其中介面中您建立網頁發行規則，並選擇 [**新增**] 或 [**建立**] 選項 （可能為功能表或根據您的反向 proxy 設定] 索引標籤）。</span><span class="sxs-lookup"><span data-stu-id="79da9-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="79da9-285">您要尋找要建立新的 web 發行規則的選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="79da9-286">一般而言，您需要輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="79da9-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="79da9-287">**名稱**： 您的規則的名稱</span><span class="sxs-lookup"><span data-stu-id="79da9-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="79da9-288">**規則動作**： 在此情況下是**允許**規則，就會讓通過反向 proxy 的某個項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="79da9-289">您選擇的**發佈**規則或選項就是**單一網站或負載平衡器**。</span><span class="sxs-lookup"><span data-stu-id="79da9-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="79da9-290">這必須是**SSL**進行外部存取，請選擇該選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="79da9-291">您將需要發佈**內部發佈**，路徑，並輸入 FQDN，才在前端集區的負載平衡器 （或 FQDN，Director 集區的負載平衡器如果有的話） 的外部 Web 服務，就是 sfb_pool01.contoso.local 的範例。</span><span class="sxs-lookup"><span data-stu-id="79da9-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="79da9-292">您應該輸入**/**\* 時要發佈、 路徑，但您也需要**轉寄原始主機標頭**。</span><span class="sxs-lookup"><span data-stu-id="79da9-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="79da9-293">會為**公用或外部名稱**詳細資料] 或 [資訊] 選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="79da9-294">這是其中您可以輸入的位置：</span><span class="sxs-lookup"><span data-stu-id="79da9-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="79da9-295">**接受要求**，但它應該是網域名稱。</span><span class="sxs-lookup"><span data-stu-id="79da9-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="79da9-296">對於**名稱**] 中，您應該輸入**lyncdiscover。**</span><span class="sxs-lookup"><span data-stu-id="79da9-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="79da9-297"><sipdomain>（這是外部自動探索服務 URL）。</span><span class="sxs-lookup"><span data-stu-id="79da9-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="79da9-298">現在，如果您正在建立規則的前端集區上的外部 Web 服務 URL，您需要輸入您的前端集區 (例如 lyncwebextpool01.contoso.com) 上的外部 Web 服務 FQDN。</span><span class="sxs-lookup"><span data-stu-id="79da9-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="79da9-299">將**路徑**] 選項，而您將需要輸入**/**\* 以下。</span><span class="sxs-lookup"><span data-stu-id="79da9-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="79da9-300">您需要選取與您最新的公用憑證的**SSL 接聽程式**。</span><span class="sxs-lookup"><span data-stu-id="79da9-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="79da9-301">**驗證委派**應該設定為 [**沒有委派**，但直接用戶端驗證**應**被允許。</span><span class="sxs-lookup"><span data-stu-id="79da9-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="79da9-302">在規則應設定為**所有使用者**。</span><span class="sxs-lookup"><span data-stu-id="79da9-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="79da9-303">這應該是您要建立此規則，並可讓您可繼續進行的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="79da9-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="79da9-304">您要需要確保會轉寄**原始主機標頭**。</span><span class="sxs-lookup"><span data-stu-id="79da9-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="79da9-305">**Web 伺服器**連接埠必須也要設定，您需要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79da9-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="79da9-306">**重新導向至 HTTP 連接埠的要求**和連接埠號碼應該**8080**。</span><span class="sxs-lookup"><span data-stu-id="79da9-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="79da9-307">**重新導向至 SSL 連接埠的要求**和連接埠號碼應該**4443**。</span><span class="sxs-lookup"><span data-stu-id="79da9-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="79da9-308">設定每個項目時，您需要儲存或套用這些項目，，然後您會想要測試規則。</span><span class="sxs-lookup"><span data-stu-id="79da9-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="79da9-309">建立網頁發行規則的連接埠 80 （選用）</span><span class="sxs-lookup"><span data-stu-id="79da9-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="79da9-310">開啟您的反向 proxy 介面。</span><span class="sxs-lookup"><span data-stu-id="79da9-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="79da9-311">您需要找出其中介面中您建立網頁發行規則，並選擇 [**新增**] 或 [**建立**] 選項 （可能為功能表或根據您的反向 proxy 設定] 索引標籤）。</span><span class="sxs-lookup"><span data-stu-id="79da9-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="79da9-312">您要尋找要建立新的 web 發行規則的選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="79da9-313">一般而言，您需要輸入下列資訊：</span><span class="sxs-lookup"><span data-stu-id="79da9-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="79da9-314">**名稱**： 您的規則的名稱</span><span class="sxs-lookup"><span data-stu-id="79da9-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="79da9-315">**規則動作**： 在此情況下是**允許**規則，就會讓通過反向 proxy 的某個項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="79da9-316">您選擇的**發佈**規則或選項就是**單一網站或負載平衡器**。</span><span class="sxs-lookup"><span data-stu-id="79da9-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="79da9-317">這必須是**非安全連線來連線到發行的 Web 伺服器或伺服器陣列**。</span><span class="sxs-lookup"><span data-stu-id="79da9-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="79da9-318">您將需要發佈**內部發佈**，路徑，並輸入 FQDN，前端集區的負載平衡器的**VIP 位址**，範例會為 sfb_pool01.contoso.local。</span><span class="sxs-lookup"><span data-stu-id="79da9-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="79da9-319">您應該輸入**/**\* 時要發佈、 路徑，但您也需要**轉寄原始主機標頭**。</span><span class="sxs-lookup"><span data-stu-id="79da9-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="79da9-320">會為**公用或外部名稱**詳細資料] 或 [資訊] 選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="79da9-321">這是其中您可以輸入的位置：</span><span class="sxs-lookup"><span data-stu-id="79da9-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="79da9-322">**接受要求**，但它應該是網域名稱。</span><span class="sxs-lookup"><span data-stu-id="79da9-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="79da9-323">對於**名稱**] 中，您應該輸入**lyncdiscover。**</span><span class="sxs-lookup"><span data-stu-id="79da9-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="79da9-324"><sipdomain>（這是外部自動探索服務 URL）。</span><span class="sxs-lookup"><span data-stu-id="79da9-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="79da9-325">將**路徑**] 選項，而您將需要輸入**/**\* 以下。</span><span class="sxs-lookup"><span data-stu-id="79da9-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="79da9-326">您需要選取網頁接聽程式，或可讓您建立另一個適用於您的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="79da9-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="79da9-327">**驗證委派**應該設定為 [**沒有委派**，但直接用戶端驗證**不應**被允許。</span><span class="sxs-lookup"><span data-stu-id="79da9-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="79da9-328">在規則應設定為**所有使用者**。</span><span class="sxs-lookup"><span data-stu-id="79da9-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="79da9-329">這應該是您要建立此規則，並可讓您可繼續進行的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="79da9-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="79da9-330">**Web 伺服器**連接埠必須要設定，您需要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79da9-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="79da9-331">**重新導向至 HTTP 連接埠的要求**和連接埠號碼應該**8080**。</span><span class="sxs-lookup"><span data-stu-id="79da9-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="79da9-332">**重新導向至 SSL 連接埠的要求**和連接埠號碼應該**4443**。</span><span class="sxs-lookup"><span data-stu-id="79da9-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="79da9-333">設定每個項目時，您需要儲存或套用這些項目，，然後您會想要測試規則。</span><span class="sxs-lookup"><span data-stu-id="79da9-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="79da9-334">使用混合式部署設定行動的自動探索</span><span class="sxs-lookup"><span data-stu-id="79da9-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="79da9-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="79da9-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="79da9-336">Skype for Business Server 的混合式環境是結合內部部署的環境和 O365 環境。</span><span class="sxs-lookup"><span data-stu-id="79da9-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="79da9-337">當您有 Skype for Business Server 混合式環境中工作時，自動探索服務必須能夠找到其中一個這些環境中的使用者。</span><span class="sxs-lookup"><span data-stu-id="79da9-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="79da9-338">若要讓行動用戶端探索使用者所在的位置，自動探索服務必須設定與新的統一資源定位器 (URL)。</span><span class="sxs-lookup"><span data-stu-id="79da9-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="79da9-339">步驟如下：</span><span class="sxs-lookup"><span data-stu-id="79da9-339">The steps are:</span></span>
  
1. <span data-ttu-id="79da9-340">開啟 Skype for Business Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="79da9-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="79da9-341">執行下列命令以取得您 Skype for Business Server 環境屬性**ProxyFQDN**的值：</span><span class="sxs-lookup"><span data-stu-id="79da9-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="79da9-342">然後，仍在命令介面] 視窗中，執行：</span><span class="sxs-lookup"><span data-stu-id="79da9-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="79da9-343">其中 [identity] 被取代共用 SIP 位址空間的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="79da9-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="79da9-344">測試行動性部署</span><span class="sxs-lookup"><span data-stu-id="79da9-344">Test your Mobility deployment</span></span>
<span data-ttu-id="79da9-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="79da9-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="79da9-346">一旦您已部署 Business Server Mobility Service 和 Skype 的 Skype for Business Server 自動探索服務，您會想要執行測試的交易時，若要確保您的部署工作右邊。</span><span class="sxs-lookup"><span data-stu-id="79da9-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="79da9-347">您可以執行**Test-csucwaconference**若要測試的兩個使用者建立、 加入及會議中進行通訊的能力。</span><span class="sxs-lookup"><span data-stu-id="79da9-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="79da9-348">您將需要兩位使用者 （實數或測試） 和其完整認證來執行這項操作測試。</span><span class="sxs-lookup"><span data-stu-id="79da9-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="79da9-349">此命令將這兩個 skype 適合商務用戶端，以及 Lync Server 2013 用戶端。</span><span class="sxs-lookup"><span data-stu-id="79da9-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="79da9-350">對於商務用 Skype Server 2015 上的 Lync Server 2010 用戶端，您需要執行**Test-csmcxp2pim**來測試。</span><span class="sxs-lookup"><span data-stu-id="79da9-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="79da9-351">您的 Lync Server 2010 使用者仍必須為實際使用者或預先定義的測試使用者，而您將需要其密碼的認證。</span><span class="sxs-lookup"><span data-stu-id="79da9-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="79da9-352">MCX (Mobility Service) 支援舊版的行動用戶端已不再提供 skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="79da9-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="79da9-353">所有目前的 Skype for Business 行動用戶端已使用 Unified Communications Web API (UCWA) 來支援立即訊息 (IM)、 目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="79da9-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="79da9-354">使用舊版用戶端使用 MCX 使用者必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="79da9-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="79da9-355">測試會議 skype for Business 和 Lync 2013 行動用戶端</span><span class="sxs-lookup"><span data-stu-id="79da9-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="79da9-356">在任一安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦上**CsAdministrator**角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="79da9-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="79da9-357">啟動**Skype for Business Server 管理命令介面**（您可能在搜尋中輸入名稱或移到 [**所有程式]** 然後選擇 [它）。</span><span class="sxs-lookup"><span data-stu-id="79da9-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="79da9-358">在命令列，請輸入：</span><span class="sxs-lookup"><span data-stu-id="79da9-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="79da9-359">它也可在指令碼中設定認證，並將其傳遞至 test cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79da9-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="79da9-360">我們有下列的範例。</span><span class="sxs-lookup"><span data-stu-id="79da9-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="79da9-361">測試 Lync 2010 行動用戶端的會議</span><span class="sxs-lookup"><span data-stu-id="79da9-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="79da9-362">MCX (Mobility Service) 支援舊版的行動用戶端已不再提供 skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="79da9-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="79da9-363">所有目前的 Skype for Business 行動用戶端已使用 Unified Communications Web API (UCWA) 來支援立即訊息 (IM)、 目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="79da9-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="79da9-364">使用舊版用戶端使用 MCX 使用者必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="79da9-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="79da9-365">在任一安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦上**CsAdministrator**角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="79da9-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="79da9-366">啟動**Skype for Business Server 管理命令介面**（您可能在搜尋中輸入名稱或移到 [**所有程式]** 然後選擇 [它）。</span><span class="sxs-lookup"><span data-stu-id="79da9-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="79da9-367">在命令列，請輸入：</span><span class="sxs-lookup"><span data-stu-id="79da9-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="79da9-368">它也可在指令碼中設定認證，並將其傳遞至 test cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79da9-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="79da9-369">我們有下列的範例。</span><span class="sxs-lookup"><span data-stu-id="79da9-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="79da9-370">若要檢閱的命令程序此外，您可以查看[Test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps)和[Test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="79da9-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="79da9-371">設定推入通知</span><span class="sxs-lookup"><span data-stu-id="79da9-371">Configure for push notifications</span></span>
<span data-ttu-id="79da9-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="79da9-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="79da9-373">推入通知，形式的徽章、 圖示或提醒，可以傳送至行動裝置，即使 Skype 或 Lync 應用程式是不在作用中。</span><span class="sxs-lookup"><span data-stu-id="79da9-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="79da9-374">但什麼是推入通知？</span><span class="sxs-lookup"><span data-stu-id="79da9-374">But what are push notifications?</span></span> <span data-ttu-id="79da9-375">它們是事件通知，例如新的或未接的 IM 邀請，或收到的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="79da9-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="79da9-376">Skype for Business Server Mobility service 將這些通知傳送至雲端式用 Skype 的商務伺服器推播通知服務，然後將傳送通知到 Microsoft 推播通知服務 (MSNS) for Windows Phone 的使用者。</span><span class="sxs-lookup"><span data-stu-id="79da9-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="79da9-377">這項功能是從 Lync Server 2013 中，不變，但如果您有 Skype for Business Server 時，您會想要執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="79da9-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="79da9-378">Skype for Business Server Edge Server，新增新主機服務提供者，Microsoft Skype for Business Online，然後再設定裝載提供者同盟之間您的組織與 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="79da9-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="79da9-379">執行**Set-cspushnotificationconfiguration** cmdlet 來啟用推入通知。</span><span class="sxs-lookup"><span data-stu-id="79da9-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="79da9-380">根據預設，推入通知被關閉的。</span><span class="sxs-lookup"><span data-stu-id="79da9-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="79da9-381">測試同盟設定和推入通知。</span><span class="sxs-lookup"><span data-stu-id="79da9-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="79da9-382">設定您 Skype for Business Edge Server 推入通知</span><span class="sxs-lookup"><span data-stu-id="79da9-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="79da9-383">是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="79da9-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="79da9-384">啟動**Skype for Business Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="79da9-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="79da9-385">新增 Skype for Business Server 線上裝載提供者。</span><span class="sxs-lookup"><span data-stu-id="79da9-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="79da9-386">做為範例：</span><span class="sxs-lookup"><span data-stu-id="79da9-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="79da9-387">您不能有一個以上的同盟關係與單一主機服務提供者。</span><span class="sxs-lookup"><span data-stu-id="79da9-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="79da9-388">因此，如果您已經設定好裝載提供者已與 sipfed.online.lync.com 的同盟關係，不新增另一台主機服務提供者，即使裝載提供者的身分識別是 SkypeOnline 以外的項目。</span><span class="sxs-lookup"><span data-stu-id="79da9-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="79da9-389">設定裝載提供者同盟之間您的組織和推入通知服務在 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="79da9-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="79da9-390">在命令列，您需要輸入：</span><span class="sxs-lookup"><span data-stu-id="79da9-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="79da9-391">啟用推入通知</span><span class="sxs-lookup"><span data-stu-id="79da9-391">Enable push notifications</span></span>

1. <span data-ttu-id="79da9-392">是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="79da9-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="79da9-393">啟動**Skype for Business Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="79da9-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="79da9-394">啟用推播通知：</span><span class="sxs-lookup"><span data-stu-id="79da9-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="79da9-395">啟用同盟：</span><span class="sxs-lookup"><span data-stu-id="79da9-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="79da9-396">測試同盟和推入通知</span><span class="sxs-lookup"><span data-stu-id="79da9-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="79da9-397">是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="79da9-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="79da9-398">啟動**Skype for Business Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="79da9-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="79da9-399">測試同盟設定：</span><span class="sxs-lookup"><span data-stu-id="79da9-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="79da9-400">做為範例：</span><span class="sxs-lookup"><span data-stu-id="79da9-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="79da9-401">測試推入通知：</span><span class="sxs-lookup"><span data-stu-id="79da9-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="79da9-402">做為範例：</span><span class="sxs-lookup"><span data-stu-id="79da9-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="79da9-403">設定行動性原則</span><span class="sxs-lookup"><span data-stu-id="79da9-403">Configure Mobility policy</span></span>
<span data-ttu-id="79da9-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="79da9-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="79da9-405">您可以與 Skype for Business 伺服器，以判定誰可以使用您的行動性服務，呼叫從公司，voice over IP (VoIP) 或視訊，以及是否 WiFi 將會需要 VoIP 或視訊。</span><span class="sxs-lookup"><span data-stu-id="79da9-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="79da9-406">從公司撥號可讓行動裝置使用者使用其公司電話號碼，而不是其行動電話號碼，撥打和接聽電話時。</span><span class="sxs-lookup"><span data-stu-id="79da9-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="79da9-407">在 [其他線條結尾的人員不會看到該行動使用者的行動電話號碼，以及它可讓行動使用者避免撥出通話費。</span><span class="sxs-lookup"><span data-stu-id="79da9-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="79da9-408">當 VoIP 和視訊設定時，使用者可以採取，並讓 VoIP 通話和視訊。</span><span class="sxs-lookup"><span data-stu-id="79da9-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="79da9-409">WiFi 流量的設定會決定使用者的行動裝置是否必須透過行動數據網路使用 WiFi 網路。</span><span class="sxs-lookup"><span data-stu-id="79da9-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="79da9-410">行動性、 工作，透過呼叫和 VoIP 和視訊功能會啟用所有預設值。</span><span class="sxs-lookup"><span data-stu-id="79da9-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="79da9-411">需要 VoIP 和視訊 WiFi 設定會停用。</span><span class="sxs-lookup"><span data-stu-id="79da9-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="79da9-412">系統管理員必須能夠變更此設定，全域、 網站，或藉由使用者。</span><span class="sxs-lookup"><span data-stu-id="79da9-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="79da9-413">若要能夠使用行動功能和呼叫從公司，使用者必須為：</span><span class="sxs-lookup"><span data-stu-id="79da9-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="79da9-414">啟用 skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79da9-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="79da9-415">啟用企業語音。</span><span class="sxs-lookup"><span data-stu-id="79da9-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="79da9-416">指派 [ **enablemobility]** 選項設為**True**的行動性原則。</span><span class="sxs-lookup"><span data-stu-id="79da9-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="79da9-417">為了能夠使用從公司撥號的使用者，他們也需要為：</span><span class="sxs-lookup"><span data-stu-id="79da9-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="79da9-418">指派語音原則已選取 [**啟用同時電話響鈴**] 選項。</span><span class="sxs-lookup"><span data-stu-id="79da9-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="79da9-419">指派 [ **EnableOutsideVoice**設為**True**的行動性原則。</span><span class="sxs-lookup"><span data-stu-id="79da9-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="79da9-420">未啟用 Enterprise Voice 的使用者可以使用其行動裝置 Skype 對 Skype VoIP 通話或可以在其行動裝置上使用 [按一下以加入連結時加入會議時，如果語音原則設定的適當選項它們關聯使用。</span><span class="sxs-lookup"><span data-stu-id="79da9-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="79da9-421">規劃主題中沒有更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="79da9-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="79da9-422">修改全域行動性原則</span><span class="sxs-lookup"><span data-stu-id="79da9-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="79da9-423">是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="79da9-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="79da9-424">啟動**Skype for Business Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="79da9-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="79da9-425">關閉對存取 Mobility] 和 [從公司撥號全域輸入：</span><span class="sxs-lookup"><span data-stu-id="79da9-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="79da9-426">您可以關閉從公司撥號，而不必關閉行動存取。</span><span class="sxs-lookup"><span data-stu-id="79da9-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="79da9-427">但您無法關閉行動性而不必也關閉從公司撥號。</span><span class="sxs-lookup"><span data-stu-id="79da9-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="79da9-428">如需詳細資訊，請參閱[Set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="79da9-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="79da9-429">依網站修改行動原則</span><span class="sxs-lookup"><span data-stu-id="79da9-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="79da9-430">是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="79da9-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="79da9-431">啟動**Skype for Business Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="79da9-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="79da9-432">您可以建立網站層級原則、 關閉 VoIP 和視訊、 啟用 IP 音訊需要 WiFi 和需要 WiFi 如 IP 視訊由站台。</span><span class="sxs-lookup"><span data-stu-id="79da9-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="79da9-433">類型：</span><span class="sxs-lookup"><span data-stu-id="79da9-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="79da9-434">深入瞭解[New-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="79da9-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="79da9-435">依使用者修改行動原則</span><span class="sxs-lookup"><span data-stu-id="79da9-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="79da9-436">是要安裝**Skype for Business Server 管理命令介面**和**Ocscore**的電腦的**CsAdministrator**角色的成員帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="79da9-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="79da9-437">啟動**Skype for Business Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="79da9-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="79da9-438">建立使用者層級的行動性原則，並關閉行動性和呼叫從使用者的公司。</span><span class="sxs-lookup"><span data-stu-id="79da9-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="79da9-439">類型：</span><span class="sxs-lookup"><span data-stu-id="79da9-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="79da9-440">將含有範例資料進一步範例：</span><span class="sxs-lookup"><span data-stu-id="79da9-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="79da9-441">您可以關閉從公司撥號，而不必關閉行動存取。</span><span class="sxs-lookup"><span data-stu-id="79da9-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="79da9-442">但您無法關閉行動性而不必也關閉從公司撥號。</span><span class="sxs-lookup"><span data-stu-id="79da9-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

