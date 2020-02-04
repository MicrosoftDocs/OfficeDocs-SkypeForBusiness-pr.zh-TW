---
title: Microsoft 團隊中的資料位置
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: admin
ms.service: msteams
ms.reviewer: anach, kehardy
description: 瞭解資料在 Microsoft 團隊中的儲存位置。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24432b0854ac0c4256f5d097bacfca5f1a392d72
ms.sourcegitcommit: 2cb46af39a0d116e8fd020aa04bd2ecbd6998a5f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41679040"
---
# <a name="location-of-data-in-microsoft-teams"></a><span data-ttu-id="6daaa-103">Microsoft 團隊中的資料位置</span><span class="sxs-lookup"><span data-stu-id="6daaa-103">Location of data in Microsoft Teams</span></span>

<span data-ttu-id="6daaa-104">團隊中的資料位於與您的 Office 365 租使用者相關聯的地理區域中。</span><span class="sxs-lookup"><span data-stu-id="6daaa-104">Data in Teams resides in the geographic region associated with your Office 365 tenant.</span></span> <span data-ttu-id="6daaa-105">目前，團隊支援澳大利亞、加拿大、法國、德國、印度、日本、南非、韓國、瑞士（包括列支敦斯登）、阿拉伯聯合大公國、英國、美洲、APAC 及 EMEA 地區。</span><span class="sxs-lookup"><span data-stu-id="6daaa-105">Currently, Teams supports the Australia, Canada, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, United Kingdom, Americas, APAC, and EMEA regions.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6daaa-106">團隊目前在澳大利亞、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、韓國、非洲和瑞士（包括列支敦斯登）等新的租使用者中提供資料。</span><span class="sxs-lookup"><span data-stu-id="6daaa-106">Teams currently offers data residency in Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, United Kingdom, South Korea, South Africa, and Switzerland (which includes Liechtenstein) for new tenants only.</span></span>
> <span data-ttu-id="6daaa-107">新的租使用者定義為任何沒有租使用者登入團隊中的使用者的租使用者。</span><span class="sxs-lookup"><span data-stu-id="6daaa-107">A new tenant is defined as any tenant that hasn’t had a single user from the tenant sign in to Teams.</span></span> <span data-ttu-id="6daaa-108">澳大利亞、印度、日本和韓國的現有租使用者將繼續將其小組資料儲存在 APAC 區域中。</span><span class="sxs-lookup"><span data-stu-id="6daaa-108">Existing tenants from Australia, India, Japan, and South Korea will continue to have their Teams data stored in the APAC region.</span></span> <span data-ttu-id="6daaa-109">加拿大中的現有租使用者將繼續將其資料儲存在美洲。</span><span class="sxs-lookup"><span data-stu-id="6daaa-109">Existing tenants in Canada will continue to have their data stored in the Americas.</span></span> <span data-ttu-id="6daaa-110">在華北、德國、列支敦斯登、阿拉伯聯合大公國、英國、南非和瑞士的現有租使用者，其資料會儲存在 EMEA 地區。</span><span class="sxs-lookup"><span data-stu-id="6daaa-110">Existing tenants in France, Germany, Liechtenstein, the United Arab Emirates, the United Kingdom, South Africa, and Switzerland will have their data stored in the EMEA region.</span></span>

## <a name="where-your-teams-data-is-stored"></a><span data-ttu-id="6daaa-111">您的團隊資料的儲存位置</span><span class="sxs-lookup"><span data-stu-id="6daaa-111">Where your Teams data is stored</span></span>

