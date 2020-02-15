---
title: 商務伺服器部署中 Skype Skype 連線能力
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
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要： 了解如何與 Skype 消費者連線 Skype for Business Server。 也稱為 Skype 連線。
ms.openlocfilehash: be53acc531d0abb789ae4e622a24dc313483cac6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030446"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a><span data-ttu-id="3fd41-104">商務伺服器部署中 Skype Skype 連線能力</span><span class="sxs-lookup"><span data-stu-id="3fd41-104">Deploy Skype Connectivity in Skype for Business Server</span></span>

<span data-ttu-id="3fd41-105">**摘要：** 了解如何與 Skype 消費者連線 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="3fd41-105">**Summary:** Learn how to connect Skype for Business Server with Skype consumer.</span></span> <span data-ttu-id="3fd41-106">也稱為 Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="3fd41-106">Also known as Skype connectivity.</span></span>
  
<span data-ttu-id="3fd41-107">本文會逐步完成 Skype 連線的部署。</span><span class="sxs-lookup"><span data-stu-id="3fd41-107">This article walks through deployment for Skype Connectivity.</span></span>
  
## <a name="skype-connectivity-overview-for-it-professionals"></a><span data-ttu-id="3fd41-108">適用於 IT 專業人員的 Skype 連線概觀</span><span class="sxs-lookup"><span data-stu-id="3fd41-108">Skype Connectivity Overview for IT Professionals</span></span>

<span data-ttu-id="3fd41-109">Skype 連線提供的功能來搜尋並加入 Skype 使用者的商務使用者 Skype。</span><span class="sxs-lookup"><span data-stu-id="3fd41-109">Skype Connectivity provides Skype for Business users with the ability to search for and add Skype users.</span></span> <span data-ttu-id="3fd41-110">Skype 連線是可讓您啟用同盟和目錄搜尋與 Skype 使用者的商務用 Skype 的功能。</span><span class="sxs-lookup"><span data-stu-id="3fd41-110">Skype Connectivity is a feature of Skype for Business that lets you enable federation and directory search with Skype users.</span></span> <span data-ttu-id="3fd41-111">啟用 Skype 連線後您 Skype for Business 使用者將能夠搜尋並加入 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="3fd41-111">After you enable Skype Connectivity your Skype for Business users will be able to search for and add Skype users.</span></span>
  
## <a name="skype-directory-search"></a><span data-ttu-id="3fd41-112">Skype 目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="3fd41-112">Skype Directory Search</span></span>

<span data-ttu-id="3fd41-113">Skype 目錄搜尋功能提供 Skype 商務使用者搜尋 Skype 連絡人的能力。</span><span class="sxs-lookup"><span data-stu-id="3fd41-113">Skype Directory Search functionality provides Skype for Business users with the ability to search for Skype contacts.</span></span> <span data-ttu-id="3fd41-114">搜尋功能可讓使用者使用下列搜尋：</span><span class="sxs-lookup"><span data-stu-id="3fd41-114">The search functionality lets users search using the following:</span></span>
  
- <span data-ttu-id="3fd41-115">**依顯示名稱，範例 「 John Doe 「 搜尋**-這無法傳回多結果，所以您可能無法找到您要尋找的。</span><span class="sxs-lookup"><span data-stu-id="3fd41-115">**Search by display name, example "John Doe"** - This could return many results, so you might not find what you are looking for.</span></span>
    
- <span data-ttu-id="3fd41-116">**依顯示名稱加上的位置，範例 「 John Doe 中巴塞隆納 「 搜尋**-這會縮小搜尋結果大幅。</span><span class="sxs-lookup"><span data-stu-id="3fd41-116">**Search by display name plus location, example "John Doe in Barcelona"** - This will narrow the results of the search down considerably.</span></span>
    
- <span data-ttu-id="3fd41-117">**透過電子郵件，範例 「 johndoe@outlook.com 「 搜尋**-這應該在大多數情況下，會傳回一個結果完全符合指定的電子郵件的其中一個。</span><span class="sxs-lookup"><span data-stu-id="3fd41-117">**Search by email, example "johndoe@outlook.com"** - This should return one result in most cases; the one that matches the specified email exactly.</span></span> <span data-ttu-id="3fd41-118">但與多個帳戶相關聯的相同的電子郵件時，可能會傳回多個結果。</span><span class="sxs-lookup"><span data-stu-id="3fd41-118">But if the same email is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="3fd41-119">**依電話號碼，範例 「 123-123-1234 「 搜尋**-這應該在大多數情況下，會傳回一個結果一個確實符合指定的電話。</span><span class="sxs-lookup"><span data-stu-id="3fd41-119">**Search by phone number, example "123-123-1234"** - This should return one result in most cases; the one that matches the specified phone exactly.</span></span> <span data-ttu-id="3fd41-120">電話號碼必須包含國碼/地區碼 (亦即 1-xxx-yyy-zzzz)。</span><span class="sxs-lookup"><span data-stu-id="3fd41-120">Phone number must include the country code (i.e. 1-xxx-yyy-zzzz).</span></span> <span data-ttu-id="3fd41-121">與多個帳戶相關聯的相同的電話號碼時，可能會傳回多個結果。</span><span class="sxs-lookup"><span data-stu-id="3fd41-121">If the same phone number is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="3fd41-122">**Skype 名稱範例 「 JohnDoe1456 「 搜尋**-如果找到完全相符，它會傳回為第一個結果。</span><span class="sxs-lookup"><span data-stu-id="3fd41-122">**Search by Skype Name, example "JohnDoe1456"** - If exact match is found, it will be returned as the first result.</span></span> <span data-ttu-id="3fd41-123">其他可能 「 名稱 」 相符項目可能會傳回。</span><span class="sxs-lookup"><span data-stu-id="3fd41-123">Other possible "name" matches may be returned.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3fd41-124">Skype 目錄搜尋必須能夠彼此通訊連接埠 443 上的下列 IP 位址： 104.40.75.246、 23.101.135.34，以及 40.113.86.19。</span><span class="sxs-lookup"><span data-stu-id="3fd41-124">Skype Directory Search must be able to communicate with the following IP addresses on port 443: 104.40.75.246, 23.101.135.34, and 40.113.86.19.</span></span> 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a><span data-ttu-id="3fd41-125">支援的部署矩陣 Skype 目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="3fd41-125">Supported deployment matrix for Skype Directory Search</span></span>

