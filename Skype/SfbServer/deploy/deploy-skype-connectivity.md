---
title: 在商務用 Skype Server 中部署 Skype Connectivity
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
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要：瞭解如何使用 Skype 客戶程式來連接商務用 Skype Server。 也稱為「Skype 連線」。
ms.openlocfilehash: 9c5f7f5c275b60c5b59dc43fe0a9b4a5c9b1514b
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574062"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a><span data-ttu-id="64979-104">在商務用 Skype Server 中部署 Skype Connectivity</span><span class="sxs-lookup"><span data-stu-id="64979-104">Deploy Skype Connectivity in Skype for Business Server</span></span>

<span data-ttu-id="64979-105">**摘要：** 瞭解如何使用 Skype 客戶程式來連接商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="64979-105">**Summary:** Learn how to connect Skype for Business Server with Skype consumer.</span></span> <span data-ttu-id="64979-106">也稱為「Skype 連線」。</span><span class="sxs-lookup"><span data-stu-id="64979-106">Also known as Skype connectivity.</span></span>
  
<span data-ttu-id="64979-107">本文將引導您進行 Skype 連線的部署。</span><span class="sxs-lookup"><span data-stu-id="64979-107">This article walks through deployment for Skype Connectivity.</span></span>
  
## <a name="skype-connectivity-overview-for-it-professionals"></a><span data-ttu-id="64979-108">適用于 IT 專業人員的 Skype 連線能力一覽</span><span class="sxs-lookup"><span data-stu-id="64979-108">Skype Connectivity Overview for IT Professionals</span></span>

<span data-ttu-id="64979-109">Skype Connectivity 為商務用 Skype 使用者提供的功能可搜尋及新增 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="64979-109">Skype Connectivity provides Skype for Business users with the ability to search for and add Skype users.</span></span> <span data-ttu-id="64979-110">Skype 連線功能是商務用 Skype 的功能，可讓您使用 Skype 使用者啟用同盟及目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="64979-110">Skype Connectivity is a feature of Skype for Business that lets you enable federation and directory search with Skype users.</span></span> <span data-ttu-id="64979-111">啟用 Skype 連線功能之後，商務用 Skype 使用者就能夠搜尋並新增 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="64979-111">After you enable Skype Connectivity your Skype for Business users will be able to search for and add Skype users.</span></span>
  
## <a name="skype-directory-search"></a><span data-ttu-id="64979-112">Skype 目錄搜尋</span><span class="sxs-lookup"><span data-stu-id="64979-112">Skype Directory Search</span></span>

<span data-ttu-id="64979-113">Skype 目錄搜尋功能可讓商務用 Skype 使用者能夠搜尋 Skype 連絡人。</span><span class="sxs-lookup"><span data-stu-id="64979-113">Skype Directory Search functionality provides Skype for Business users with the ability to search for Skype contacts.</span></span> <span data-ttu-id="64979-114">搜尋功能可讓使用者使用下列專案進行搜尋：</span><span class="sxs-lookup"><span data-stu-id="64979-114">The search functionality lets users search using the following:</span></span>
  
- <span data-ttu-id="64979-115">**依顯示名稱搜尋，例如「John Doe** 」-這可能會傳回許多結果，所以您可能不會找到您要尋找的專案。</span><span class="sxs-lookup"><span data-stu-id="64979-115">**Search by display name, example "John Doe"** - This could return many results, so you might not find what you are looking for.</span></span>
    
- <span data-ttu-id="64979-116">**依顯示名稱加上位置進行搜尋，範例「John Doe 為巴塞羅納** 」-這會大幅縮小搜尋的結果。</span><span class="sxs-lookup"><span data-stu-id="64979-116">**Search by display name plus location, example "John Doe in Barcelona"** - This will narrow the results of the search down considerably.</span></span>
    
- <span data-ttu-id="64979-117">**依電子郵件搜尋，範例 "johndoe@outlook.com"** -在大多數情況下，這應該會傳回一個結果。與指定之電子郵件完全相符的專案。</span><span class="sxs-lookup"><span data-stu-id="64979-117">**Search by email, example "johndoe@outlook.com"** - This should return one result in most cases; the one that matches the specified email exactly.</span></span> <span data-ttu-id="64979-118">不過，如果相同的電子郵件與一個以上的帳戶相關聯，則可能會傳回多個結果。</span><span class="sxs-lookup"><span data-stu-id="64979-118">But if the same email is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="64979-119">**依電話號碼搜尋（範例 "123-123-1234"），** 在大多數情況下，這應該會傳回一個結果。完全符合指定電話的一種。</span><span class="sxs-lookup"><span data-stu-id="64979-119">**Search by phone number, example "123-123-1234"** - This should return one result in most cases; the one that matches the specified phone exactly.</span></span> <span data-ttu-id="64979-120">電話號碼必須包含國家/地區碼 (例如 1-xxx-yyy-zzzz) 。</span><span class="sxs-lookup"><span data-stu-id="64979-120">Phone number must include the country code (i.e. 1-xxx-yyy-zzzz).</span></span> <span data-ttu-id="64979-121">如果相同的電話號碼與一個以上的帳戶相關聯，則可能會傳回多個結果。</span><span class="sxs-lookup"><span data-stu-id="64979-121">If the same phone number is associated with more than one account, multiple results may be returned.</span></span>
    
- <span data-ttu-id="64979-122">**依 Skype 名稱搜尋，例如 "JohnDoe1456"** -如果找到完全相符的，它會傳回為第一個結果。</span><span class="sxs-lookup"><span data-stu-id="64979-122">**Search by Skype Name, example "JohnDoe1456"** - If exact match is found, it will be returned as the first result.</span></span> <span data-ttu-id="64979-123">可能會傳回其他可能的「名稱」相符專案。</span><span class="sxs-lookup"><span data-stu-id="64979-123">Other possible "name" matches may be returned.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="64979-124">Skype 目錄搜尋必須能夠與下列埠443上的 IP 位址通訊：104.40.75.246、23.101.135.34 及40.113.86.19。</span><span class="sxs-lookup"><span data-stu-id="64979-124">Skype Directory Search must be able to communicate with the following IP addresses on port 443: 104.40.75.246, 23.101.135.34, and 40.113.86.19.</span></span> 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a><span data-ttu-id="64979-125">支援 Skype 目錄搜尋的部署矩陣</span><span class="sxs-lookup"><span data-stu-id="64979-125">Supported deployment matrix for Skype Directory Search</span></span>

