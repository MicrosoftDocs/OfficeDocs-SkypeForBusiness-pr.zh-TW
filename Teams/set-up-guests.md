---
title: 開啟或關閉 Microsoft Teams 的來賓存取
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: 瞭解如何以 Office 365 系統管理員身份在 Microsoft Teams 中開啟或關閉來賓存取功能。
ms.openlocfilehash: c82172eb4d0c9fe50832d45ce2146c89d7e6d7d8
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884517"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="dc3ff-103">開啟或關閉 Microsoft Teams 的來賓存取</span><span class="sxs-lookup"><span data-stu-id="dc3ff-103">Turn on or turn off guest access to Microsoft Teams</span></span>

> [!Note]

> <span data-ttu-id="dc3ff-104">在 **2021 年 2** 月之前，來賓存取預設為關閉。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-104">Until **February 2021**, guest access is turned off by default.</span></span> <span data-ttu-id="dc3ff-105">在系統管理員或小組擁有者可以新增來賓之前，必須為 Teams 開啟來賓存取。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span> <span data-ttu-id="dc3ff-106">開啟來賓存取權後，變更可能需要幾個小時才能生效。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-106">After you turn on guest access, it might take a few hours for the changes to take effect.</span></span> <span data-ttu-id="dc3ff-107">如果使用者在嘗試將來賓新到小組時看到訊息，請連上您的系統管理員，可能是來賓存取尚未開啟，或是設定尚未生效。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-107">If users see the message **Contact your administrator** when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> <span data-ttu-id="dc3ff-108">**2021** 年 2 月之後，對於尚未設定此設定的現有客戶&，Microsoft Teams 中的來賓存取預設會開啟。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-108">After **February 2021**, guest access in Microsoft Teams will be turned on by default for new customers & existing customers who haven't configured this setting.</span></span> <span data-ttu-id="dc3ff-109">執行此變更時，如果您尚未在 Microsoft Teams 中配置來賓存取功能，該功能就會在租使用者中啟用。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-109">When this change is implemented, if you've not already configured guest access capability in Microsoft Teams, that capability will be enabled in your tenant.</span></span> <span data-ttu-id="dc3ff-110">如果您希望貴組織的來賓存取保持停用狀態，您必須確認來賓存取設定已設定為 **關閉，而非\*\*\*\*服務預設值**。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-110">If you want guest access to remain disabled for your organization, you'll need to confirm that the guest access setting is set to **Off** instead of **Service default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc3ff-111">開啟來賓存取取決於 Azure Active Directory、Microsoft 365、SharePoint 和 Teams 的設定。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-111">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="dc3ff-112">如需詳細資訊，請參閱 [在小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-112">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="dc3ff-113">在 Teams 系統管理中心設定來賓存取</span><span class="sxs-lookup"><span data-stu-id="dc3ff-113">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="dc3ff-114">登入 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-114">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="dc3ff-115">選取 **[全組織設定]** > **[來賓存取]**。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-115">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="dc3ff-116">將 **[允許 Microsoft Teams 中的來賓存取]** 設定為 **[開啟]**。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-116">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="dc3ff-117">允許來賓存取開關設定為開啟</span><span class="sxs-lookup"><span data-stu-id="dc3ff-117">Allow guest access switch set to On</span></span> ](media/guest-access-setting.png)

4. <span data-ttu-id="dc3ff-118">在 **[通話]**、**[會議]** 和 **[通訊]** 下，根據要允許來賓使用者使用的功能，為每個功能選擇 **[開啟]** 或 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-118">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="dc3ff-119">**進行私人通話** – **[開啟]** 此設定可允許來賓進行對等呼叫。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-119">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="dc3ff-120">**允許 IP 視訊** - **[開啟]** 此設定可允許來賓在其通話和會議中使用視訊。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-120">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="dc3ff-121">**螢幕畫面分享模式** – 此設定控制來賓使用者的螢幕畫面分享可用性。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-121">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span>
          - <span data-ttu-id="dc3ff-122">將此設定設定為 **[停用]** 以移除來賓在 Teams 中共用其螢幕的功能。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-122">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span>
          - <span data-ttu-id="dc3ff-123">將此設定設定為 **[單一應用程式]** 以允許共用單個應用程式。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-123">Turn this setting to **Single application** to allow sharing of individual applications.</span></span>
          - <span data-ttu-id="dc3ff-124">將此設定設定為 **[整個螢幕]** 以允許完整的螢幕畫面分享。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-124">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="dc3ff-125">**允許立即開會** – **[開啟]** 此設定可允許來賓使用 Microsoft Teams 中的 [立即開會] 功能。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-125">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="dc3ff-126">**編輯已傳送的訊息** - **[開啟]** 此設定可允許來賓編輯他們以前傳送的郵件。 </span><span class="sxs-lookup"><span data-stu-id="dc3ff-126">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="dc3ff-127">**來賓可刪除已傳送的訊息** - **[開啟]** 此設定可允許來賓刪除他們以前傳送的郵件。 </span><span class="sxs-lookup"><span data-stu-id="dc3ff-127">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="dc3ff-128">**聊天** –**[開啟]** 此設定可使來賓能够在 Teams 中使用聊天。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-128">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="dc3ff-129">**在交談中使用 Giphy** – **[開啟]** 此設定可允許來賓在交談中使用 Giphys。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-129">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="dc3ff-130">Giphy 是線上資料庫和搜尋引擎，允許使用者搜尋和共用 GIF 動畫檔案。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-130">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="dc3ff-131">每個 Giphy 都有內容分級。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-131">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="dc3ff-132">**Giphy 內容分級** –  從下拉式清單中選取分級：</span><span class="sxs-lookup"><span data-stu-id="dc3ff-132">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="dc3ff-133">**[允許所有內容]** - 來賓可以在聊天中插入所有 Giphy，而無論內容分級為何。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-133">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="dc3ff-134">**[中等]**，來賓可以在聊天中插入 Giphy，但會適當限制成人內容。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-134">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="dc3ff-135">**嚴格** - 來賓可以在聊天中插入 Giphys，但禁止插入成人內容。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-135">**Strict** – Guests can insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="dc3ff-136">**在交談中使用 Meme** – **[開啟]** 此設定可允許來賓在交談中使用 Meme。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-136">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="dc3ff-137">**在交談中使用貼圖** – **[開啟]** 此設定可允許來賓在交談中使用貼圖。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-137">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span>

    ![Teams 中的來賓權限設定](media/manage-guest-access-image1.png)

5. <span data-ttu-id="dc3ff-139">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="dc3ff-139">Select **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="dc3ff-140">外部存取 (同盟) 與來賓存取</span><span class="sxs-lookup"><span data-stu-id="dc3ff-140">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="dc3ff-141">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dc3ff-141">See also</span></span>

[<span data-ttu-id="dc3ff-142">使用 Microsoft 365 設定安全的共同作業</span><span class="sxs-lookup"><span data-stu-id="dc3ff-142">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="dc3ff-143">封鎖特定小組的來賓使用者</span><span class="sxs-lookup"><span data-stu-id="dc3ff-143">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="dc3ff-144">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="dc3ff-144">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)