<span data-ttu-id="3fd41-126">下表說明支援的 Skype 目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="3fd41-126">The following table outlines support for Skype Directory Search.</span></span>
  

||<span data-ttu-id="3fd41-127">**Skype for Business Server 前端**</span><span class="sxs-lookup"><span data-stu-id="3fd41-127">**Skype for Business Server Front End**</span></span>|<span data-ttu-id="3fd41-128">**Lync Server 2013 （或更舊版本） 前端**</span><span class="sxs-lookup"><span data-stu-id="3fd41-128">**Lync Server 2013 (or older) Front End**</span></span>|<span data-ttu-id="3fd41-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="3fd41-129">**Comments**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3fd41-130">Skype for Business Server Edge</span><span class="sxs-lookup"><span data-stu-id="3fd41-130">Skype for Business Server Edge</span></span>  <br/> |<span data-ttu-id="3fd41-131">支援</span><span class="sxs-lookup"><span data-stu-id="3fd41-131">Supported</span></span>  <br/> |<span data-ttu-id="3fd41-132">不支援</span><span class="sxs-lookup"><span data-stu-id="3fd41-132">Not Supported</span></span>  <br/> |<span data-ttu-id="3fd41-133">Skype for Business Server 和 Edge 是 Skype 目錄搜尋的必要條件</span><span class="sxs-lookup"><span data-stu-id="3fd41-133">Skype for Business Server and Edge are prerequisites for Skype Directory Search</span></span>  <br/> |
|<span data-ttu-id="3fd41-134">Skype 商務 Server Edge + Lync Server 2013 Edge 部署並排顯示</span><span class="sxs-lookup"><span data-stu-id="3fd41-134">Skype for Business Server Edge + Lync Server 2013 Edge deployed side-by-side</span></span>  <br/> |<span data-ttu-id="3fd41-135">支援</span><span class="sxs-lookup"><span data-stu-id="3fd41-135">Supported</span></span>  <br/> |<span data-ttu-id="3fd41-136">不支援</span><span class="sxs-lookup"><span data-stu-id="3fd41-136">Not Supported</span></span>  <br/> |<span data-ttu-id="3fd41-137">Skype 目錄搜尋流量會經由 Skype 商務伺服器 Edge server。</span><span class="sxs-lookup"><span data-stu-id="3fd41-137">Skype Directory Search traffic flows through Skype for Business Server Edge servers.</span></span> <span data-ttu-id="3fd41-138">同盟流量會通過 edge 由系統管理員設定。</span><span class="sxs-lookup"><span data-stu-id="3fd41-138">Federation traffic goes through edge configured by the administrator.</span></span> <span data-ttu-id="3fd41-139">例如，系統管理員可以選擇繼續傳送到 Lync Server 2013 Edge server，哪些不支援 Skype 目錄搜尋的同盟流量。</span><span class="sxs-lookup"><span data-stu-id="3fd41-139">For example, the administrator could choose to continue to send federation traffic through Lync Server 2013 Edge servers which would not support Skype Directory Search.</span></span>  <br/> |
|<span data-ttu-id="3fd41-140">Lync Server 2013 （或更舊版本） Edge</span><span class="sxs-lookup"><span data-stu-id="3fd41-140">Lync Server 2013 (or older) Edge</span></span>  <br/> |<span data-ttu-id="3fd41-141">不支援</span><span class="sxs-lookup"><span data-stu-id="3fd41-141">Not Supported</span></span>  <br/> |<span data-ttu-id="3fd41-142">不支援</span><span class="sxs-lookup"><span data-stu-id="3fd41-142">Not Supported</span></span>  <br/> ||
   
> [!NOTE]
> <span data-ttu-id="3fd41-143">Skype for Business Server 前端所執行的 Addressbook 服務找到 Edge 的 Edge server 中的 Skype 搜尋連接埠 4443 存在。</span><span class="sxs-lookup"><span data-stu-id="3fd41-143">Addressbook service running on Skype for Business Server Front End finds the Edge by the existence of the Skype Search port 4443 in the Edge server.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3fd41-144">以防客戶有多個網站在其內部部署中，而且如果他們已部署只有一個 Skype for Business Server Edge server/集區]，然後搜尋從所有網站的流量會通過單一可用的 Edge server。</span><span class="sxs-lookup"><span data-stu-id="3fd41-144">In case a customer has multiple sites in their on-premises deployment, and if they have deployed just one Skype for Business Server Edge server/pool, then Search traffic from all sites will go through the single available Edge server.</span></span> <span data-ttu-id="3fd41-145">管理員必須確定從所有網站的集區可以存取已部署的 Skype for Business Server Edge server 集區。</span><span class="sxs-lookup"><span data-stu-id="3fd41-145">The administrator needs to make sure the pools from all sites can access the deployed Skype for Business Server Edge server/pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3fd41-146">Skype graph 服務會要求率超過 15 要求節流搜尋要求從任何內部部署或 Office 365 客戶/秒。</span><span class="sxs-lookup"><span data-stu-id="3fd41-146">Skype graph service will throttle search requests from any on-premises or Office 365 customer if the request rate exceeds 15 requests / second.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3fd41-147">對於大型企業內部部署客戶，網域必須設為允許清單與 Skype 搜尋服務，以允許更高的要求速率。</span><span class="sxs-lookup"><span data-stu-id="3fd41-147">For large enterprise on-premises customers, the domains will need to be whitelisted with the Skype search service to allow higher request rates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3fd41-148">Skype 商務 Server 將調節傳入的要求，，如果在佇列中有太多暫止的要求。</span><span class="sxs-lookup"><span data-stu-id="3fd41-148">Skype for Business Server will throttle incoming requests, if there are too many pending requests in the queue.</span></span> 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a><span data-ttu-id="3fd41-149">用於商務用 Skype Online 在 Office 365 部署的 Skype 連線</span><span class="sxs-lookup"><span data-stu-id="3fd41-149">Deploying Skype Connectivity for Skype for Business Online in Office 365</span></span>