<span data-ttu-id="64979-126">下表概述 Skype 目錄搜尋的支援。</span><span class="sxs-lookup"><span data-stu-id="64979-126">The following table outlines support for Skype Directory Search.</span></span>
  

||<span data-ttu-id="64979-127">**商務用 Skype Server 前端**</span><span class="sxs-lookup"><span data-stu-id="64979-127">**Skype for Business Server Front End**</span></span>|<span data-ttu-id="64979-128">**Lync Server 2013 (或舊版) 前端**</span><span class="sxs-lookup"><span data-stu-id="64979-128">**Lync Server 2013 (or older) Front End**</span></span>|<span data-ttu-id="64979-129">**Comments**</span><span class="sxs-lookup"><span data-stu-id="64979-129">**Comments**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="64979-130">商務用 Skype Server Edge</span><span class="sxs-lookup"><span data-stu-id="64979-130">Skype for Business Server Edge</span></span>  <br/> |<span data-ttu-id="64979-131">支援</span><span class="sxs-lookup"><span data-stu-id="64979-131">Supported</span></span>  <br/> |<span data-ttu-id="64979-132">不支援</span><span class="sxs-lookup"><span data-stu-id="64979-132">Not Supported</span></span>  <br/> |<span data-ttu-id="64979-133">商務用 skype Server 和 Edge 是 Skype 目錄搜尋的必要條件</span><span class="sxs-lookup"><span data-stu-id="64979-133">Skype for Business Server and Edge are prerequisites for Skype Directory Search</span></span>  <br/> |
|<span data-ttu-id="64979-134">商務用 Skype Server Edge + Lync Server 2013 Edge 並排部署</span><span class="sxs-lookup"><span data-stu-id="64979-134">Skype for Business Server Edge + Lync Server 2013 Edge deployed side-by-side</span></span>  <br/> |<span data-ttu-id="64979-135">支援</span><span class="sxs-lookup"><span data-stu-id="64979-135">Supported</span></span>  <br/> |<span data-ttu-id="64979-136">不支援</span><span class="sxs-lookup"><span data-stu-id="64979-136">Not Supported</span></span>  <br/> |<span data-ttu-id="64979-137">透過商務用 Skype Server Edge server 流過 skype 目錄搜尋流量。</span><span class="sxs-lookup"><span data-stu-id="64979-137">Skype Directory Search traffic flows through Skype for Business Server Edge servers.</span></span> <span data-ttu-id="64979-138">同盟流量會透過系統管理員設定的 edge 進行。</span><span class="sxs-lookup"><span data-stu-id="64979-138">Federation traffic goes through edge configured by the administrator.</span></span> <span data-ttu-id="64979-139">例如，管理員可以選擇繼續透過 Lync Server 2013 Edge server 傳送同盟流量，這不會支援 Skype 目錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="64979-139">For example, the administrator could choose to continue to send federation traffic through Lync Server 2013 Edge servers which would not support Skype Directory Search.</span></span>  <br/> |
|<span data-ttu-id="64979-140">Lync Server 2013 (或舊版) Edge</span><span class="sxs-lookup"><span data-stu-id="64979-140">Lync Server 2013 (or older) Edge</span></span>  <br/> |<span data-ttu-id="64979-141">不支援</span><span class="sxs-lookup"><span data-stu-id="64979-141">Not Supported</span></span>  <br/> |<span data-ttu-id="64979-142">不支援</span><span class="sxs-lookup"><span data-stu-id="64979-142">Not Supported</span></span>  <br/> ||
   
> [!NOTE]
> <span data-ttu-id="64979-143">在商務用 Skype Server 前端執行的 Addressbook 服務會在 Edge server 中存在 Skype 搜尋埠4443，以找出 Edge。</span><span class="sxs-lookup"><span data-stu-id="64979-143">Addressbook service running on Skype for Business Server Front End finds the Edge by the existence of the Skype Search port 4443 in the Edge server.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64979-144">若客戶在其內部部署中有多個網站，而且他們只部署了一個商務用 Skype Server Edge server/集區，則從所有網站搜尋流量都會透過單一可用的 Edge server。</span><span class="sxs-lookup"><span data-stu-id="64979-144">In case a customer has multiple sites in their on-premises deployment, and if they have deployed just one Skype for Business Server Edge server/pool, then Search traffic from all sites will go through the single available Edge server.</span></span> <span data-ttu-id="64979-145">管理員需要確定所有網站的集區都可以存取已部署的商務用 Skype Server Edge server/集區。</span><span class="sxs-lookup"><span data-stu-id="64979-145">The administrator needs to make sure the pools from all sites can access the deployed Skype for Business Server Edge server/pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64979-146">如果要求率超過15個要求/秒，則 Skype graph 服務會節流任何內部部署或 Microsoft 365 或 Office 365 客戶的搜尋要求。</span><span class="sxs-lookup"><span data-stu-id="64979-146">Skype graph service will throttle search requests from any on-premises or Microsoft 365 or Office 365 customer if the request rate exceeds 15 requests / second.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64979-147">針對大型企業內部部署客戶，您必須使用 Skype 搜尋服務將網域新增至 allowlist，以允許更高的要求率。</span><span class="sxs-lookup"><span data-stu-id="64979-147">For large enterprise on-premises customers, the domains will need to be added to an allowlist with the Skype search service to allow higher request rates.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64979-148">如果佇列中有太多擱置要求，商務用 Skype Server 會節流傳入的要求。</span><span class="sxs-lookup"><span data-stu-id="64979-148">Skype for Business Server will throttle incoming requests, if there are too many pending requests in the queue.</span></span> 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a><span data-ttu-id="64979-149">為商務用 Skype Online 部署 Skype Connectivity</span><span class="sxs-lookup"><span data-stu-id="64979-149">Deploying Skype Connectivity for Skype for Business Online</span></span>

