---
title: Microsoft Teams 中的資料位置
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 在本文中，你將瞭解這些資料在 Microsoft Teams 中的地理位置。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c16065a864ac82cdf5f11c0d2c8254b648731cac
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121683"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="0d5f0-103">Microsoft Teams 中的資料位置</span><span class="sxs-lookup"><span data-stu-id="0d5f0-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="0d5f0-104">Teams 中的資料位於與 Microsoft 365 或 Office 365 組織關聯的地理區域中。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-104">Data in Teams resides in the geographic region associated with your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="0d5f0-105">目前，Teams 支持澳大利亞、加拿大、法國、德國、印度、日本、南非、韓國、瑞士（包括列支敦斯登）、阿拉伯聯合大公國、英國、美洲、亞太地區和歐洲、中東和非洲地區。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-105">Currently, Teams supports the Australia, Canada, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0d5f0-106">Teams 目前只為新租用戶提供澳大利亞、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、韓國、南非和瑞士（包括列支敦斯登）的資料落地。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-106">Teams currently offers data residency in Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, United Kingdom, South Korea, South Africa, and Switzerland (which includes Liechtenstein) for new tenants only.</span></span>
> <span data-ttu-id="0d5f0-107">新的租用戶被定義為任何未從租用戶中的單個使用者登入 Teams 的租用戶。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="0d5f0-108">來自澳大利亞、印度、日本和韓國的現有租戶將繼續將其 Teams 資料儲存在亞太地區。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-108">Existing tenants from Australia, India, Japan, and South Korea will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="0d5f0-109">加拿大的現有租用戶將繼續將其資料儲存在美國。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="0d5f0-110">法國、德國、列支敦斯登、阿拉伯聯合大公國、英國、南非和瑞士的現有租戶的資料將儲存在歐洲、中東和非洲 (EMEA) 地區。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-110">Existing tenants in France, Germany, Liechtenstein, the United Arab Emirates, the United Kingdom, South Africa, and Switzerland will have their data stored in the EMEA region.</span></span>

## <a name="where-your-teams-data-is-stored"></a><span data-ttu-id="0d5f0-111">你的 Teams 資料的儲存位置</span><span class="sxs-lookup"><span data-stu-id="0d5f0-111">Where your Teams data is stored</span></span>

<span data-ttu-id="0d5f0-112">要查看哪些區域託管你的租用戶資料，請轉到 [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home) >  **[設置]** >  **[組織設定檔]**。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-112">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="0d5f0-113">向下捲動到**資料位置**。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-113">Scroll down to **Data location**.</span></span>