<span data-ttu-id="3fd41-150">Skype 連線也是商務用 Skype 商務 Online，也就是 Office 365 的一部分的功能。</span><span class="sxs-lookup"><span data-stu-id="3fd41-150">Skype Connectivity is also a feature of Skype for Business Online, which is part of Office 365.</span></span> <span data-ttu-id="3fd41-151">您可以在啟用 Skype 連線功能從 Skype for Business 系統管理中心內的 Office 365 入口網站。</span><span class="sxs-lookup"><span data-stu-id="3fd41-151">You can enable the Skype Connectivity feature from the Skype for Business Administration Center within the Office 365 portal.</span></span>
  
<span data-ttu-id="3fd41-152">Office 365 中型企業版、 Office 365 企業版、 Office 365 教育版，和 Office 365 for Government： 登入 Office 365 入口網站，並瀏覽至 Skype for Business 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="3fd41-152">For Office 365 Midsize Business, Office 365 Enterprise, Office 365 Education, and Office 365 for Government: Sign in to the Office 365 portal and navigate to the Skype for Business Administration Center.</span></span> <span data-ttu-id="3fd41-153">移至外部通訊。</span><span class="sxs-lookup"><span data-stu-id="3fd41-153">Go to External Communications.</span></span> <span data-ttu-id="3fd41-154">在 [公用 IM 服務提供者] 下按一下 [啟用]。</span><span class="sxs-lookup"><span data-stu-id="3fd41-154">Under Public IM Service Providers, click Enable.</span></span> <span data-ttu-id="3fd41-155">如果您想要控制個別使用者的存取權 Skype 連線，您可以藉由編輯個別使用者的外部通訊設定來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="3fd41-155">If you want to control individual user access to Skype Connectivity, you can do so by editing individual users' External Communications settings.</span></span>
  
<span data-ttu-id="3fd41-156">針對 Office 365 小型企業進階版： 登入 Office 365，並移至系統\>服務設定\>立即訊息、 會議及會議。</span><span class="sxs-lookup"><span data-stu-id="3fd41-156">For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Settings \> Instant messaging, meetings and conferencing.</span></span> <span data-ttu-id="3fd41-157">開啟外部通訊。</span><span class="sxs-lookup"><span data-stu-id="3fd41-157">Turn on External communications.</span></span> <span data-ttu-id="3fd41-158">功能變數的外部通訊參數會開啟 Skype 連線和與其他使用商務用 Skype 的組織的通訊。</span><span class="sxs-lookup"><span data-stu-id="3fd41-158">The External communications switch turns on both Skype Connectivity and communications with other organizations that use Skype for Business.</span></span>
  
<span data-ttu-id="3fd41-159">如需 Skype 商務 Online 系統管理，請參閱：</span><span class="sxs-lookup"><span data-stu-id="3fd41-159">For more information about Skype for Business Online administration, see:</span></span>
  