<span data-ttu-id="64979-150">Skype Connectivity 也是商務用 Skype Online 的功能，也就是 Microsoft 365 和 Office 365 的一部分。</span><span class="sxs-lookup"><span data-stu-id="64979-150">Skype Connectivity is also a feature of Skype for Business Online, which is part of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="64979-151">您可以從 Microsoft 365 系統管理中心內的商務用 Skype 系統管理中心啟用 Skype Connectivity 功能。</span><span class="sxs-lookup"><span data-stu-id="64979-151">You can enable the Skype Connectivity feature from the Skype for Business Administration Center within the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="64979-152">Microsoft 365 中型企業版、Office 365 企業版、Microsoft 365 教育版和 Office 365 for 政府：登入 Microsoft 365 系統管理中心，並流覽至商務用 Skype 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="64979-152">For Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education, and Office 365 for Government: Sign in to the Microsoft 365 admin center and navigate to the Skype for Business Administration Center.</span></span> <span data-ttu-id="64979-153">移至 [外部通訊]。</span><span class="sxs-lookup"><span data-stu-id="64979-153">Go to External Communications.</span></span> <span data-ttu-id="64979-154">在 [公用 IM 服務提供者] 底下，按一下 [啟用]。</span><span class="sxs-lookup"><span data-stu-id="64979-154">Under Public IM Service Providers, click Enable.</span></span> <span data-ttu-id="64979-155">如果您想要控制個別使用者對 Skype 連線的存取，您可以編輯個別使用者的外部通訊設定來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="64979-155">If you want to control individual user access to Skype Connectivity, you can do so by editing individual users' External Communications settings.</span></span>
  
<span data-ttu-id="64979-156">適用于 Office 365 Small Business Premium：登入 Office 365，然後移至 [系統管理] \> 服務設定 \> 立即訊息、會議和會議。</span><span class="sxs-lookup"><span data-stu-id="64979-156">For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Settings \> Instant messaging, meetings and conferencing.</span></span> <span data-ttu-id="64979-157">開啟外部通訊。</span><span class="sxs-lookup"><span data-stu-id="64979-157">Turn on External communications.</span></span> <span data-ttu-id="64979-158">外部通訊參數會同時開啟 Skype 連線，以及與使用商務用 Skype 的其他組織進行通訊。</span><span class="sxs-lookup"><span data-stu-id="64979-158">The External communications switch turns on both Skype Connectivity and communications with other organizations that use Skype for Business.</span></span>
  
<span data-ttu-id="64979-159">如需商務用 Skype Online 管理的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="64979-159">For more information about Skype for Business Online administration, see:</span></span>
  