![包含系統管理中心中的 Teams 的資料位置表的螢幕截圖](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a><span data-ttu-id="0d5f0-115">Teams 待用資料的位置</span><span class="sxs-lookup"><span data-stu-id="0d5f0-115">Location of Teams data at rest</span></span>

<span data-ttu-id="0d5f0-116">Teams 資料的儲存方式將有所不同，具體取決於內容類別型。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-116">Your Teams data is stored differently depending on the content type.</span></span> 

![顯示 Teams 內容類別型及其待用儲存位置的圖表](media/location-of-data-storage-at-rest.png)

<span data-ttu-id="0d5f0-118">查看有關 [Microsoft Teams 結構的 Ignite 分組討論](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)，以進行深入討論。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-118">Check out the [Ignite breakout session on Microsoft Teams architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) for an in-depth discussion.</span></span>

### <a name="core-teams-customer-data"></a><span data-ttu-id="0d5f0-119">核心 Teams 客戶資料</span><span class="sxs-lookup"><span data-stu-id="0d5f0-119">Core Teams customer data</span></span>

<span data-ttu-id="0d5f0-120">如果您的租用戶位於澳大利亞、加拿大、歐盟、法國、德國、印度、日本、南非、韓國、瑞士（包括列支敦斯登）、阿拉伯聯合大公國、英國或美國，則 Microsoft 僅在該位置儲存以下客戶資料：</span><span class="sxs-lookup"><span data-stu-id="0d5f0-120">If your tenant is provisioned in Australia, Canada, the European Union, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, the United Kingdom, or the United States, Microsoft stores the following customer data at rest only within that location:</span></span>

- <span data-ttu-id="0d5f0-121">Teams 聊天、小組和頻道交談、圖像、語音郵件和連絡人</span><span class="sxs-lookup"><span data-stu-id="0d5f0-121">Teams chats, team and channel conversations, images, voicemail messages, and contacts</span></span>
- <span data-ttu-id="0d5f0-122">SharePoint Online 網站內容和儲存在該網站中的檔</span><span class="sxs-lookup"><span data-stu-id="0d5f0-122">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="0d5f0-123">上傳到商務用 OneDrive 的檔案</span><span class="sxs-lookup"><span data-stu-id="0d5f0-123">Files uploaded to OneDrive for Business</span></span>

#### <a name="chat-channel-messages-team-structure"></a><span data-ttu-id="0d5f0-124">聊天，頻道訊息，小組結構</span><span class="sxs-lookup"><span data-stu-id="0d5f0-124">Chat, channel messages, team structure</span></span>

<span data-ttu-id="0d5f0-125">Teams 中的每個小組都由 Microsoft 365 群組及其 SharePoint 網站和 Exchange 信箱支援。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-125">Every team in Teams is backed by a Microsoft 365 Group and its SharePoint site and Exchange mailbox.</span></span> <span data-ttu-id="0d5f0-126">私人聊天（包括群組聊天）、在頻道中作為交談一部分發送的訊息以及小組和頻道的結構都儲存在運行於 Azure 的聊天服務中。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-126">Private chats (including group chats), messages sent as part of a conversation in a channel, and the structure of teams and channels are stored in a chat service running in Azure.</span></span> <span data-ttu-id="0d5f0-127">資料還儲存在使用者和組信箱中的隱藏資料夾中，以啟用資訊保護功能。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-127">The data is also stored in a hidden folder in the user and group mailboxes to enable Information Protection features.</span></span>

#### <a name="voicemail-and-contacts"></a><span data-ttu-id="0d5f0-128">語音郵件和連絡人</span><span class="sxs-lookup"><span data-stu-id="0d5f0-128">Voicemail and contacts</span></span>

<span data-ttu-id="0d5f0-129">語音郵件儲存在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-129">Voicemails are stored in Exchange.</span></span> <span data-ttu-id="0d5f0-130">連絡人存儲在基於 Exchange 的雲端資料儲存區中。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-130">Contacts are stored in Exchange-based cloud data store.</span></span> <span data-ttu-id="0d5f0-131">Exchange 和基於 Exchange 的雲端儲存區已在全球每個資料中心地理位置提供資料落地。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-131">Exchange and the Exchange-based cloud store already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="0d5f0-132">對於所有小組，語音郵件和連絡人儲存在澳大利亞、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、南非、韓國、瑞士（包括列支敦斯登）和美國的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-132">For all teams, voicemail and contacts are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, Switzerland (includes Liechtenstein), and the United States.</span></span> <span data-ttu-id="0d5f0-133">對於所有其他國家/地區，基於租用戶相關性，檔案儲存在美國、歐洲或亞太地區。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-133">For all other countries, files are stored in the US, Europe, or Asia-Pacific location based on tenant affinity.</span></span>

#### <a name="images-and-media"></a><span data-ttu-id="0d5f0-134">影像和媒體</span><span class="sxs-lookup"><span data-stu-id="0d5f0-134">Images and media</span></span>

<span data-ttu-id="0d5f0-135">聊天中使用的媒體 (Giphy GIF 除外，它沒有被儲存，但是指向原始 Giphy 服務 URL 的參考連結，Giphy 是非 Microsoft 服務) 儲存在基於 Azure 的媒體服務中，該服務部署到與聊天服務相同的位置。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-135">Media used in chats (except for Giphy GIFs which aren't stored but are a reference link to the original Giphy service URL, Giphy is a non-Microsoft service) is stored in an Azure-based media service that is deployed to the same locations as the chat service.</span></span>

#### <a name="files"></a><span data-ttu-id="0d5f0-136">檔案</span><span class="sxs-lookup"><span data-stu-id="0d5f0-136">Files</span></span>

<span data-ttu-id="0d5f0-137">頻道中共用的檔案 (包括 OneNote 和 Wiki) 儲存在小組的 SharePoint 網站中。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-137">Files (including OneNote and Wiki) that somebody shares in a channel are stored in the team’s SharePoint site.</span></span> <span data-ttu-id="0d5f0-138">在私人聊天、會議或通話期間的聊天中共用的檔將上載並儲存在 OneDrive 中，供共用該檔的使用者的商務帳戶使用。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-138">Files shared in a private chat or a chat during a meeting or call are uploaded and stored in the OneDrive for the Business account of the user who shares the file.</span></span> <span data-ttu-id="0d5f0-139">Exchange、SharePoint 和 OneDrive 已經在全球每個資料中心地理位置提供資料落地。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-139">Exchange, SharePoint and OneDrive already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="0d5f0-140">因此，對於現有客戶，作為 Teams 體驗一部分的所有檔、OneNote 筆記本、Team wiki 內容和郵箱都已根據您的租用戶相關性儲存在該位置。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-140">So, for existing customers, all files, OneNote notebooks, Teams wiki content, and mailboxes that are part of the Teams experience are already stored in the location based on your tenant affinity.</span></span> <span data-ttu-id="0d5f0-141">檔案存儲在澳大利亞、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、南非、韓國和瑞士 (包括列支敦斯登) 的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-141">Files are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, and Switzerland (which includes Liechtenstein).</span></span> <span data-ttu-id="0d5f0-142">對於所有其他國家/地區，基於租用戶相關性，檔案儲存在美國、歐洲或亞太地區。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-142">For all other countries, files are stored in the US, Europe, or Asia Pacific location based on tenant affinity.</span></span>

### <a name="datacenter-locations"></a><span data-ttu-id="0d5f0-143">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="0d5f0-143">Datacenter locations</span></span>

<span data-ttu-id="0d5f0-144">本節中描述的 Teams 服務將待用資料儲存在以下位置：</span><span class="sxs-lookup"><span data-stu-id="0d5f0-144">The Teams services described in this section store data at rest in the following locations:</span></span>

|<span data-ttu-id="0d5f0-145">國家或地區</span><span class="sxs-lookup"><span data-stu-id="0d5f0-145">Country or region</span></span>  |<span data-ttu-id="0d5f0-146">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="0d5f0-146">Datacenter location</span></span> |
|---------|---------|
|<span data-ttu-id="0d5f0-147">澳大利亞</span><span class="sxs-lookup"><span data-stu-id="0d5f0-147">Australia</span></span>   |<span data-ttu-id="0d5f0-148">新南威爾士州和維多利亞</span><span class="sxs-lookup"><span data-stu-id="0d5f0-148">New South Wales and Victoria</span></span>         |
|<span data-ttu-id="0d5f0-149">加拿大</span><span class="sxs-lookup"><span data-stu-id="0d5f0-149">Canada</span></span>    |<span data-ttu-id="0d5f0-150">魁北克市和多倫多</span><span class="sxs-lookup"><span data-stu-id="0d5f0-150">Quebec City and Toronto</span></span>         |
|<span data-ttu-id="0d5f0-151">法國</span><span class="sxs-lookup"><span data-stu-id="0d5f0-151">France</span></span>    |<span data-ttu-id="0d5f0-152">馬賽和巴黎</span><span class="sxs-lookup"><span data-stu-id="0d5f0-152">Marseille and Paris</span></span>         |
|<span data-ttu-id="0d5f0-153">德國</span><span class="sxs-lookup"><span data-stu-id="0d5f0-153">Germany</span></span>    |<span data-ttu-id="0d5f0-154">柏林和法蘭克福</span><span class="sxs-lookup"><span data-stu-id="0d5f0-154">Berlin and Frankfurt</span></span>      |
|<span data-ttu-id="0d5f0-155">印度</span><span class="sxs-lookup"><span data-stu-id="0d5f0-155">India</span></span>   |<span data-ttu-id="0d5f0-156">欽奈和浦那</span><span class="sxs-lookup"><span data-stu-id="0d5f0-156">Chennai and Pune</span></span>        |
|<span data-ttu-id="0d5f0-157">日本</span><span class="sxs-lookup"><span data-stu-id="0d5f0-157">Japan</span></span>    |<span data-ttu-id="0d5f0-158">東京 (埼玉) 和大阪</span><span class="sxs-lookup"><span data-stu-id="0d5f0-158">Tokyo (Saitama) and Osaka</span></span>         |
|<span data-ttu-id="0d5f0-159">列支敦斯登</span><span class="sxs-lookup"><span data-stu-id="0d5f0-159">Liechtenstein</span></span>   |<span data-ttu-id="0d5f0-160">日內瓦和蘇黎世</span><span class="sxs-lookup"><span data-stu-id="0d5f0-160">Geneva and Zurich</span></span>       |
|<span data-ttu-id="0d5f0-161">南非</span><span class="sxs-lookup"><span data-stu-id="0d5f0-161">South Africa</span></span>     |<span data-ttu-id="0d5f0-162">約翰尼斯堡和開普敦</span><span class="sxs-lookup"><span data-stu-id="0d5f0-162">Johannesburg and Cape Town</span></span>         |
|<span data-ttu-id="0d5f0-163">韓國</span><span class="sxs-lookup"><span data-stu-id="0d5f0-163">South Korea</span></span>     |<span data-ttu-id="0d5f0-164">首爾和釜山</span><span class="sxs-lookup"><span data-stu-id="0d5f0-164">Seoul and Busan</span></span>         |
|<span data-ttu-id="0d5f0-165">瑞士</span><span class="sxs-lookup"><span data-stu-id="0d5f0-165">Switzerland</span></span>    |<span data-ttu-id="0d5f0-166">日內瓦和蘇黎世</span><span class="sxs-lookup"><span data-stu-id="0d5f0-166">Geneva and Zurich</span></span>       |
|<span data-ttu-id="0d5f0-167">阿拉伯聯合大公國</span><span class="sxs-lookup"><span data-stu-id="0d5f0-167">United Arab Emirates</span></span>     |<span data-ttu-id="0d5f0-168">阿布達比和杜拜</span><span class="sxs-lookup"><span data-stu-id="0d5f0-168">Abu Dhabi and Dubai</span></span>         |
|<span data-ttu-id="0d5f0-169">英國</span><span class="sxs-lookup"><span data-stu-id="0d5f0-169">United Kingdom</span></span>     | <span data-ttu-id="0d5f0-170">加的夫和倫敦</span><span class="sxs-lookup"><span data-stu-id="0d5f0-170">Cardiff and London</span></span>        |
|<span data-ttu-id="0d5f0-171">美洲 - 北美洲和南美洲 (AMER)</span><span class="sxs-lookup"><span data-stu-id="0d5f0-171">Americas – North, and South (AMER)</span></span> |<span data-ttu-id="0d5f0-172">加州灣和維珍尼亞州博伊頓</span><span class="sxs-lookup"><span data-stu-id="0d5f0-172">Bay, CA and Boydton, VA</span></span>       |
|<span data-ttu-id="0d5f0-173">亞太地區 (APAC)</span><span class="sxs-lookup"><span data-stu-id="0d5f0-173">Asia Pacific (APAC)</span></span>  |<span data-ttu-id="0d5f0-174">新加坡和香港特別行政區</span><span class="sxs-lookup"><span data-stu-id="0d5f0-174">Singapore and Hong Kong</span></span>        |
|<span data-ttu-id="0d5f0-175">歐洲、中東和亞洲 (EMEA)</span><span class="sxs-lookup"><span data-stu-id="0d5f0-175">Europe, Middle East, and Asia (EMEA)</span></span>   |<span data-ttu-id="0d5f0-176">都柏林和阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="0d5f0-176">Dublin and Amsterdam</span></span>        |

> [!NOTE]
> <span data-ttu-id="0d5f0-177">對列支敦斯登來說，資料存儲在日內瓦和蘇黎世的瑞士資料中心。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-177">For Liechtenstein, data is stored at rest in the Switzerland data centers in Geneva and Zurich.</span></span>

### <a name="data-stored-with-a-third-party-storage-provider"></a><span data-ttu-id="0d5f0-178">使用協力廠商儲存提供者儲存的資料</span><span class="sxs-lookup"><span data-stu-id="0d5f0-178">Data stored with a third-party storage provider</span></span>

<span data-ttu-id="0d5f0-179">因此，對於那些依賴於協力廠商儲存位置的服務的使用者來說，應該允許他們將這些資料儲存在協力廠商的位置上。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-179">Organizations who allow users to store files with a third-party storage provider are dependent on the storage location of those services and should, therefore, review the location of data at rest for those services separately.</span></span>

- <span data-ttu-id="0d5f0-180">**索引標籤**：索引標籤可讓使用者將應用程式和服務中的資訊釘選到頻道。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-180">**Tabs**: Tabs allow users to pin information from apps and services to a channel.</span></span> <span data-ttu-id="0d5f0-181">因此，它因儲存資料的索引標籤類型而異。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-181">Thus, it varies by type of the tab where the data is stored.</span></span> <span data-ttu-id="0d5f0-182">該索引標籤本身不儲存任何資料。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-182">The tab itself doesn't store any data.</span></span> <span data-ttu-id="0d5f0-183">例如，SharePoint 索引標籤將根據 SharePoint 網站集合的佈建位置儲存資料。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-183">For example, a SharePoint tab will store data based on where the SharePoint site collection was provisioned.</span></span> <span data-ttu-id="0d5f0-184">包含合作夥伴資訊的索引標籤將直接將資料儲存在合作夥伴使用的系統中，並且只顯示其檢視。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-184">A tab that includes information from a partner will store the data directly in the system used by the partner and only present a view of it.</span></span>
- <span data-ttu-id="0d5f0-185">**其他合作夥伴應用程式**：對於您可能在 Teams 體驗中使用的合作夥伴的應用程式和服務，Microsoft 不提供任何資料落地支援。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-185">**Other partner apps**: Microsoft doesn't provide any data residency support for apps and services from partners that you might be using within the Teams experience.</span></span> <span data-ttu-id="0d5f0-186">直接查看這些解決方案中的資訊，以瞭解其資料的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="0d5f0-186">Review information from those solutions directly to learn about where their data is being stored.</span></span>

## <a name="see-also"></a><span data-ttu-id="0d5f0-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0d5f0-187">See also</span></span>

- [<span data-ttu-id="0d5f0-188">Microsoft Teams 推出阿拉伯聯合大公國資料落地</span><span class="sxs-lookup"><span data-stu-id="0d5f0-188">Microsoft Teams launches United Arab Emirates Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [<span data-ttu-id="0d5f0-189">Microsoft Teams 推出韓國資料落地</span><span class="sxs-lookup"><span data-stu-id="0d5f0-189">Microsoft Teams launches South Korean Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [<span data-ttu-id="0d5f0-190">Microsoft Teams 推出南非資料落地</span><span class="sxs-lookup"><span data-stu-id="0d5f0-190">Microsoft Teams launches South African Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [<span data-ttu-id="0d5f0-191">Microsoft Teams 推出法國資料落地</span><span class="sxs-lookup"><span data-stu-id="0d5f0-191">Microsoft Teams Launches France Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [<span data-ttu-id="0d5f0-192">Microsoft Teams 推出印度資料落地，即將推出其他地點</span><span class="sxs-lookup"><span data-stu-id="0d5f0-192">Microsoft Teams launches India Data Residency, other geos coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [<span data-ttu-id="0d5f0-193">Microsoft Teams 推出澳大利亞和日本資料落地</span><span class="sxs-lookup"><span data-stu-id="0d5f0-193">Microsoft Teams Launches Australia and Japan Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [<span data-ttu-id="0d5f0-194">Microsoft Teams 推出加拿大的資料落地、澳大利亞和日本即將推出</span><span class="sxs-lookup"><span data-stu-id="0d5f0-194">Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