- [<span data-ttu-id="3fd41-160">允許使用者連絡外部商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="3fd41-160">Allow users to contact external Skype for Business users</span></span>](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [<span data-ttu-id="3fd41-161">嘗試如果不行 IM Skype for Business 或 Skype 外部連絡人項目</span><span class="sxs-lookup"><span data-stu-id="3fd41-161">What to try if you can't IM Skype for Business or Skype external contacts</span></span>](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [<span data-ttu-id="3fd41-162">在商務用 Skype 中新增連絡人</span><span class="sxs-lookup"><span data-stu-id="3fd41-162">Add a contact in Skype for Business</span></span>](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [<span data-ttu-id="3fd41-163">系統管理員： 設定 Skype 針對個別使用者的企業設定</span><span class="sxs-lookup"><span data-stu-id="3fd41-163">Admins: Configure Skype for Business settings for individual users</span></span>](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a><span data-ttu-id="3fd41-164">Skype for Business Server 部署 Skype 連線</span><span class="sxs-lookup"><span data-stu-id="3fd41-164">Deploying Skype Connectivity for Skype for Business Server</span></span>

<span data-ttu-id="3fd41-165">Skype 商務 Server 使用同盟存取架構可支援用 Skype 的連線。</span><span class="sxs-lookup"><span data-stu-id="3fd41-165">Skype for Business Server uses the federation access architecture to support connectivity with Skype.</span></span> <span data-ttu-id="3fd41-166">此連線可以讓您 Skype for Business Server 使用者加入 Skype。</span><span class="sxs-lookup"><span data-stu-id="3fd41-166">This connectivity enables your Skype for Business Server users to add Skype.</span></span> <span data-ttu-id="3fd41-167">Skype 用戶端也可以將 Skype 新增至其連絡人清單的商務使用者。</span><span class="sxs-lookup"><span data-stu-id="3fd41-167">Skype clients can also add Skype for Business users to their contact list.</span></span> <span data-ttu-id="3fd41-168">根據使用者將能夠使用立即訊息通訊的企業伺服器 skype 行政規定必須設定的原則，請參閱彼此的目前狀態、 和起始音訊和視訊通話。</span><span class="sxs-lookup"><span data-stu-id="3fd41-168">Based on policies administratively set in Skype for Business Server users will be able to communicate using instant messaging, see each other's presence, and initiate audio and video calls.</span></span> <span data-ttu-id="3fd41-169">Skype 連線也是商務用 Skype 線上商務功能，可以啟用 skype 線上商務用 Skype 從客戶 for 商務版系統管理中心內的 Office 365 入口網站。</span><span class="sxs-lookup"><span data-stu-id="3fd41-169">Skype connectivity is also a feature of Skype for Business Online, and can be enabled for Skype for Business Online customers from the Skype for Business Administration Center within the Office 365 portal.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3fd41-170">Skype for Business 伺服器已設定為使用公用立即訊息連線 (PIC) 與 Windows Messenger 連線時，如果您的部署已設定的 Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="3fd41-170">If Skype for Business Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Skype connectivity.</span></span> <span data-ttu-id="3fd41-171">您可能要考慮的唯一變更是重新命名為 Skype 您現有 Messenger PIC 項目。</span><span class="sxs-lookup"><span data-stu-id="3fd41-171">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a><span data-ttu-id="3fd41-172">Skype for Business Server 公用 IM 連線佈建網站已不再提供</span><span class="sxs-lookup"><span data-stu-id="3fd41-172">The Skype for Business Server public IM connectivity provisioning site is no longer available</span></span>

<span data-ttu-id="3fd41-173">先前用來以手動方式佈建商務用 Skype 之間的同盟關係的網站在內部部署和 Skype 不再需要將會關閉 8/15/2019年上。</span><span class="sxs-lookup"><span data-stu-id="3fd41-173">The site that was formerly used to manually provision federation between Skype for Business on-premises deployments and Skype is no longer necessary and will be shut down on 8/15/2019.</span></span> <span data-ttu-id="3fd41-174">與 Skype 同盟現在使用同盟協力廠商探索，也就是相同的機制所需同盟與 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="3fd41-174">Federation with Skype now utilizes federated partner discovery, which is the same mechanism required for federation with Skype for Business Online.</span></span>

<span data-ttu-id="3fd41-175">現在商務版部署任何內部部署商務用 Skype 和 Skype 使用者透過現有的公用 IM 基礎結構之間通訊需要與 Skype for Business Online 相容的內部部署 Edge Server 組態。</span><span class="sxs-lookup"><span data-stu-id="3fd41-175">Communication between any on-premises Skype for Business deployment and Skype users via the existing Public IM infrastructure now requires the on-premises Edge Server configuration to be compatible with Skype for Business Online.</span></span>

> [!NOTE]
> <span data-ttu-id="3fd41-176">大部分的客戶，包括商務用 Skype 同盟的所有部署所不需執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="3fd41-176">No action is needed by most customers, including all deployments that federate with Skype for Business Online.</span></span>
  
<span data-ttu-id="3fd41-177">在內部部署，才能發佈它們主控每個網域同盟 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="3fd41-177">On-premises deployments are required to publish a Federation DNS SRV record for each domain that they host.</span></span> <span data-ttu-id="3fd41-178">使用[DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)規劃指引。</span><span class="sxs-lookup"><span data-stu-id="3fd41-178">Guidance is available in [DNS planning](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning).</span></span> <span data-ttu-id="3fd41-179">每個網域必須解決滿足最上層的後置詞的 FQDN 相符之網域的 DNS SRV 查詢至 edge server。</span><span class="sxs-lookup"><span data-stu-id="3fd41-179">Each domain must resolve by DNS SRV query to an edge server FQDN that satisfies a top-level suffix match of the domain.</span></span> <span data-ttu-id="3fd41-180">例如，假設網域 「 contoso.com 」:</span><span class="sxs-lookup"><span data-stu-id="3fd41-180">For example, consider the domain "contoso.com":</span></span>

|<span data-ttu-id="3fd41-181">**有效的 Fqdn**</span><span class="sxs-lookup"><span data-stu-id="3fd41-181">**Valid FQDNs**</span></span>|<span data-ttu-id="3fd41-182">**Comment**</span><span class="sxs-lookup"><span data-stu-id="3fd41-182">**Comment**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3fd41-183">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3fd41-183">sip.contoso.com</span></span>   ||
|<span data-ttu-id="3fd41-184">sipfed.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3fd41-184">sipfed.contoso.com</span></span>   |<span data-ttu-id="3fd41-185">在每個案例中，正確的 FQDN 必須出現在 SN 或 edge server 上所安裝的外部憑證的 SAN。</span><span class="sxs-lookup"><span data-stu-id="3fd41-185">In each case, the exact FQDN must be present in either the SN or the SAN of the external certificate installed on the edge server.</span></span>   |
|<span data-ttu-id="3fd41-186">access.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3fd41-186">access.contoso.com</span></span>   ||
|<span data-ttu-id="3fd41-187">**不正確的 Fqdn**</span><span class="sxs-lookup"><span data-stu-id="3fd41-187">**Invalid FQDNs**</span></span>|<span data-ttu-id="3fd41-188">**原因**</span><span class="sxs-lookup"><span data-stu-id="3fd41-188">**Reason**</span></span>|
|<span data-ttu-id="3fd41-189">sip.contoso edge.com</span><span class="sxs-lookup"><span data-stu-id="3fd41-189">sip.contoso-edge.com</span></span>   |<span data-ttu-id="3fd41-190">沒有後置詞相符項目。</span><span class="sxs-lookup"><span data-stu-id="3fd41-190">Not a suffix match.</span></span>  |
|<span data-ttu-id="3fd41-191">sip.it.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3fd41-191">sip.it.contoso.com</span></span>   |<span data-ttu-id="3fd41-192">不是最上層的後置字元符合。</span><span class="sxs-lookup"><span data-stu-id="3fd41-192">Not a top-level suffix match.</span></span>   |

<span data-ttu-id="3fd41-193">[憑證](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)規劃可以找到有關外部憑證的進一步指引。</span><span class="sxs-lookup"><span data-stu-id="3fd41-193">Further guidance regarding External Certificates can be found in [Certificate planning](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).</span></span>

#### <a name="faqs"></a><span data-ttu-id="3fd41-194">常見問題集</span><span class="sxs-lookup"><span data-stu-id="3fd41-194">FAQs</span></span>

<span data-ttu-id="3fd41-195">**為什麼要佈建網站正在關閉？**</span><span class="sxs-lookup"><span data-stu-id="3fd41-195">**Why is the provisioning website being shut down?**</span></span>
<span data-ttu-id="3fd41-196">公用 IM (PIC) 佈建在 2006年中已部署的機制 (pic.lync.com) 已不再 scalability，就會關閉 8/15/2019年上。</span><span class="sxs-lookup"><span data-stu-id="3fd41-196">The public IM (PIC) provisioning mechanism (pic.lync.com) that was deployed in 2006 is no longer serviceable and will be shut down on 8/15/2019.</span></span> <span data-ttu-id="3fd41-197">相反地，公用 IM 同盟將會採用相同同盟所使用的模型由 Skype 商務線上，又稱為 「 夥伴探索 」，在內部部署是公開可被探索到由其同盟 DNS SRV 記錄:。</span><span class="sxs-lookup"><span data-stu-id="3fd41-197">Instead, public IM federation will assume the same federation model used by Skype for Business Online, known as "partner discovery", whereby an on-premises deployment is publicly discoverable by its federation DNS SRV record(s).</span></span>

<span data-ttu-id="3fd41-198">**這項變更意思公用 IM 同盟已被取代？**</span><span class="sxs-lookup"><span data-stu-id="3fd41-198">**Does this change mean that Public IM federation is being deprecated?**</span></span>
<span data-ttu-id="3fd41-199">否。</span><span class="sxs-lookup"><span data-stu-id="3fd41-199">No.</span></span> <span data-ttu-id="3fd41-200">公用 IM 同盟會繼續受到支援許多年，可能等到商務用 Skype 內部部署產品達到週期結束。</span><span class="sxs-lookup"><span data-stu-id="3fd41-200">Public IM federation will continue to be supported for many years, probably until the Skype for Business on-premises product reaches end-of-life.</span></span>

<span data-ttu-id="3fd41-201">**我們的公司具有混合關係 （共用的位址空間） 與 Skype for Business Online，我們會影響？**</span><span class="sxs-lookup"><span data-stu-id="3fd41-201">**Our company has a hybrid relationship (shared address space) with Skype for Business Online, are we affected?**</span></span>
<span data-ttu-id="3fd41-202">否，因為您已同盟與 Skype for Business Online，這項變更不會影響您。</span><span class="sxs-lookup"><span data-stu-id="3fd41-202">No, since you are already federating with Skype for Business Online, this change will not affect you.</span></span>
 
<span data-ttu-id="3fd41-203">**這項變更意思我們的公司已啟用商務用 Skype 同盟？**</span><span class="sxs-lookup"><span data-stu-id="3fd41-203">**Does this change mean that our company has to enable federation with Skype for Business Online?**</span></span>
<span data-ttu-id="3fd41-204">否。</span><span class="sxs-lookup"><span data-stu-id="3fd41-204">No.</span></span> <span data-ttu-id="3fd41-205">如果您的 edge 伺服器 proxy 設定不啟用同盟與 Skype for Business Online 的主機服務提供者 (sipfed.online.lync.com) 然後這項變更不會影響的。</span><span class="sxs-lookup"><span data-stu-id="3fd41-205">If your edge server proxy settings do not enable federation with the Skype for Business Online hosting provider (sipfed.online.lync.com) then this change will not affect that.</span></span> <span data-ttu-id="3fd41-206">不過，相同的 DNS 和憑證需求，適用於同盟與 Skype for Business Online 現在也適用於同盟與 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="3fd41-206">However, the same DNS and certificate requirements that apply to federating with Skype for Business Online now also apply to federating with Skype users.</span></span>
 
<span data-ttu-id="3fd41-207">**我們的公司很大，且無法變更因法規/規範/等原因而其 edge 設定...]我們可以做什麼？**</span><span class="sxs-lookup"><span data-stu-id="3fd41-207">**Our company is large and cannot change its edge configuration due to regulatory/compliance/etc reasons … what can we do?**</span></span>
<span data-ttu-id="3fd41-208">無法變更其 edge server 的組態為指定之任何內部部署組織應該連絡產品支援服務儘快。</span><span class="sxs-lookup"><span data-stu-id="3fd41-208">Any on-premises organization that cannot change its edge server configuration as specified should reach out to product support at the earliest opportunity.</span></span>

### <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="3fd41-209">啟用同盟和公共 IM 連線 (PIC)</span><span class="sxs-lookup"><span data-stu-id="3fd41-209">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="3fd41-210">專注在 Skype for Business Server 環境與設定 Skype 連線所需的管理工作。</span><span class="sxs-lookup"><span data-stu-id="3fd41-210">Now focus on the Skype for Business Server environment and administrative tasks required to configure Skype Connectivity.</span></span> <span data-ttu-id="3fd41-211">在這個部分，我們假設管理員已部署 Skype for Business Server 並設定外部存取，也就是 Edge server。</span><span class="sxs-lookup"><span data-stu-id="3fd41-211">In this section, we assume that the administrator has deployed Skype for Business Server and configured external access, also known as Edge servers.</span></span> 
  
<span data-ttu-id="3fd41-212">有需要，才能啟用同盟和 PIC 的三個主要步驟。</span><span class="sxs-lookup"><span data-stu-id="3fd41-212">There are three primary steps required to enable federation and PIC.</span></span> <span data-ttu-id="3fd41-213">例如：</span><span class="sxs-lookup"><span data-stu-id="3fd41-213">These are:</span></span>
  
1. <span data-ttu-id="3fd41-214">設定同盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="3fd41-214">Configure Federation and PIC</span></span>
    
2. <span data-ttu-id="3fd41-215">設定至少一個原則以支援同盟的使用者存取</span><span class="sxs-lookup"><span data-stu-id="3fd41-215">Configure at least one policy to support federated user access</span></span>
    
3. <span data-ttu-id="3fd41-216">設定設定 Skype PIC 提供者</span><span class="sxs-lookup"><span data-stu-id="3fd41-216">Configure the Skype PIC provider setting</span></span>
    
#### <a name="1-configure-federation-and-pic"></a><span data-ttu-id="3fd41-217">1.設定同盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="3fd41-217">1. Configure Federation and PIC</span></span>

<span data-ttu-id="3fd41-218">若要啟用 Skype 使用者能夠與 Skype for 貴組織中的商務使用者需要同盟。</span><span class="sxs-lookup"><span data-stu-id="3fd41-218">Federation is required to enable Skype users to communicate with Skype for Business users in your organization.</span></span> <span data-ttu-id="3fd41-219">公用立即訊息連線 (PIC) 是一種類別的同盟，以及它必須設定為啟用您的 Skype 商務版使用者 Skype 使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3fd41-219">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business users to communicate with Skype users.</span></span> <span data-ttu-id="3fd41-220">同盟和 PIC 已藉由使用 Skype for Business Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="3fd41-220">Federation and PIC are configured by using the Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3fd41-221">PIC 的同盟已不再支援的產品版本之前 Lync Server 2010 ([Office Communications Server 中的 [即時通訊伺服器）。</span><span class="sxs-lookup"><span data-stu-id="3fd41-221">PIC federation is no longer supported by product releases prior to Lync Server 2010 (Live Communication Server, Office Communications Server).</span></span> <span data-ttu-id="3fd41-222">支援的平台 PIC 同盟包含 Skype 商務伺服器、 Lync Server 2013 和 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="3fd41-222">The supported platforms for PIC federation include Skype for Business Server, Lync Server 2013, and Lync Server 2010.</span></span> 
  
<span data-ttu-id="3fd41-223">若要啟用 Skype 使用者能夠與 Skype for 貴組織中的商務使用者需要同盟。</span><span class="sxs-lookup"><span data-stu-id="3fd41-223">Federation is required to enable Skype users to communicate with Skype for Business users in your organization.</span></span> <span data-ttu-id="3fd41-224">公用立即訊息連線 (PIC) 是一種類別的同盟，且它必須經過設定若要啟用 Skype 使用者進行通訊您 Skype for Business Server 使用者。</span><span class="sxs-lookup"><span data-stu-id="3fd41-224">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business Server users to communicate with Skype users.</span></span> <span data-ttu-id="3fd41-225">同盟和 PIC 會透過設定 Edge 設定] 對話方塊的 Skype for Business Server Control Panel 圖所示。</span><span class="sxs-lookup"><span data-stu-id="3fd41-225">Federation and PIC are configured by using the Edge configuration dialog of the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![定義新的 Edge 集區](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> <span data-ttu-id="3fd41-227">EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 屬性必須設為在才能搜尋的公用提供者設定 （請參閱更新版本的指示），則為 true。</span><span class="sxs-lookup"><span data-stu-id="3fd41-227">EnableSkypeIdRouting and EnableSkypeDirectorySearch attributes need to be set to true in the public provider settings (see later instructions) for Search to work.</span></span> 
  
<span data-ttu-id="3fd41-228">如此就完成必須在伺服器執行的管理工作。</span><span class="sxs-lookup"><span data-stu-id="3fd41-228">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="3fd41-229">現在您設定的 Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="3fd41-229">You are now set up for Skype Connectivity.</span></span>
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="3fd41-230">2.設定至少一個原則以支援同盟的使用者存取</span><span class="sxs-lookup"><span data-stu-id="3fd41-230">2. Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="3fd41-231">使用 Skype for Business Server Control Panel，系統管理員必須設定一或多個外部使用者存取原則，以控制是否 Skype 使用者可以與內部 Skype for Business Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="3fd41-231">Using the Skype for Business Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Skype for Business Server users.</span></span>
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a><span data-ttu-id="3fd41-232">3.設定 Skype PIC 提供者設定</span><span class="sxs-lookup"><span data-stu-id="3fd41-232">3. Configure the Skype PIC provider setting</span></span>

<span data-ttu-id="3fd41-233">使用 Skype for Business Server 管理命令介面，系統管理員必須設定商務用 Skype 商務用戶端原則來顯示 Skype 作為其他 PIC 提供者。</span><span class="sxs-lookup"><span data-stu-id="3fd41-233">Using the Skype for Business Server Management Shell, an administrator must configure the Skype for Business client policy to display Skype as an additional PIC provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3fd41-234">公用立即訊息連線 (PIC) 服務提供者的使用者無法參加以 IM 或會議組織中的，直到您也支援公用 IM 連線設定至少一個原則 （步驟 2 中，此程序中更早版本）。</span><span class="sxs-lookup"><span data-stu-id="3fd41-234">Users of the Public Instant Messaging Connectivity (PIC) service providers can't participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span> 
  
<span data-ttu-id="3fd41-235">新安裝您可以藉由啟用 Skype 公用提供者使用 Skype for Business Server Control Panel 圖所示設定 Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="3fd41-235">For new installations you can configure Skype Connectivity by enabling a Skype Public Provider using the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![SIP 同盟提供者](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> <span data-ttu-id="3fd41-237">若要升級至 Skype for Business Server 時，設定 Skype 連線您必須移除並重新加入現有的 Skype 公用提供者。</span><span class="sxs-lookup"><span data-stu-id="3fd41-237">To configure Skype Connectivity when upgrading to Skype for Business Server you must remove and re-add the existing Skype public provider.</span></span> 
  
<span data-ttu-id="3fd41-238">設定 Skype 連線也可完成使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3fd41-238">Configuring Skype Connectivity can also be done using only PowerShell.</span></span> <span data-ttu-id="3fd41-239">若要設定使用 PowerShell 的 Skype 連線：</span><span class="sxs-lookup"><span data-stu-id="3fd41-239">To configure Skype Connectivity using PowerShell:</span></span>
  
1. <span data-ttu-id="3fd41-240">從 Skype for Business Server 前端伺服器中，開啟 Skype for Business Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="3fd41-240">From a Skype for Business Server Front End Server, open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="3fd41-241">執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="3fd41-241">Run the following two commands:</span></span>
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > <span data-ttu-id="3fd41-242">如果您在環境中還沒有 PIC 提供者，並建立新的 PIC 提供者然後您不需要執行移除 CsPublicProvider 指令程式。</span><span class="sxs-lookup"><span data-stu-id="3fd41-242">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the Remove-CsPublicProvider cmdlet.</span></span> 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    <span data-ttu-id="3fd41-243">較不明顯參數可以做什麼？</span><span class="sxs-lookup"><span data-stu-id="3fd41-243">What do the less obvious parameters do?</span></span>
    
   - <span data-ttu-id="3fd41-244">ProxyFqdn： 邊緣位置 Skype 同盟 （擁有/維護 microsoft）</span><span class="sxs-lookup"><span data-stu-id="3fd41-244">ProxyFqdn: location of Skype federation edge (owned/maintained by Microsoft)</span></span>
    
   - <span data-ttu-id="3fd41-245">IconURL： 圖示由 Lync&amp;用來以視覺方式識別 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="3fd41-245">IconURL: icon used by Lync &amp; Skype for Business client to visually identify Skype contacts</span></span>
    
   - <span data-ttu-id="3fd41-246">NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList： 設定這些設定可讓使用者輸入 Skype 使用者 MSAs 而不需要了解 「 裝飾 」 與 「 msn.com 「 非 Microsoft 網域。</span><span class="sxs-lookup"><span data-stu-id="3fd41-246">NameDecorationRoutingDomain and NameDecorationExcludedDomainList: setting these allows users to enter Skype users' MSAs without needing to know about "decorating" non-Microsoft domains with "msn.com".</span></span> <span data-ttu-id="3fd41-247">這就不用輸入 「 使用者 (contoso.com) @msn.com 「 不在 ExcludedDomainList 中的所有網域。</span><span class="sxs-lookup"><span data-stu-id="3fd41-247">This eliminates the need to type "user(contoso.com)@msn.com" for all domains that are NOT in the ExcludedDomainList.</span></span> <span data-ttu-id="3fd41-248">如果網域不在 [排除清單中，[MSA 會自動設定格式 SfB 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3fd41-248">The SfB client will automatically format the MSA if the domain is NOT in the Excluded list.</span></span> <span data-ttu-id="3fd41-249">我們已將最常見的 Microsoft 帳戶網域加入排除清單。</span><span class="sxs-lookup"><span data-stu-id="3fd41-249">We've added the most common Microsoft Account domains to the excluded list.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="3fd41-250">公用提供者必須移除，而且如果變更新加入。</span><span class="sxs-lookup"><span data-stu-id="3fd41-250">Public Provider must be removed and added new if changes are made.</span></span> <span data-ttu-id="3fd41-251">允許沒有就地變更。</span><span class="sxs-lookup"><span data-stu-id="3fd41-251">No in-place changes are allowed.</span></span> 
  
     > [!NOTE]
     > <span data-ttu-id="3fd41-252">在 Lync Server 2013 CU5 中新增&amp;Lync 桌面用戶端的 Office 2013 SP1、 NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善其中加入 Skype 連絡人所需的 Lync 使用者 「 裝飾 」 以找出並將它們路由傳送到 Skype 非 Microsoft 網域的情況 (格式為： user(contoso.com)@msn.com)。</span><span class="sxs-lookup"><span data-stu-id="3fd41-252">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to "decorate" non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="3fd41-253">這些新的設定將允許的地址使用者的自動格式設定的對話方塊中輸入 「 新增 Skype 連絡人 」 與 NameDecorationRoutingDomain （這應設為 msn.com） 如果它不含 NameDecorationExcludedDomainList （中的網域我們目前可支援 msn.com、 live.com、 Hotmail.com、 outlook.com）。</span><span class="sxs-lookup"><span data-stu-id="3fd41-253">These new settings will allow automatic formatting of the address user's enter in the "Add Skype contact" dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span> 
  
3. <span data-ttu-id="3fd41-254">從商務用 Skype 用戶端使用者現在可以搜尋並加入 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="3fd41-254">From a Skype for Business client users can now search for and add a Skype user.</span></span>
    
## <a name="clients-and-interoperability-matrix"></a><span data-ttu-id="3fd41-255">用戶端和互通性矩陣</span><span class="sxs-lookup"><span data-stu-id="3fd41-255">Clients and Interoperability Matrix</span></span>

<span data-ttu-id="3fd41-256">下表概述 interop 最新版的 Skype 消費者和商務用 Skype 的最新版本之間的狀態。</span><span class="sxs-lookup"><span data-stu-id="3fd41-256">The following table outlines the status of interop between the latest version of Skype consumer and the latest version of Skype for Business.</span></span>
  

|<span data-ttu-id="3fd41-257">**Skype 用戶端**</span><span class="sxs-lookup"><span data-stu-id="3fd41-257">**Skype Clients**</span></span>|<span data-ttu-id="3fd41-258">**新增連絡人、 IM、 目前狀態、 音訊及視訊通話**</span><span class="sxs-lookup"><span data-stu-id="3fd41-258">**Add contacts, IM, presence, audio, and video calling**</span></span>|<span data-ttu-id="3fd41-259">**Comment**</span><span class="sxs-lookup"><span data-stu-id="3fd41-259">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3fd41-260">Skype Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="3fd41-260">Skype Windows Desktop</span></span>  <br/> |<span data-ttu-id="3fd41-261">7.6 或更高版本、 Windows XP 和更高版本</span><span class="sxs-lookup"><span data-stu-id="3fd41-261">7.6 or higher, Windows XP and higher</span></span>  <br/> |<span data-ttu-id="3fd41-262">**新增**： 新增支援在 Windows XP 和 Windows Vista **（需要最新的用戶端版本 7.26 或更高版本）** 上執行的 Windows 用 Skype 用戶端</span><span class="sxs-lookup"><span data-stu-id="3fd41-262">**NEW**: Support added for Windows Skype client running on Windows XP, and Windows Vista **(requires latest client version 7.26 or higher)**</span></span> <br/> |
|<span data-ttu-id="3fd41-263">Skype 行動裝置-Android 手機和平板電腦</span><span class="sxs-lookup"><span data-stu-id="3fd41-263">Skype Mobile - Android Phone and Tablet</span></span>  <br/> |<span data-ttu-id="3fd41-264">6.19 或更新版本，執行 Android 作業系統版本 4.0.3 或更高層級</span><span class="sxs-lookup"><span data-stu-id="3fd41-264">6.19 or higher, running Android OS version 4.0.3 or higher</span></span>  <br/> |<span data-ttu-id="3fd41-265">低規格裝置可能不支援視訊通話</span><span class="sxs-lookup"><span data-stu-id="3fd41-265">Low spec devices may not support video calling</span></span>  <br/> |
|<span data-ttu-id="3fd41-266">Skype 行動裝置-iOS</span><span class="sxs-lookup"><span data-stu-id="3fd41-266">Skype Mobile - iOS</span></span>  <br/> |<span data-ttu-id="3fd41-267">6.11 或更新版本，在 IOS 7 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3fd41-267">6.11 or higher, on IOS 7 or higher</span></span>  <br/> |<span data-ttu-id="3fd41-268">不支援已 4th 產生 iPhone 4 和更早版本、 iPod 和更早，iPad 1st 產生</span><span class="sxs-lookup"><span data-stu-id="3fd41-268">Not supported are iPhone 4 and earlier, iPod 4th generation and earlier, iPad 1st generation</span></span>  <br/> |
|<span data-ttu-id="3fd41-269">Skype Mac</span><span class="sxs-lookup"><span data-stu-id="3fd41-269">Skype Mac</span></span>  <br/> |<span data-ttu-id="3fd41-270">7.19 或更新版本，在 Mac OS X 10.9 (Mavericks) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3fd41-270">7.19 or higher, on Mac OS X 10.9 (Mavericks) or higher</span></span>  <br/> |<span data-ttu-id="3fd41-271">需要 Mac OSX 「 10.9 或更高版本</span><span class="sxs-lookup"><span data-stu-id="3fd41-271">Requires Mac OSX 10.9 or higher</span></span>  <br/> |
|<span data-ttu-id="3fd41-272">Skype Universal Windows 應用程式 (Windows 10) 桌面和行動裝置</span><span class="sxs-lookup"><span data-stu-id="3fd41-272">Skype Universal Windows App (Windows 10) Desktop and Mobile</span></span>  <br/> |<span data-ttu-id="3fd41-273">Windows 10 (Redstone 1 更新或更新版本)</span><span class="sxs-lookup"><span data-stu-id="3fd41-273">Windows 10 (Redstone 1 update or later)</span></span>  <br/> |<span data-ttu-id="3fd41-274">Windows 通用應用程式會在新增 interop 支援 Fall 2016 收到更新</span><span class="sxs-lookup"><span data-stu-id="3fd41-274">Windows Universal App will receive update in Fall 2016 adding interop support</span></span>  <br/> |
   
<span data-ttu-id="3fd41-275">下表概述 interop 最新版的商務用 Skype 和 Skype 消費者的最新版本之間的狀態。</span><span class="sxs-lookup"><span data-stu-id="3fd41-275">The following table outlines the status of interop between the latest version of Skype for Business and the latest version of Skype consumer.</span></span> 
  
|<span data-ttu-id="3fd41-276">**用戶端**</span><span class="sxs-lookup"><span data-stu-id="3fd41-276">**Client**</span></span>|<span data-ttu-id="3fd41-277">**Skype 目錄搜尋，並新增連絡人**</span><span class="sxs-lookup"><span data-stu-id="3fd41-277">**Skype Directory Search and Add Contacts**</span></span>|<span data-ttu-id="3fd41-278">**Skype A / V，IM interop**</span><span class="sxs-lookup"><span data-stu-id="3fd41-278">**Skype A/V, IM interop**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3fd41-279">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="3fd41-279">Skype for Business</span></span>  <br/> |<span data-ttu-id="3fd41-280">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-280">Yes</span></span>  <br/> |<span data-ttu-id="3fd41-281">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-281">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-282">Mac 版商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="3fd41-282">Skype for Business on Mac</span></span>  <br/> |<span data-ttu-id="3fd41-283">可以新增 （沒有搜尋）</span><span class="sxs-lookup"><span data-stu-id="3fd41-283">Can add (no search)</span></span>  <br/> |<span data-ttu-id="3fd41-284">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-284">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-285">Lync Desktop 2013</span><span class="sxs-lookup"><span data-stu-id="3fd41-285">Lync Desktop 2013</span></span>  <br/> |<span data-ttu-id="3fd41-286">可以新增 （沒有搜尋）</span><span class="sxs-lookup"><span data-stu-id="3fd41-286">Can add (no search)</span></span>  <br/> |<span data-ttu-id="3fd41-287">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-287">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-288">Lync Web App 的線上和內部部署</span><span class="sxs-lookup"><span data-stu-id="3fd41-288">Lync Web App - online and on-premises</span></span>  <br/> |<span data-ttu-id="3fd41-289">不適用</span><span class="sxs-lookup"><span data-stu-id="3fd41-289">N/A</span></span>  <br/> |<span data-ttu-id="3fd41-290">不適用</span><span class="sxs-lookup"><span data-stu-id="3fd41-290">N/A</span></span>  <br/> |
|<span data-ttu-id="3fd41-291">Lync 行動裝置-Windows Phone</span><span class="sxs-lookup"><span data-stu-id="3fd41-291">Lync Mobile - Windows Phone</span></span>  <br/> |<span data-ttu-id="3fd41-292">即將推出</span><span class="sxs-lookup"><span data-stu-id="3fd41-292">Coming Soon</span></span>  <br/> |<span data-ttu-id="3fd41-293">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-293">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-294">Lync 行動裝置-Android</span><span class="sxs-lookup"><span data-stu-id="3fd41-294">Lync Mobile - Android</span></span>  <br/> |<span data-ttu-id="3fd41-295">即將推出</span><span class="sxs-lookup"><span data-stu-id="3fd41-295">Coming Soon</span></span>  <br/> |<span data-ttu-id="3fd41-296">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-296">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-297">Lync 行動裝置-iOS</span><span class="sxs-lookup"><span data-stu-id="3fd41-297">Lync Mobile - iOS</span></span>  <br/> |<span data-ttu-id="3fd41-298">即將推出</span><span class="sxs-lookup"><span data-stu-id="3fd41-298">Coming Soon</span></span>  <br/> |<span data-ttu-id="3fd41-299">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-299">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-300">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="3fd41-300">Lync Room System</span></span>  <br/> |<span data-ttu-id="3fd41-301">即將推出</span><span class="sxs-lookup"><span data-stu-id="3fd41-301">Coming Soon</span></span>  <br/> |<span data-ttu-id="3fd41-302">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-302">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-303">Lync 現代化應用程式 (Win 8.1)</span><span class="sxs-lookup"><span data-stu-id="3fd41-303">Lync Modern App (Win 8.1)</span></span>  <br/> |<span data-ttu-id="3fd41-304">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-304">Yes</span></span>  <br/> |<span data-ttu-id="3fd41-305">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-305">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-306">Lync Mac 2011</span><span class="sxs-lookup"><span data-stu-id="3fd41-306">Lync Mac 2011</span></span>  <br/> |<span data-ttu-id="3fd41-307">可以新增 （沒有搜尋）</span><span class="sxs-lookup"><span data-stu-id="3fd41-307">Can add (no search)</span></span>  <br/> |<span data-ttu-id="3fd41-308">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-308">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-309">Lync 桌面 2010</span><span class="sxs-lookup"><span data-stu-id="3fd41-309">Lync Desktop 2010</span></span>  <br/> |<span data-ttu-id="3fd41-310">可以新增 （沒有搜尋）</span><span class="sxs-lookup"><span data-stu-id="3fd41-310">Can add (no search)</span></span>  <br/> |<span data-ttu-id="3fd41-311">是</span><span class="sxs-lookup"><span data-stu-id="3fd41-311">Yes</span></span>  <br/> |
|<span data-ttu-id="3fd41-312">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="3fd41-312">Lync Phone Edition</span></span>  <br/> |<span data-ttu-id="3fd41-313">不適用</span><span class="sxs-lookup"><span data-stu-id="3fd41-313">N/A</span></span>  <br/> |<span data-ttu-id="3fd41-314">不適用</span><span class="sxs-lookup"><span data-stu-id="3fd41-314">N/A</span></span>  <br/> |
|<span data-ttu-id="3fd41-315">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="3fd41-315">Lync Attendant</span></span>  <br/> |<span data-ttu-id="3fd41-316">不適用</span><span class="sxs-lookup"><span data-stu-id="3fd41-316">N/A</span></span>  <br/> |<span data-ttu-id="3fd41-317">不適用</span><span class="sxs-lookup"><span data-stu-id="3fd41-317">N/A</span></span>  <br/> |
   