- [<span data-ttu-id="64979-160">允許使用者連絡外部商務用 Skype 使用者</span><span class="sxs-lookup"><span data-stu-id="64979-160">Allow users to contact external Skype for Business users</span></span>](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [<span data-ttu-id="64979-161">當您無法 IM 商務用 Skype 或 Skype 外部連絡人時，要嘗試的專案</span><span class="sxs-lookup"><span data-stu-id="64979-161">What to try if you can't IM Skype for Business or Skype external contacts</span></span>](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [<span data-ttu-id="64979-162">在商務用 Skype 中新增連絡人</span><span class="sxs-lookup"><span data-stu-id="64979-162">Add a contact in Skype for Business</span></span>](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [<span data-ttu-id="64979-163">Admins：設定個別使用者的商務用 Skype 設定</span><span class="sxs-lookup"><span data-stu-id="64979-163">Admins: Configure Skype for Business settings for individual users</span></span>](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a><span data-ttu-id="64979-164">為商務用 Skype Server 部署 Skype Connectivity</span><span class="sxs-lookup"><span data-stu-id="64979-164">Deploying Skype Connectivity for Skype for Business Server</span></span>

<span data-ttu-id="64979-165">商務用 skype Server 使用同盟存取架構，以支援與 Skype 的連線。</span><span class="sxs-lookup"><span data-stu-id="64979-165">Skype for Business Server uses the federation access architecture to support connectivity with Skype.</span></span> <span data-ttu-id="64979-166">這種連線功能可讓商務用 Skype Server 使用者新增 Skype。</span><span class="sxs-lookup"><span data-stu-id="64979-166">This connectivity enables your Skype for Business Server users to add Skype.</span></span> <span data-ttu-id="64979-167">Skype 用戶端也可以將商務用 Skype 使用者新增至其連絡人清單。</span><span class="sxs-lookup"><span data-stu-id="64979-167">Skype clients can also add Skype for Business users to their contact list.</span></span> <span data-ttu-id="64979-168">根據在商務用 Skype Server 中設定的原則，使用者將能夠使用立即訊息進行通訊、查看彼此的狀態，以及啟動音訊和視頻通話。</span><span class="sxs-lookup"><span data-stu-id="64979-168">Based on policies administratively set in Skype for Business Server users will be able to communicate using instant messaging, see each other's presence, and initiate audio and video calls.</span></span> <span data-ttu-id="64979-169">Skype 連線功能也是商務用 Skype Online 的功能，可在 Microsoft 365 系統管理中心內的商務用 Skype 系統管理中心啟用商務用 Skype Online 客戶。</span><span class="sxs-lookup"><span data-stu-id="64979-169">Skype connectivity is also a feature of Skype for Business Online, and can be enabled for Skype for Business Online customers from the Skype for Business Administration Center within the Microsoft 365 admin center.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64979-170">如果已使用公用立即訊息連線將商務用 Skype 伺服器設定為與 Windows Messenger 連線，則 (PIC) 上，您的部署已設定為使用 Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="64979-170">If Skype for Business Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Skype connectivity.</span></span> <span data-ttu-id="64979-171">您可能想要考慮的唯一變更是將現有的 Messenger PIC 專案重新命名為 Skype。</span><span class="sxs-lookup"><span data-stu-id="64979-171">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a><span data-ttu-id="64979-172">已無法再使用商務用 Skype Server 公用 IM 連線布建網站</span><span class="sxs-lookup"><span data-stu-id="64979-172">The Skype for Business Server public IM connectivity provisioning site is no longer available</span></span>

<span data-ttu-id="64979-173">原來曾用來在商務用 Skype 內部部署與 Skype 之間手動布建同盟的網站，在8/15/2019 上不再需要並將其關閉。</span><span class="sxs-lookup"><span data-stu-id="64979-173">The site that was formerly used to manually provision federation between Skype for Business on-premises deployments and Skype is no longer necessary and will be shut down on 8/15/2019.</span></span> <span data-ttu-id="64979-174">與 Skype 的同盟現在會利用同盟協力廠商探索，這是與商務用 Skype Online 同盟所需的相同機制。</span><span class="sxs-lookup"><span data-stu-id="64979-174">Federation with Skype now utilizes federated partner discovery, which is the same mechanism required for federation with Skype for Business Online.</span></span>

<span data-ttu-id="64979-175">透過現有的公用 IM 基礎結構，任何內部部署商務用 Skype 部署與 Skype 使用者之間的通訊現在，都需要內部部署 Edge Server 設定與商務用 Skype Online 相容。</span><span class="sxs-lookup"><span data-stu-id="64979-175">Communication between any on-premises Skype for Business deployment and Skype users via the existing Public IM infrastructure now requires the on-premises Edge Server configuration to be compatible with Skype for Business Online.</span></span>

> [!NOTE]
> <span data-ttu-id="64979-176">大多數客戶不需要執行任何動作，包括與商務用 Skype Online 同盟的所有部署。</span><span class="sxs-lookup"><span data-stu-id="64979-176">No action is needed by most customers, including all deployments that federate with Skype for Business Online.</span></span>
  
<span data-ttu-id="64979-177">內部部署是針對其所裝載的每個網域，發佈同盟 DNS SRV 記錄所需的。</span><span class="sxs-lookup"><span data-stu-id="64979-177">On-premises deployments are required to publish a Federation DNS SRV record for each domain that they host.</span></span> <span data-ttu-id="64979-178">在 [DNS 規劃](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)中提供指導方針。</span><span class="sxs-lookup"><span data-stu-id="64979-178">Guidance is available in [DNS planning](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning).</span></span> <span data-ttu-id="64979-179">每個網域都必須由 DNS SRV 查詢解析為滿足網域的最上層尾碼比對之 edge server FQDN。</span><span class="sxs-lookup"><span data-stu-id="64979-179">Each domain must resolve by DNS SRV query to an edge server FQDN that satisfies a top-level suffix match of the domain.</span></span> <span data-ttu-id="64979-180">例如，請考慮網域 "contoso.com"：</span><span class="sxs-lookup"><span data-stu-id="64979-180">For example, consider the domain "contoso.com":</span></span>

|<span data-ttu-id="64979-181">**有效 Fqdn**</span><span class="sxs-lookup"><span data-stu-id="64979-181">**Valid FQDNs**</span></span>|<span data-ttu-id="64979-182">**Comment**</span><span class="sxs-lookup"><span data-stu-id="64979-182">**Comment**</span></span>|
|:-----|:-----|
|<span data-ttu-id="64979-183">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64979-183">sip.contoso.com</span></span>   ||
|<span data-ttu-id="64979-184">sipfed.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64979-184">sipfed.contoso.com</span></span>   |<span data-ttu-id="64979-185">在每個案例中，確切的 FQDN 都必須存在於安裝在 edge server 上之外部憑證的 SN 或 SAN 中。</span><span class="sxs-lookup"><span data-stu-id="64979-185">In each case, the exact FQDN must be present in either the SN or the SAN of the external certificate installed on the edge server.</span></span>   |
|<span data-ttu-id="64979-186">access.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64979-186">access.contoso.com</span></span>   ||
|<span data-ttu-id="64979-187">**不正確 Fqdn**</span><span class="sxs-lookup"><span data-stu-id="64979-187">**Invalid FQDNs**</span></span>|<span data-ttu-id="64979-188">**原因**</span><span class="sxs-lookup"><span data-stu-id="64979-188">**Reason**</span></span>|
|<span data-ttu-id="64979-189">sip.contoso-edge.com</span><span class="sxs-lookup"><span data-stu-id="64979-189">sip.contoso-edge.com</span></span>   |<span data-ttu-id="64979-190">非尾碼相符。</span><span class="sxs-lookup"><span data-stu-id="64979-190">Not a suffix match.</span></span>  |
|<span data-ttu-id="64979-191">sip.it.contoso.com</span><span class="sxs-lookup"><span data-stu-id="64979-191">sip.it.contoso.com</span></span>   |<span data-ttu-id="64979-192">不是最上層尾碼相符。</span><span class="sxs-lookup"><span data-stu-id="64979-192">Not a top-level suffix match.</span></span>   |

<span data-ttu-id="64979-193">您可以在 [認證規劃](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)中找到外部憑證的相關指引。</span><span class="sxs-lookup"><span data-stu-id="64979-193">Further guidance regarding External Certificates can be found in [Certificate planning](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).</span></span>

#### <a name="faqs"></a><span data-ttu-id="64979-194">常見問題集</span><span class="sxs-lookup"><span data-stu-id="64979-194">FAQs</span></span>

<span data-ttu-id="64979-195">**為何要關閉布建網站？**</span><span class="sxs-lookup"><span data-stu-id="64979-195">**Why is the provisioning website being shut down?**</span></span>
<span data-ttu-id="64979-196">在2006中部署的公用 IM (PIC) 布建機制 (pic.lync.com) 已無法繼續維護，且會在8/15/2019 時關閉。</span><span class="sxs-lookup"><span data-stu-id="64979-196">The public IM (PIC) provisioning mechanism (pic.lync.com) that was deployed in 2006 is no longer serviceable and will be shut down on 8/15/2019.</span></span> <span data-ttu-id="64979-197">相反地，公用 IM 同盟會採用商務用 Skype Online （稱為「夥伴探索」）所使用的相同同盟模型，因此內部部署部署會透過其同盟 DNS SRV 記錄公開探索 (s) 。</span><span class="sxs-lookup"><span data-stu-id="64979-197">Instead, public IM federation will assume the same federation model used by Skype for Business Online, known as "partner discovery", whereby an on-premises deployment is publicly discoverable by its federation DNS SRV record(s).</span></span>

<span data-ttu-id="64979-198">**這種變更意味著公用 IM 同盟被取代？**</span><span class="sxs-lookup"><span data-stu-id="64979-198">**Does this change mean that Public IM federation is being deprecated?**</span></span>
<span data-ttu-id="64979-199">否。</span><span class="sxs-lookup"><span data-stu-id="64979-199">No.</span></span> <span data-ttu-id="64979-200">公用 IM 同盟將繼續支援許多年，直到商務用 Skype 內部部署產品到達生命週期結束時為止。</span><span class="sxs-lookup"><span data-stu-id="64979-200">Public IM federation will continue to be supported for many years, probably until the Skype for Business on-premises product reaches end-of-life.</span></span>

<span data-ttu-id="64979-201">**我們公司與商務用 Skype Online) 共用位址空間的混合式關聯性 (，我們受到影響嗎？**</span><span class="sxs-lookup"><span data-stu-id="64979-201">**Our company has a hybrid relationship (shared address space) with Skype for Business Online, are we affected?**</span></span>
<span data-ttu-id="64979-202">不需要，因為您已與商務用 Skype Online 進行同盟，所以此變更不會影響您。</span><span class="sxs-lookup"><span data-stu-id="64979-202">No, since you are already federating with Skype for Business Online, this change will not affect you.</span></span>
 
<span data-ttu-id="64979-203">**這種變更是否意味著我們的公司必須啟用與商務用 Skype Online 的同盟？**</span><span class="sxs-lookup"><span data-stu-id="64979-203">**Does this change mean that our company has to enable federation with Skype for Business Online?**</span></span>
<span data-ttu-id="64979-204">否。</span><span class="sxs-lookup"><span data-stu-id="64979-204">No.</span></span> <span data-ttu-id="64979-205">如果您的 edge server proxy 設定沒有啟用與商務用 Skype Online 主機服務提供者的同盟 (sipfed.online.lync.com) 則此變更不會影響。</span><span class="sxs-lookup"><span data-stu-id="64979-205">If your edge server proxy settings do not enable federation with the Skype for Business Online hosting provider (sipfed.online.lync.com) then this change will not affect that.</span></span> <span data-ttu-id="64979-206">不過，與商務用 Skype Online 進行同盟的相同 DNS 和憑證需求現在也適用于與 Skype 使用者的聯盟。</span><span class="sxs-lookup"><span data-stu-id="64979-206">However, the same DNS and certificate requirements that apply to federating with Skype for Business Online now also apply to federating with Skype users.</span></span>
 
<span data-ttu-id="64979-207">**我們公司很大，無法變更其 edge 設定，因為規定/合規性/etc 原因 .。。我們可以做什麼？**</span><span class="sxs-lookup"><span data-stu-id="64979-207">**Our company is large and cannot change its edge configuration due to regulatory/compliance/etc reasons … what can we do?**</span></span>
<span data-ttu-id="64979-208">任何內部部署組織若不能根據指定變更其 edge server 設定，應儘早到達產品支援服務。</span><span class="sxs-lookup"><span data-stu-id="64979-208">Any on-premises organization that cannot change its edge server configuration as specified should reach out to product support at the earliest opportunity.</span></span>

### <a name="enabling-federation-and-public-im-connectivity-pic"></a><span data-ttu-id="64979-209">啟用同盟和公用 IM 連線 (PIC) </span><span class="sxs-lookup"><span data-stu-id="64979-209">Enabling Federation and Public IM Connectivity (PIC)</span></span>

<span data-ttu-id="64979-210">現在將重點放在商務用 Skype 伺服器環境上，以及設定 Skype Connectivity 所需的管理工作。</span><span class="sxs-lookup"><span data-stu-id="64979-210">Now focus on the Skype for Business Server environment and administrative tasks required to configure Skype Connectivity.</span></span> <span data-ttu-id="64979-211">在本節中，我們假設系統管理員已部署商務用 Skype 伺服器及設定的外部存取（也稱為 Edge server）。</span><span class="sxs-lookup"><span data-stu-id="64979-211">In this section, we assume that the administrator has deployed Skype for Business Server and configured external access, also known as Edge servers.</span></span> 
  
<span data-ttu-id="64979-212">有三個主要步驟必須啟用同盟和 PIC。</span><span class="sxs-lookup"><span data-stu-id="64979-212">There are three primary steps required to enable federation and PIC.</span></span> <span data-ttu-id="64979-213">例如：</span><span class="sxs-lookup"><span data-stu-id="64979-213">These are:</span></span>
  
1. <span data-ttu-id="64979-214">設定同盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="64979-214">Configure Federation and PIC</span></span>
    
2. <span data-ttu-id="64979-215">設定至少一個原則以支援同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="64979-215">Configure at least one policy to support federated user access</span></span>
    
3. <span data-ttu-id="64979-216">設定 Skype PIC 提供者設定</span><span class="sxs-lookup"><span data-stu-id="64979-216">Configure the Skype PIC provider setting</span></span>
    
#### <a name="1-configure-federation-and-pic"></a><span data-ttu-id="64979-217">1. 設定同盟和 PIC</span><span class="sxs-lookup"><span data-stu-id="64979-217">1. Configure Federation and PIC</span></span>

<span data-ttu-id="64979-218">需要同盟才能讓 Skype 使用者能夠與您組織中的商務用 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="64979-218">Federation is required to enable Skype users to communicate with Skype for Business users in your organization.</span></span> <span data-ttu-id="64979-219">公用立即訊息連線 (PIC) 是同盟的類別，必須設定為讓商務用 Skype 使用者能夠與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="64979-219">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business users to communicate with Skype users.</span></span> <span data-ttu-id="64979-220">同盟和 PIC 是透過商務用 Skype Server 控制台進行設定。</span><span class="sxs-lookup"><span data-stu-id="64979-220">Federation and PIC are configured by using the Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64979-221">Lync Server 2010 (Live Communication Server，Office 通訊伺服器) 之前，產品版本已不再支援 PIC 同盟。</span><span class="sxs-lookup"><span data-stu-id="64979-221">PIC federation is no longer supported by product releases prior to Lync Server 2010 (Live Communication Server, Office Communications Server).</span></span> <span data-ttu-id="64979-222">支援的 PIC 同盟平臺包括商務用 Skype 伺服器、Lync Server 2013 和 Lync Server 2010。</span><span class="sxs-lookup"><span data-stu-id="64979-222">The supported platforms for PIC federation include Skype for Business Server, Lync Server 2013, and Lync Server 2010.</span></span> 
  
<span data-ttu-id="64979-223">需要同盟才能讓 Skype 使用者能夠與您組織中的商務用 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="64979-223">Federation is required to enable Skype users to communicate with Skype for Business users in your organization.</span></span> <span data-ttu-id="64979-224">公用立即訊息連線 (PIC) 是同盟的類別，必須設定為讓商務用 Skype 伺服器使用者能夠與 Skype 使用者通訊。</span><span class="sxs-lookup"><span data-stu-id="64979-224">Public Instant Messaging Connectivity (PIC) is a class of federation, and it must be configured to enable your Skype for Business Server users to communicate with Skype users.</span></span> <span data-ttu-id="64979-225">同盟和 PIC 是使用商務用 Skype Server [控制台] 的 [Edge 設定] 對話方塊進行設定，如圖所示。</span><span class="sxs-lookup"><span data-stu-id="64979-225">Federation and PIC are configured by using the Edge configuration dialog of the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![定義新的 Edge 集區](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> <span data-ttu-id="64979-227">EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 屬性必須設定為 true 中的公用提供者設定 (請參閱後續指示) 供搜尋正常運作。</span><span class="sxs-lookup"><span data-stu-id="64979-227">EnableSkypeIdRouting and EnableSkypeDirectorySearch attributes need to be set to true in the public provider settings (see later instructions) for Search to work.</span></span> 
  
<span data-ttu-id="64979-228">這會完成必須在伺服器上執行的管理工作。</span><span class="sxs-lookup"><span data-stu-id="64979-228">This completes the administrative tasks that must be performed on the server.</span></span> <span data-ttu-id="64979-229">您現在已設定 Skype 連線。</span><span class="sxs-lookup"><span data-stu-id="64979-229">You are now set up for Skype Connectivity.</span></span>
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a><span data-ttu-id="64979-230">2. 設定至少一個原則以支援同盟使用者存取</span><span class="sxs-lookup"><span data-stu-id="64979-230">2. Configure at least one policy to support federated user access</span></span>

<span data-ttu-id="64979-231">使用商務用 Skype Server 控制台，管理員必須設定一或多個外部使用者存取原則，以控制 Skype 使用者是否可以與內部商務用 Skype Server 使用者共同作業。</span><span class="sxs-lookup"><span data-stu-id="64979-231">Using the Skype for Business Server Control Panel, an administrator must configure one or more external user access policies to control whether Skype users can collaborate with internal Skype for Business Server users.</span></span>
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a><span data-ttu-id="64979-232">3. 設定 Skype PIC 提供者設定</span><span class="sxs-lookup"><span data-stu-id="64979-232">3. Configure the Skype PIC provider setting</span></span>

<span data-ttu-id="64979-233">使用商務用 Skype Server 管理命令介面，管理員必須設定商務用 Skype 用戶端原則，將 Skype 顯示為其他 PIC 提供者。</span><span class="sxs-lookup"><span data-stu-id="64979-233">Using the Skype for Business Server Management Shell, an administrator must configure the Skype for Business client policy to display Skype as an additional PIC provider.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64979-234"> (PIC) 服務提供者的公用立即訊息連線使用者無法參與您組織中的 IM 或會議，除非您在此程式之前設定至少一個原則 (步驟2，) 以支援公用 IM 連線能力。</span><span class="sxs-lookup"><span data-stu-id="64979-234">Users of the Public Instant Messaging Connectivity (PIC) service providers can't participate in IM or conferences in your organization until you also configure at least one policy (step 2, earlier in this procedure) to support public IM connectivity.</span></span> 
  
<span data-ttu-id="64979-235">針對全新安裝，您可以使用商務用 Skype Server 控制台（如圖所示）來啟用 Skype 公用服務，以設定 Skype 連線性。</span><span class="sxs-lookup"><span data-stu-id="64979-235">For new installations you can configure Skype Connectivity by enabling a Skype Public Provider using the Skype for Business Server Control Panel as shown in the figure.</span></span>
  
![SIP 同盟提供者](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> <span data-ttu-id="64979-237">若要在升級至商務用 Skype 伺服器時設定 Skype 連線，您必須移除並重新新增現有的 Skype 公用提供者。</span><span class="sxs-lookup"><span data-stu-id="64979-237">To configure Skype Connectivity when upgrading to Skype for Business Server you must remove and re-add the existing Skype public provider.</span></span> 
  
<span data-ttu-id="64979-238">您也可以僅使用 PowerShell 來設定 Skype 連線能力。</span><span class="sxs-lookup"><span data-stu-id="64979-238">Configuring Skype Connectivity can also be done using only PowerShell.</span></span> <span data-ttu-id="64979-239">設定使用 PowerShell: 的 Skype 連線能力</span><span class="sxs-lookup"><span data-stu-id="64979-239">To configure Skype Connectivity using PowerShell:</span></span>
  
1. <span data-ttu-id="64979-240">從商務用 Skype Server 前端伺服器開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="64979-240">From a Skype for Business Server Front End Server, open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="64979-241">執行下列兩個命令：</span><span class="sxs-lookup"><span data-stu-id="64979-241">Run the following two commands:</span></span>
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > <span data-ttu-id="64979-242">如果您的環境中已沒有 PIC 提供者，且正在建立新的 PIC 提供者，則不需要執行 Remove-CsPublicProvider Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="64979-242">If you do not already have a PIC provider in your environment and are creating a new PIC provider then you do not need to run the Remove-CsPublicProvider cmdlet.</span></span> 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    <span data-ttu-id="64979-243">不太明顯的參數會有什麼用處？</span><span class="sxs-lookup"><span data-stu-id="64979-243">What do the less obvious parameters do?</span></span>
    
   - <span data-ttu-id="64979-244">ProxyFqdn： Microsoft 所擁有/維護 (Skype 同盟 edge 的位置) </span><span class="sxs-lookup"><span data-stu-id="64979-244">ProxyFqdn: location of Skype federation edge (owned/maintained by Microsoft)</span></span>
    
   - <span data-ttu-id="64979-245">IconURL： Lync &amp; 商務用 skype 用戶端用來以視覺方式識別 Skype 連絡人的圖示</span><span class="sxs-lookup"><span data-stu-id="64979-245">IconURL: icon used by Lync &amp; Skype for Business client to visually identify Skype contacts</span></span>
    
   - <span data-ttu-id="64979-246">NameDecorationRoutingDomain 與 NameDecorationExcludedDomainList：設定這些功能可讓使用者輸入 Skype 使用者的 MSAs，而不需要知道「修飾」非 Microsoft 網域與「msn.com」。</span><span class="sxs-lookup"><span data-stu-id="64979-246">NameDecorationRoutingDomain and NameDecorationExcludedDomainList: setting these allows users to enter Skype users' MSAs without needing to know about "decorating" non-Microsoft domains with "msn.com".</span></span> <span data-ttu-id="64979-247">這樣就不需要為 ExcludedDomainList 以外的所有網域輸入「使用者 (contoso.com) @msn .com」。</span><span class="sxs-lookup"><span data-stu-id="64979-247">This eliminates the need to type "user(contoso.com)@msn.com" for all domains that are NOT in the ExcludedDomainList.</span></span> <span data-ttu-id="64979-248">當網域不在排除清單中時，SfB 用戶端會自動格式化 MSA。</span><span class="sxs-lookup"><span data-stu-id="64979-248">The SfB client will automatically format the MSA if the domain is NOT in the Excluded list.</span></span> <span data-ttu-id="64979-249">我們已將最常見的 Microsoft 帳戶網域新增至排除清單。</span><span class="sxs-lookup"><span data-stu-id="64979-249">We've added the most common Microsoft Account domains to the excluded list.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="64979-250">若要進行變更，必須移除公用提供者並新增新的提供者。</span><span class="sxs-lookup"><span data-stu-id="64979-250">Public Provider must be removed and added new if changes are made.</span></span> <span data-ttu-id="64979-251">不允許就地變更。</span><span class="sxs-lookup"><span data-stu-id="64979-251">No in-place changes are allowed.</span></span> 
  
     > [!NOTE]
     > <span data-ttu-id="64979-252">已新增于 Office 2013 中的 lync Server 2013 CU5 &amp; lync 桌面用戶端 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善了 Lync 使用者新增所需的 skype 連絡人，以識別並路由傳送至 skype (： user (contoso.com) @msn .com) 的情況。</span><span class="sxs-lookup"><span data-stu-id="64979-252">Added in Lync Server 2013 CU5 &amp; Lync desktop client in Office 2013 SP1, the NameDecorationRoutingDomain and NameDecorationExcludedDomainList improve the situation where Lync users adding Skype contacts needed to "decorate" non-Microsoft domains to identify and route them to Skype (the format of: user(contoso.com)@msn.com).</span></span> <span data-ttu-id="64979-253">在 [新增 Skype 連絡人] 對話方塊中，這些新設定將允許自動設定位址使用者輸入的格式，NameDecorationRoutingDomain (應設定為 msn.com) 如果不包含 NameDecorationExcludedDomainList 中的網域 (我們目前可支援 msn.com、live.com、Hotmail.com、outlook.com) 。</span><span class="sxs-lookup"><span data-stu-id="64979-253">These new settings will allow automatic formatting of the address user's enter in the "Add Skype contact" dialog box with the NameDecorationRoutingDomain (which should be set to msn.com) if it does not contain the domains in the NameDecorationExcludedDomainList (we currently can support msn.com, live.com, Hotmail.com, outlook.com).</span></span> 
  
3. <span data-ttu-id="64979-254">從商務用 Skype 用戶端使用者現在可以搜尋並新增 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="64979-254">From a Skype for Business client users can now search for and add a Skype user.</span></span>
    
## <a name="clients-and-interoperability-matrix"></a><span data-ttu-id="64979-255">用戶端和互通性清單</span><span class="sxs-lookup"><span data-stu-id="64979-255">Clients and Interoperability Matrix</span></span>

<span data-ttu-id="64979-256">下表概述最新版 Skype 使用者和商務用 Skype 的最新版本之間的交互操作狀態。</span><span class="sxs-lookup"><span data-stu-id="64979-256">The following table outlines the status of interop between the latest version of Skype consumer and the latest version of Skype for Business.</span></span>
  

|<span data-ttu-id="64979-257">**Skype 用戶端**</span><span class="sxs-lookup"><span data-stu-id="64979-257">**Skype Clients**</span></span>|<span data-ttu-id="64979-258">**新增連絡人、IM、顯示狀態、音訊和影片通話**</span><span class="sxs-lookup"><span data-stu-id="64979-258">**Add contacts, IM, presence, audio, and video calling**</span></span>|<span data-ttu-id="64979-259">**Comment**</span><span class="sxs-lookup"><span data-stu-id="64979-259">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="64979-260">Skype Windows 桌面</span><span class="sxs-lookup"><span data-stu-id="64979-260">Skype Windows Desktop</span></span>  <br/> |<span data-ttu-id="64979-261">7.6 或更高版本、Windows XP 及更高版本</span><span class="sxs-lookup"><span data-stu-id="64979-261">7.6 or higher, Windows XP and higher</span></span>  <br/> |<span data-ttu-id="64979-262">**新**：新增支援在 windows XP 上執行的 windows Skype 用戶端，以及 windows Vista **(需要最新的用戶端版本7.26 或更高版本)**</span><span class="sxs-lookup"><span data-stu-id="64979-262">**NEW**: Support added for Windows Skype client running on Windows XP, and Windows Vista **(requires latest client version 7.26 or higher)**</span></span> <br/> |
|<span data-ttu-id="64979-263">Skype Mobile-Android 手機和平板電腦</span><span class="sxs-lookup"><span data-stu-id="64979-263">Skype Mobile - Android Phone and Tablet</span></span>  <br/> |<span data-ttu-id="64979-264">6.19 或更高版本，執行 Android OS 版本4.0.3 或更高版本</span><span class="sxs-lookup"><span data-stu-id="64979-264">6.19 or higher, running Android OS version 4.0.3 or higher</span></span>  <br/> |<span data-ttu-id="64979-265">低規格裝置可能不支援影片通話</span><span class="sxs-lookup"><span data-stu-id="64979-265">Low spec devices may not support video calling</span></span>  <br/> |
|<span data-ttu-id="64979-266">Skype Mobile-iOS</span><span class="sxs-lookup"><span data-stu-id="64979-266">Skype Mobile - iOS</span></span>  <br/> |<span data-ttu-id="64979-267">IOS 7 或更高版本上的6.11 或更高版本</span><span class="sxs-lookup"><span data-stu-id="64979-267">6.11 or higher, on IOS 7 or higher</span></span>  <br/> |<span data-ttu-id="64979-268">不支援的版本為 iPhone 4 及更早版本、iPod 第四代及更早的「iPad 第一代」</span><span class="sxs-lookup"><span data-stu-id="64979-268">Not supported are iPhone 4 and earlier, iPod 4th generation and earlier, iPad 1st generation</span></span>  <br/> |
|<span data-ttu-id="64979-269">Skype Mac</span><span class="sxs-lookup"><span data-stu-id="64979-269">Skype Mac</span></span>  <br/> |<span data-ttu-id="64979-270">7.19 或更高版本，Mac OS X 10.9 (Mavericks) 或更高版本</span><span class="sxs-lookup"><span data-stu-id="64979-270">7.19 or higher, on Mac OS X 10.9 (Mavericks) or higher</span></span>  <br/> |<span data-ttu-id="64979-271">需要 Mac OSX 10.9 或更高版本</span><span class="sxs-lookup"><span data-stu-id="64979-271">Requires Mac OSX 10.9 or higher</span></span>  <br/> |
|<span data-ttu-id="64979-272"> (Windows 10) 桌面和行動裝置的 Skype 通用 Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="64979-272">Skype Universal Windows App (Windows 10) Desktop and Mobile</span></span>  <br/> |<span data-ttu-id="64979-273">Windows 10 (Redstone 1 更新或更新版本) </span><span class="sxs-lookup"><span data-stu-id="64979-273">Windows 10 (Redstone 1 update or later)</span></span>  <br/> |<span data-ttu-id="64979-274">Windows 通用應用程式會在秋季2016接收更新新增 interop 支援</span><span class="sxs-lookup"><span data-stu-id="64979-274">Windows Universal App will receive update in Fall 2016 adding interop support</span></span>  <br/> |
   
<span data-ttu-id="64979-275">下表概述最新版商務用 Skype 與最新版 Skype 使用者之間的交互操作狀態。</span><span class="sxs-lookup"><span data-stu-id="64979-275">The following table outlines the status of interop between the latest version of Skype for Business and the latest version of Skype consumer.</span></span> 
  
|<span data-ttu-id="64979-276">**用戶端**</span><span class="sxs-lookup"><span data-stu-id="64979-276">**Client**</span></span>|<span data-ttu-id="64979-277">**Skype 目錄搜尋及新增連絡人**</span><span class="sxs-lookup"><span data-stu-id="64979-277">**Skype Directory Search and Add Contacts**</span></span>|<span data-ttu-id="64979-278">**Skype A/V，IM interop**</span><span class="sxs-lookup"><span data-stu-id="64979-278">**Skype A/V, IM interop**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="64979-279">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="64979-279">Skype for Business</span></span>  <br/> |<span data-ttu-id="64979-280">是</span><span class="sxs-lookup"><span data-stu-id="64979-280">Yes</span></span>  <br/> |<span data-ttu-id="64979-281">是</span><span class="sxs-lookup"><span data-stu-id="64979-281">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-282">Mac 版商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="64979-282">Skype for Business on Mac</span></span>  <br/> |<span data-ttu-id="64979-283">可以新增 (無搜尋) </span><span class="sxs-lookup"><span data-stu-id="64979-283">Can add (no search)</span></span>  <br/> |<span data-ttu-id="64979-284">是</span><span class="sxs-lookup"><span data-stu-id="64979-284">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-285">Lync 桌面2013</span><span class="sxs-lookup"><span data-stu-id="64979-285">Lync Desktop 2013</span></span>  <br/> |<span data-ttu-id="64979-286">可以新增 (無搜尋) </span><span class="sxs-lookup"><span data-stu-id="64979-286">Can add (no search)</span></span>  <br/> |<span data-ttu-id="64979-287">是</span><span class="sxs-lookup"><span data-stu-id="64979-287">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-288">Lync Web App-線上和內部部署</span><span class="sxs-lookup"><span data-stu-id="64979-288">Lync Web App - online and on-premises</span></span>  <br/> |<span data-ttu-id="64979-289">不適用</span><span class="sxs-lookup"><span data-stu-id="64979-289">N/A</span></span>  <br/> |<span data-ttu-id="64979-290">不適用</span><span class="sxs-lookup"><span data-stu-id="64979-290">N/A</span></span>  <br/> |
|<span data-ttu-id="64979-291">Lync Mobile-Windows Phone</span><span class="sxs-lookup"><span data-stu-id="64979-291">Lync Mobile - Windows Phone</span></span>  <br/> |<span data-ttu-id="64979-292">即將推出</span><span class="sxs-lookup"><span data-stu-id="64979-292">Coming Soon</span></span>  <br/> |<span data-ttu-id="64979-293">是</span><span class="sxs-lookup"><span data-stu-id="64979-293">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-294">Lync Mobile-Android</span><span class="sxs-lookup"><span data-stu-id="64979-294">Lync Mobile - Android</span></span>  <br/> |<span data-ttu-id="64979-295">即將推出</span><span class="sxs-lookup"><span data-stu-id="64979-295">Coming Soon</span></span>  <br/> |<span data-ttu-id="64979-296">是</span><span class="sxs-lookup"><span data-stu-id="64979-296">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-297">Lync Mobile-iOS</span><span class="sxs-lookup"><span data-stu-id="64979-297">Lync Mobile - iOS</span></span>  <br/> |<span data-ttu-id="64979-298">即將推出</span><span class="sxs-lookup"><span data-stu-id="64979-298">Coming Soon</span></span>  <br/> |<span data-ttu-id="64979-299">是</span><span class="sxs-lookup"><span data-stu-id="64979-299">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-300">Lync Room System</span><span class="sxs-lookup"><span data-stu-id="64979-300">Lync Room System</span></span>  <br/> |<span data-ttu-id="64979-301">即將推出</span><span class="sxs-lookup"><span data-stu-id="64979-301">Coming Soon</span></span>  <br/> |<span data-ttu-id="64979-302">是</span><span class="sxs-lookup"><span data-stu-id="64979-302">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-303">Lync 新式應用程式 (Win 8.1) </span><span class="sxs-lookup"><span data-stu-id="64979-303">Lync Modern App (Win 8.1)</span></span>  <br/> |<span data-ttu-id="64979-304">是</span><span class="sxs-lookup"><span data-stu-id="64979-304">Yes</span></span>  <br/> |<span data-ttu-id="64979-305">是</span><span class="sxs-lookup"><span data-stu-id="64979-305">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-306">Lync Mac 2011</span><span class="sxs-lookup"><span data-stu-id="64979-306">Lync Mac 2011</span></span>  <br/> |<span data-ttu-id="64979-307">可以新增 (無搜尋) </span><span class="sxs-lookup"><span data-stu-id="64979-307">Can add (no search)</span></span>  <br/> |<span data-ttu-id="64979-308">是</span><span class="sxs-lookup"><span data-stu-id="64979-308">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-309">Lync 桌面2010</span><span class="sxs-lookup"><span data-stu-id="64979-309">Lync Desktop 2010</span></span>  <br/> |<span data-ttu-id="64979-310">可以新增 (無搜尋) </span><span class="sxs-lookup"><span data-stu-id="64979-310">Can add (no search)</span></span>  <br/> |<span data-ttu-id="64979-311">是</span><span class="sxs-lookup"><span data-stu-id="64979-311">Yes</span></span>  <br/> |
|<span data-ttu-id="64979-312">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="64979-312">Lync Phone Edition</span></span>  <br/> |<span data-ttu-id="64979-313">不適用</span><span class="sxs-lookup"><span data-stu-id="64979-313">N/A</span></span>  <br/> |<span data-ttu-id="64979-314">不適用</span><span class="sxs-lookup"><span data-stu-id="64979-314">N/A</span></span>  <br/> |
|<span data-ttu-id="64979-315">Lync 語音應答</span><span class="sxs-lookup"><span data-stu-id="64979-315">Lync Attendant</span></span>  <br/> |<span data-ttu-id="64979-316">不適用</span><span class="sxs-lookup"><span data-stu-id="64979-316">N/A</span></span>  <br/> |<span data-ttu-id="64979-317">不適用</span><span class="sxs-lookup"><span data-stu-id="64979-317">N/A</span></span>  <br/> |
   
