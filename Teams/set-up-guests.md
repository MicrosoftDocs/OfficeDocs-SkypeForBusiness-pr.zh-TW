---
title: 開啟或關閉 Microsoft 團隊的來賓存取權
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: 開啟或關閉 Microsoft 團隊中的來賓存取功能。
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: 240e93d5f6329090940e6bf49cb2d6a4ee46ce2f
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2019
ms.locfileid: "36184347"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="81cd7-103">開啟或關閉 Microsoft 團隊的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="81cd7-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="81cd7-104">做為 Office 365 系統管理員, 您必須先啟用來賓功能, 您或貴組織的使用者 (特別是團隊擁有者) 才能新增來賓。</span><span class="sxs-lookup"><span data-stu-id="81cd7-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="81cd7-105">來賓設定是在 Azure Active Directory 中設定。</span><span class="sxs-lookup"><span data-stu-id="81cd7-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="81cd7-106">在您的 Office 365 組織中, 變更的時間必須是2小時到24小時才能生效。</span><span class="sxs-lookup"><span data-stu-id="81cd7-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="81cd7-107">當使用者嘗試將來賓新增到其小組時, 如果使用者看到「與您的系統管理員聯繫」的訊息, 可能是因為來賓功能尚未啟用或設定尚未生效。</span><span class="sxs-lookup"><span data-stu-id="81cd7-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81cd7-108">若要啟用來賓存取功能的完整體驗, 請務必瞭解 Microsoft 團隊、Azure Active Directory 和 Office 365 之間的核心授權相依性。</span><span class="sxs-lookup"><span data-stu-id="81cd7-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="81cd7-109">如需詳細資訊, 請參閱[授權 Microsoft 團隊中的來賓存取](Teams-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="81cd7-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="81cd7-110">來賓存取與外部存取 (同盟)</span><span class="sxs-lookup"><span data-stu-id="81cd7-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="81cd7-111">在 Microsoft [團隊管理中心] 中設定來賓存取</span><span class="sxs-lookup"><span data-stu-id="81cd7-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="81cd7-112">登入 Microsoft 團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="81cd7-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="81cd7-113">選取 [全**組織性設定** > **來賓存取**]。</span><span class="sxs-lookup"><span data-stu-id="81cd7-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="81cd7-114">將**Microsoft 團隊中的 [允許來賓存取**] 切換為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="81cd7-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="81cd7-115">[允許來賓存取開關設定為開啟]</span><span class="sxs-lookup"><span data-stu-id="81cd7-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="81cd7-116">根據您要允許來賓使用者的功能, 將 [**通話**]、[**會議**] 和 [**訊息**] 下的切換設定為 [**開啟**] 或 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="81cd7-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="81cd7-117">**撥打私人電話**–開啟此設定\*\*\*\* 可讓來賓進行對等通話。</span><span class="sxs-lookup"><span data-stu-id="81cd7-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="81cd7-118">[**允許 IP 影片**]-開啟\*\*\*\* 此設定可讓來賓在通話和會議中使用影片。</span><span class="sxs-lookup"><span data-stu-id="81cd7-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="81cd7-119">**螢幕共用模式**–此設定會控制來賓使用者螢幕共用的可用性。</span><span class="sxs-lookup"><span data-stu-id="81cd7-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="81cd7-120">將此設定設為 [**停用**], 移除來賓在小組中共用畫面的功能。</span><span class="sxs-lookup"><span data-stu-id="81cd7-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="81cd7-121">將此設定轉換為 [**單一應用程式**] 以允許共用個別的應用程式。</span><span class="sxs-lookup"><span data-stu-id="81cd7-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="81cd7-122">將此設定設為 [**整個畫面**] 以允許完整的螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="81cd7-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="81cd7-123">[**允許立即開會**] –開啟\*\*\*\* 此設定可讓來賓在 Microsoft 團隊中使用 [立即開會] 功能。</span><span class="sxs-lookup"><span data-stu-id="81cd7-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="81cd7-124">**編輯已傳送的郵件**-開啟\*\*\*\* 此設定, 允許來賓編輯先前傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="81cd7-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="81cd7-125">**來賓可以刪除已傳送的郵件**–開啟\*\*\*\* 此設定, 允許來賓刪除先前傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="81cd7-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="81cd7-126">[**聊天**]: 開啟\*\*\*\* 此設定可讓客人在團隊中使用聊天功能。</span><span class="sxs-lookup"><span data-stu-id="81cd7-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="81cd7-127">**在交談中使用 giphy** –開啟此\*\*\*\* 設定可讓來賓在交談中使用 giphy。</span><span class="sxs-lookup"><span data-stu-id="81cd7-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="81cd7-128">Giphy 是線上資料庫和搜尋引擎, 可讓使用者搜尋及共用動畫 GIF 檔案。</span><span class="sxs-lookup"><span data-stu-id="81cd7-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="81cd7-129">每個 Giphy 都會獲指派內容評級。</span><span class="sxs-lookup"><span data-stu-id="81cd7-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="81cd7-130">**Giphy 內容分級**–從下拉式清單中選取評分:</span><span class="sxs-lookup"><span data-stu-id="81cd7-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="81cd7-131">[**允許所有內容**-來賓] 能在聊天中插入所有 giphy, 無論內容分級為何。</span><span class="sxs-lookup"><span data-stu-id="81cd7-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="81cd7-132">[**適中**]-訪客將能在聊天中插入 giphy, 但將會針對成人內容適度地限制。</span><span class="sxs-lookup"><span data-stu-id="81cd7-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="81cd7-133">[**嚴格**]-來賓將能在聊天中插入 giphy, 但會限制插入成人內容。</span><span class="sxs-lookup"><span data-stu-id="81cd7-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
    - <span data-ttu-id="81cd7-134">**在交談中使用 meme** -開啟此\*\*\*\* 設定可讓來賓在交談中使用 meme。</span><span class="sxs-lookup"><span data-stu-id="81cd7-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="81cd7-135">**在交談中使用不乾膠**圖示, 請\*\*\*\* 開啟此設定, 以允許來賓在交談中使用不乾膠圖示。</span><span class="sxs-lookup"><span data-stu-id="81cd7-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="81cd7-136">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="81cd7-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="81cd7-137">使用 PowerShell 開啟或關閉來賓存取</span><span class="sxs-lookup"><span data-stu-id="81cd7-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="81cd7-138">從下載商務用 Skype Online PowerShell 模組https://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="81cd7-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="81cd7-139">將 PowerShell 會話連線到商務用 Skype Online 端點。</span><span class="sxs-lookup"><span data-stu-id="81cd7-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="81cd7-140">檢查您的設定, `AllowGuestUser`如果`$False`是, 請使用[CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) Cmdlet 將它設定為`$True`。</span><span class="sxs-lookup"><span data-stu-id="81cd7-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="81cd7-141">您現在可以在貴組織的小組中擁有來賓使用者。</span><span class="sxs-lookup"><span data-stu-id="81cd7-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="81cd7-142">其他資訊</span><span class="sxs-lookup"><span data-stu-id="81cd7-142">More information</span></span>

<span data-ttu-id="81cd7-143">請觀看下列影片, 以取得更多關於來賓存取的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="81cd7-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="81cd7-144">在 Microsoft 團隊中新增來賓</span><span class="sxs-lookup"><span data-stu-id="81cd7-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