<span data-ttu-id="6daaa-112">若要查看哪個地區駐留您租使用者的資料，請移至[Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home) > **設定** > **組織設定檔**。</span><span class="sxs-lookup"><span data-stu-id="6daaa-112">To see which region houses data for your tenant, go to the [Microsoft 365 admin center](https://portal.office.com/adminportal/home) > **Settings** > **Organization profile**.</span></span> <span data-ttu-id="6daaa-113">向下滾動至 [**資料位置**]。</span><span class="sxs-lookup"><span data-stu-id="6daaa-113">Scroll down to **Data location**.</span></span>

![資料位置資料表的螢幕擷取畫面，其中包含系統管理中心的團隊](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="location-of-teams-data-at-rest"></a><span data-ttu-id="6daaa-115">[Rest] 上的小組資料位置</span><span class="sxs-lookup"><span data-stu-id="6daaa-115">Location of Teams data at rest</span></span>

<span data-ttu-id="6daaa-116">依內容類型而定，您的小組資料會以不同的方式儲存。</span><span class="sxs-lookup"><span data-stu-id="6daaa-116">Your Teams data is stored differently depending on the content type.</span></span> 

![圖表顯示小組內容類型，以及將其儲存在其他位置](media/location-of-data-storage-at-rest.png)

<span data-ttu-id="6daaa-118">請參閱[Microsoft 團隊結構上的 Ignite 專題討論會話](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071)，取得深入討論。</span><span class="sxs-lookup"><span data-stu-id="6daaa-118">Check out the [Ignite breakout session on Microsoft Teams architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) for an in-depth discussion.</span></span>

### <a name="core-teams-customer-data"></a><span data-ttu-id="6daaa-119">核心團隊客戶資料</span><span class="sxs-lookup"><span data-stu-id="6daaa-119">Core Teams customer data</span></span>

<span data-ttu-id="6daaa-120">如果您的租使用者是在澳大利亞、加拿大、歐洲同盟、法國、德國、印度、日本、南非、韓國、瑞士（包括列支敦斯登）、阿拉伯聯合大公國、英國或美國，Microsoft 書店下列客戶資料只存放在該位置中：</span><span class="sxs-lookup"><span data-stu-id="6daaa-120">If your tenant is provisioned in Australia, Canada, the European Union, France, Germany, India, Japan, South Africa, South Korea, Switzerland (which includes Liechtenstein), the United Arab Emirates, the United Kingdom, or the United States, Microsoft stores the following customer data at rest only within that location:</span></span>

- <span data-ttu-id="6daaa-121">團隊聊天、團隊和頻道交談、影像、語音信箱訊息及連絡人</span><span class="sxs-lookup"><span data-stu-id="6daaa-121">Teams chats, team and channel conversations, images, voicemail messages, and contacts</span></span>
- <span data-ttu-id="6daaa-122">SharePoint Online 網站內容和儲存在該網站中的檔案</span><span class="sxs-lookup"><span data-stu-id="6daaa-122">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="6daaa-123">上傳到商務用 OneDrive 的檔案</span><span class="sxs-lookup"><span data-stu-id="6daaa-123">Files uploaded to OneDrive for Business</span></span>

#### <a name="chat-channel-messages-team-structure"></a><span data-ttu-id="6daaa-124">聊天、頻道訊息、團隊結構</span><span class="sxs-lookup"><span data-stu-id="6daaa-124">Chat, channel messages, team structure</span></span>

<span data-ttu-id="6daaa-125">團隊中的每個團隊都是由 Office 365 群組及其 SharePoint 網站和 Exchange 信箱來支援。</span><span class="sxs-lookup"><span data-stu-id="6daaa-125">Every team in Teams is backed by an Office 365 Group and its SharePoint site and Exchange mailbox.</span></span> <span data-ttu-id="6daaa-126">私人聊天（包括群組聊天）、在頻道中作為交談的一部分傳送的郵件，以及團隊和頻道的結構，都儲存在在 Azure 中執行的聊天服務中。</span><span class="sxs-lookup"><span data-stu-id="6daaa-126">Private chats (including group chats), messages sent as part of a conversation in a channel, and the structure of teams and channels are stored in a chat service running in Azure.</span></span> <span data-ttu-id="6daaa-127">資料也會儲存在使用者和群組信箱的隱藏資料夾中，以啟用資訊保護功能。</span><span class="sxs-lookup"><span data-stu-id="6daaa-127">The data is also stored in a hidden folder in the user and group mailboxes to enable Information Protection features.</span></span>

#### <a name="voicemail-and-contacts"></a><span data-ttu-id="6daaa-128">語音信箱和連絡人</span><span class="sxs-lookup"><span data-stu-id="6daaa-128">Voicemail and contacts</span></span>

<span data-ttu-id="6daaa-129">語音訊息儲存在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="6daaa-129">Voicemails are stored in Exchange.</span></span> <span data-ttu-id="6daaa-130">連絡人儲存在 Exchange 雲端資料儲存區中。</span><span class="sxs-lookup"><span data-stu-id="6daaa-130">Contacts are stored in Exchange-based cloud data store.</span></span> <span data-ttu-id="6daaa-131">Exchange 與 Exchange 雲端儲存區已在每個全球資料中心 geos 中提供資料常駐功能。</span><span class="sxs-lookup"><span data-stu-id="6daaa-131">Exchange and the Exchange-based cloud store already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="6daaa-132">針對所有團隊，語音信箱和連絡人都是儲存在美國國內、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、南非、韓國、瑞士（包括列支敦斯登）及美國等。</span><span class="sxs-lookup"><span data-stu-id="6daaa-132">For all teams, voicemail and contacts are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, Switzerland (includes Liechtenstein), and the United States.</span></span> <span data-ttu-id="6daaa-133">針對所有其他國家/地區，檔案會根據租使用者關聯性儲存在美國、歐洲或亞太地區位置。</span><span class="sxs-lookup"><span data-stu-id="6daaa-133">For all other countries, files are stored in the US, Europe, or Asia-Pacific location based on tenant affinity.</span></span>

#### <a name="images-and-media"></a><span data-ttu-id="6daaa-134">影像和媒體</span><span class="sxs-lookup"><span data-stu-id="6daaa-134">Images and media</span></span>

<span data-ttu-id="6daaa-135">在聊天中使用的媒體（除了不會儲存的 Giphy Gif，但是原始 Giphy 服務 URL 的參照連結，Giphy 是非 Microsoft 服務）儲存在與聊天服務相同位置的 Azure 媒體服務中。</span><span class="sxs-lookup"><span data-stu-id="6daaa-135">Media used in chats (except for Giphy GIFs which aren't stored but are a reference link to the original Giphy service URL, Giphy is a non-Microsoft service) is stored in an Azure-based media service that is deployed to the same locations as the chat service.</span></span>

#### <a name="files"></a><span data-ttu-id="6daaa-136">檔案</span><span class="sxs-lookup"><span data-stu-id="6daaa-136">Files</span></span>

<span data-ttu-id="6daaa-137">在頻道中共用的檔案（包括 OneNote 和 Wiki）會儲存在小組的 SharePoint 網站上。</span><span class="sxs-lookup"><span data-stu-id="6daaa-137">Files (including OneNote and Wiki) that somebody shares in a channel are stored in the team’s SharePoint site.</span></span> <span data-ttu-id="6daaa-138">在會議或通話期間，在私人聊天或聊天中共用的檔案，會上傳並儲存在共用該檔案之使用者的商務用 OneDrive 帳戶中。</span><span class="sxs-lookup"><span data-stu-id="6daaa-138">Files shared in a private chat or a chat during a meeting or call are uploaded and stored in the OneDrive for the Business account of the user who shares the file.</span></span> <span data-ttu-id="6daaa-139">Exchange、SharePoint 和 OneDrive 已在每個全球資料中心 geos 提供資料常駐功能。</span><span class="sxs-lookup"><span data-stu-id="6daaa-139">Exchange, SharePoint and OneDrive already provide data residency in each of the worldwide datacenter geos.</span></span> <span data-ttu-id="6daaa-140">所以針對現有客戶，所有檔案、OneNote 筆記本、團隊 wiki 內容，以及屬於團隊經驗的信箱，都已儲存在根據您的租使用者關聯性的位置。</span><span class="sxs-lookup"><span data-stu-id="6daaa-140">So, for existing customers, all files, OneNote notebooks, Teams wiki content, and mailboxes that are part of the Teams experience are already stored in the location based on your tenant affinity.</span></span> <span data-ttu-id="6daaa-141">檔案是儲存在國內、加拿大、法國、德國、印度、日本、阿拉伯聯合大公國、英國、南非、韓國和瑞士（包括列支敦斯登）的國家/地區。</span><span class="sxs-lookup"><span data-stu-id="6daaa-141">Files are stored in-country for Australia, Canada, France, Germany, India, Japan, the United Arab Emirates, the United Kingdom, South Africa, South Korea, and Switzerland (which includes Liechtenstein).</span></span> <span data-ttu-id="6daaa-142">針對所有其他國家/地區，檔案會根據租使用者關聯性儲存在美國、歐洲或亞太地區的位置。</span><span class="sxs-lookup"><span data-stu-id="6daaa-142">For all other countries, files are stored in the US, Europe, or Asia Pacific location based on tenant affinity.</span></span>

### <a name="datacenter-locations"></a><span data-ttu-id="6daaa-143">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="6daaa-143">Datacenter locations</span></span>

<span data-ttu-id="6daaa-144">本節所述的小組服務將資料儲存在下列位置：</span><span class="sxs-lookup"><span data-stu-id="6daaa-144">The Teams services described in this section store data at rest in the following locations:</span></span>

|<span data-ttu-id="6daaa-145">國家或地區</span><span class="sxs-lookup"><span data-stu-id="6daaa-145">Country or region</span></span>  |<span data-ttu-id="6daaa-146">資料中心位置</span><span class="sxs-lookup"><span data-stu-id="6daaa-146">Datacenter location</span></span> |
|---------|---------|
|<span data-ttu-id="6daaa-147">澳洲</span><span class="sxs-lookup"><span data-stu-id="6daaa-147">Australia</span></span>   |<span data-ttu-id="6daaa-148">新的南威爾士及維多利亞</span><span class="sxs-lookup"><span data-stu-id="6daaa-148">New South Wales and Victoria</span></span>         |
|<span data-ttu-id="6daaa-149">加拿大</span><span class="sxs-lookup"><span data-stu-id="6daaa-149">Canada</span></span>    |<span data-ttu-id="6daaa-150">魁北克城市和多倫多</span><span class="sxs-lookup"><span data-stu-id="6daaa-150">Quebec City and Toronto</span></span>         |
|<span data-ttu-id="6daaa-151">法國</span><span class="sxs-lookup"><span data-stu-id="6daaa-151">France</span></span>    |<span data-ttu-id="6daaa-152">Marseille 和巴黎</span><span class="sxs-lookup"><span data-stu-id="6daaa-152">Marseille and Paris</span></span>         |
|<span data-ttu-id="6daaa-153">德國</span><span class="sxs-lookup"><span data-stu-id="6daaa-153">Germany</span></span>    |<span data-ttu-id="6daaa-154">柏林與 Frankfurt</span><span class="sxs-lookup"><span data-stu-id="6daaa-154">Berlin and Frankfurt</span></span>      |
|<span data-ttu-id="6daaa-155">印度</span><span class="sxs-lookup"><span data-stu-id="6daaa-155">India</span></span>   |<span data-ttu-id="6daaa-156">Chennai 和 Pune</span><span class="sxs-lookup"><span data-stu-id="6daaa-156">Chennai and Pune</span></span>        |
|<span data-ttu-id="6daaa-157">日本</span><span class="sxs-lookup"><span data-stu-id="6daaa-157">Japan</span></span>    |<span data-ttu-id="6daaa-158">東京（Saitama）和 Osaka</span><span class="sxs-lookup"><span data-stu-id="6daaa-158">Tokyo (Saitama) and Osaka</span></span>         |
|<span data-ttu-id="6daaa-159">列支敦斯登</span><span class="sxs-lookup"><span data-stu-id="6daaa-159">Liechtenstein</span></span>   |<span data-ttu-id="6daaa-160">Geneva 和蘇黎世</span><span class="sxs-lookup"><span data-stu-id="6daaa-160">Geneva and Zurich</span></span>       |
|<span data-ttu-id="6daaa-161">南非</span><span class="sxs-lookup"><span data-stu-id="6daaa-161">South Africa</span></span>     |<span data-ttu-id="6daaa-162">Johannesburg 和維德角</span><span class="sxs-lookup"><span data-stu-id="6daaa-162">Johannesburg and Cape Town</span></span>         |
|<span data-ttu-id="6daaa-163">南韓</span><span class="sxs-lookup"><span data-stu-id="6daaa-163">South Korea</span></span>     |<span data-ttu-id="6daaa-164">首爾與 Busan</span><span class="sxs-lookup"><span data-stu-id="6daaa-164">Seoul and Busan</span></span>         |
|<span data-ttu-id="6daaa-165">瑞士</span><span class="sxs-lookup"><span data-stu-id="6daaa-165">Switzerland</span></span>    |<span data-ttu-id="6daaa-166">Geneva 和蘇黎世</span><span class="sxs-lookup"><span data-stu-id="6daaa-166">Geneva and Zurich</span></span>       |
|<span data-ttu-id="6daaa-167">阿拉伯聯合大公國</span><span class="sxs-lookup"><span data-stu-id="6daaa-167">United Arab Emirates</span></span>     |<span data-ttu-id="6daaa-168">阿布達比 Dhabi 和 Dubai</span><span class="sxs-lookup"><span data-stu-id="6daaa-168">Abu Dhabi and Dubai</span></span>         |
|<span data-ttu-id="6daaa-169">英國</span><span class="sxs-lookup"><span data-stu-id="6daaa-169">United Kingdom</span></span>     | <span data-ttu-id="6daaa-170">Cardiff 和倫敦</span><span class="sxs-lookup"><span data-stu-id="6daaa-170">Cardiff and London</span></span>        |
|<span data-ttu-id="6daaa-171">美洲–北和南部（AMER）</span><span class="sxs-lookup"><span data-stu-id="6daaa-171">Americas – North, and South (AMER)</span></span> |<span data-ttu-id="6daaa-172">Bay、CA 與 Boydton、佛吉尼亞</span><span class="sxs-lookup"><span data-stu-id="6daaa-172">Bay, CA and Boydton, VA</span></span>       |
|<span data-ttu-id="6daaa-173">亞太地區（APAC）</span><span class="sxs-lookup"><span data-stu-id="6daaa-173">Asia Pacific (APAC)</span></span>  |<span data-ttu-id="6daaa-174">新加坡與香港</span><span class="sxs-lookup"><span data-stu-id="6daaa-174">Singapore and Hong Kong</span></span>        |
|<span data-ttu-id="6daaa-175">歐洲、中東及亞洲（EMEA）</span><span class="sxs-lookup"><span data-stu-id="6daaa-175">Europe, Middle East, and Asia (EMEA)</span></span>   |<span data-ttu-id="6daaa-176">都柏林與阿姆斯特丹</span><span class="sxs-lookup"><span data-stu-id="6daaa-176">Dublin and Amsterdam</span></span>        |

> [!NOTE]
> <span data-ttu-id="6daaa-177">對於列支敦斯登，資料會儲存在 Geneva 和蘇黎世的瑞士資料中心中的 [其他]。</span><span class="sxs-lookup"><span data-stu-id="6daaa-177">For Liechtenstein, data is stored at rest in the Switzerland data centers in Geneva and Zurich.</span></span>

### <a name="data-stored-with-a-third-party-storage-provider"></a><span data-ttu-id="6daaa-178">與協力廠商存儲提供者一起儲存的資料</span><span class="sxs-lookup"><span data-stu-id="6daaa-178">Data stored with a third-party storage provider</span></span>

<span data-ttu-id="6daaa-179">允許使用者使用協力廠商儲存空間提供者儲存檔案的組織，會視這些服務的儲存位置而定，因此請分別檢查其餘服務的資料位置。</span><span class="sxs-lookup"><span data-stu-id="6daaa-179">Organizations who allow users to store files with a third-party storage provider are dependent on the storage location of those services and should, therefore, review the location of data at rest for those services separately.</span></span>

- <span data-ttu-id="6daaa-180">**[** 索引標籤]：索引標籤可讓使用者將應用程式和服務的資訊釘選到頻道。</span><span class="sxs-lookup"><span data-stu-id="6daaa-180">**Tabs**: Tabs allow users to pin information from apps and services to a channel.</span></span> <span data-ttu-id="6daaa-181">因此，它會依儲存資料的索引標籤類型而有所不同。</span><span class="sxs-lookup"><span data-stu-id="6daaa-181">Thus, it varies by type of the tab where the data is stored.</span></span> <span data-ttu-id="6daaa-182">索引標籤本身不會儲存任何資料。</span><span class="sxs-lookup"><span data-stu-id="6daaa-182">The tab itself doesn't store any data.</span></span> <span data-ttu-id="6daaa-183">例如，[SharePoint] 索引標籤會根據 SharePoint 網站集合的調配位置來儲存資料。</span><span class="sxs-lookup"><span data-stu-id="6daaa-183">For example, a SharePoint tab will store data based on where the SharePoint site collection was provisioned.</span></span> <span data-ttu-id="6daaa-184">包括來自合作夥伴之資訊的索引標籤會直接將資料儲存在合作夥伴所使用的系統中，而且只會呈現它的觀點。</span><span class="sxs-lookup"><span data-stu-id="6daaa-184">A tab that includes information from a partner will store the data directly in the system used by the partner and only present a view of it.</span></span>
- <span data-ttu-id="6daaa-185">**其他合作夥伴應用程式**： Microsoft 不會針對您在團隊體驗中所使用的合作夥伴提供 app 與服務的任何資料派駐支援。</span><span class="sxs-lookup"><span data-stu-id="6daaa-185">**Other partner apps**: Microsoft doesn't provide any data residency support for apps and services from partners that you might be using within the Teams experience.</span></span> <span data-ttu-id="6daaa-186">直接查看這些解決方案中的資訊，以瞭解其資料的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6daaa-186">Review information from those solutions directly to learn about where their data is being stored.</span></span>

## <a name="see-also"></a><span data-ttu-id="6daaa-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6daaa-187">See also</span></span>

- [<span data-ttu-id="6daaa-188">Microsoft 團隊會啟動阿拉伯聯合大公國資料派駐</span><span class="sxs-lookup"><span data-stu-id="6daaa-188">Microsoft Teams launches United Arab Emirates Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-United-Arab-Emirates-Data-Residency/ba-p/980330)

- [<span data-ttu-id="6daaa-189">Microsoft 團隊啟動南亞韓文資料派駐服務</span><span class="sxs-lookup"><span data-stu-id="6daaa-189">Microsoft Teams launches South Korean Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171)

- [<span data-ttu-id="6daaa-190">Microsoft 團隊啟動南亞非洲資料派駐服務</span><span class="sxs-lookup"><span data-stu-id="6daaa-190">Microsoft Teams launches South African Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611)

- [<span data-ttu-id="6daaa-191">Microsoft 團隊會啟動法國資料派駐服務</span><span class="sxs-lookup"><span data-stu-id="6daaa-191">Microsoft Teams Launches France Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466)

- [<span data-ttu-id="6daaa-192">Microsoft 團隊會啟動印度資料派駐服務，即將推出其他 geos</span><span class="sxs-lookup"><span data-stu-id="6daaa-192">Microsoft Teams launches India Data Residency, other geos coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-India-Data-Residency-other-geos-coming/ba-p/154083)

- [<span data-ttu-id="6daaa-193">Microsoft 團隊會啟動澳大利亞和日本資料派駐服務</span><span class="sxs-lookup"><span data-stu-id="6daaa-193">Microsoft Teams Launches Australia and Japan Data Residency</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827)

- [<span data-ttu-id="6daaa-194">Microsoft 團隊隨即推出加拿大的加拿大資料派駐、澳大利亞和日本</span><span class="sxs-lookup"><span data-stu-id="6daaa-194">Microsoft Teams Launches Canada Data Residency, Australia and Japan coming soon</span></span>](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178)
