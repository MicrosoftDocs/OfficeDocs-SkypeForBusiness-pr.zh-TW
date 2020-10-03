---
title: 開啟或關閉 Microsoft 團隊的來賓存取權
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: 瞭解如何開啟或關閉 Microsoft 團隊中的來賓存取功能做為 Office 365 系統管理員。
ms.openlocfilehash: aa4530979054efc5a1aeb2c8fe0afa622b893f9d
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346324"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="72561-103">開啟或關閉 Microsoft 團隊的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="72561-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="72561-104">根據預設，來賓存取權會關閉。</span><span class="sxs-lookup"><span data-stu-id="72561-104">By default, guest access is turned off.</span></span> <span data-ttu-id="72561-105">您必須先開啟團隊的來賓存取權，系統管理員或團隊擁有者才能新增來賓。</span><span class="sxs-lookup"><span data-stu-id="72561-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="72561-106">開啟來賓存取後，可能需要幾個小時的時間，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="72561-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="72561-107">當使用者嘗試將來賓新增到其小組時，如果使用者看到「與您的系統管理員聯繫」訊息，可能是因為來賓存取尚未開啟，或是設定尚未生效。</span><span class="sxs-lookup"><span data-stu-id="72561-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72561-108">開啟來賓存取權視 Azure Active Directory、Microsoft 365、SharePoint 和團隊中的設定而定。</span><span class="sxs-lookup"><span data-stu-id="72561-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="72561-109">如需詳細資訊，請參閱 [與團隊中的來賓共同](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)作業。</span><span class="sxs-lookup"><span data-stu-id="72561-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="72561-110">在團隊系統管理中心設定來賓存取</span><span class="sxs-lookup"><span data-stu-id="72561-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="72561-111">登入 [Microsoft 團隊系統管理中心](https://admin.teams.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="72561-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="72561-112">選取 [全**組織性設定**  >  **來賓存取**]。</span><span class="sxs-lookup"><span data-stu-id="72561-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="72561-113">將 **Microsoft 團隊中的 [允許來賓存取** 權設定為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="72561-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="72561-114">[允許來賓存取開關設定為開啟]</span><span class="sxs-lookup"><span data-stu-id="72561-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="72561-115">在 [ **通話**]、[ **會議**] 和 [ **訊息**] 底下，針對每個功能選取 [ **開啟** ] 或 [ **關閉** ]，視您想要來賓使用者的需求而定。</span><span class="sxs-lookup"><span data-stu-id="72561-115">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="72561-116">**撥打私人電話** **–開啟此設定可** 讓來賓進行對等通話。</span><span class="sxs-lookup"><span data-stu-id="72561-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="72561-117">[**允許 IP 影片**] **-開啟此設定可**讓來賓在通話和會議中使用影片。</span><span class="sxs-lookup"><span data-stu-id="72561-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="72561-118">**螢幕共用模式** –此設定會控制來賓使用者螢幕共用的可用性。</span><span class="sxs-lookup"><span data-stu-id="72561-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="72561-119">將此設定設為 [ **停用** ]，移除來賓在小組中共用畫面的功能。</span><span class="sxs-lookup"><span data-stu-id="72561-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="72561-120">將此設定轉換為 [ **單一應用程式** ] 以允許共用個別的應用程式。</span><span class="sxs-lookup"><span data-stu-id="72561-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="72561-121">將此設定設為 [ **整個畫面** ] 以允許完整的螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="72561-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="72561-122">[**允許立即開會**] –開啟**此設定可讓來賓在 Microsoft**團隊中使用 [立即開會] 功能。</span><span class="sxs-lookup"><span data-stu-id="72561-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="72561-123">**編輯已傳送的郵件** **-開啟此設定，** 允許來賓編輯先前傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="72561-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="72561-124">**來賓可以刪除已傳送的郵件** –開啟 **此設定，** 允許來賓刪除先前傳送的郵件。</span><span class="sxs-lookup"><span data-stu-id="72561-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="72561-125">[**聊天**] **：開啟此設定可**讓客人在團隊中使用聊天功能。</span><span class="sxs-lookup"><span data-stu-id="72561-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="72561-126">**在交談中使用 giphy** –開啟此 **設定可讓來賓在交談** 中使用 giphy。</span><span class="sxs-lookup"><span data-stu-id="72561-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="72561-127">Giphy 是線上資料庫和搜尋引擎，可讓使用者搜尋及共用動畫 GIF 檔案。</span><span class="sxs-lookup"><span data-stu-id="72561-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="72561-128">每個 Giphy 都會獲指派內容評級。</span><span class="sxs-lookup"><span data-stu-id="72561-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="72561-129">**Giphy 內容分級** –從下拉式清單中選取評分：</span><span class="sxs-lookup"><span data-stu-id="72561-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="72561-130">[**允許所有內容**-來賓] 能在聊天中插入所有 giphy，無論內容分級為何。</span><span class="sxs-lookup"><span data-stu-id="72561-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="72561-131">[**適中**]-訪客將能在聊天中插入 giphy，但將會針對成人內容適度地限制。</span><span class="sxs-lookup"><span data-stu-id="72561-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="72561-132">[**嚴格**]-來賓將能在聊天中插入 giphy，但會限制插入成人內容。</span><span class="sxs-lookup"><span data-stu-id="72561-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="72561-133">**在交談中使用 meme** -開啟此 **設定可讓來賓在交談** 中使用 meme。</span><span class="sxs-lookup"><span data-stu-id="72561-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="72561-134">**在交談中使用不乾膠** 圖示，請 **開啟此設定，** 以允許來賓在交談中使用不乾膠圖示。</span><span class="sxs-lookup"><span data-stu-id="72561-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![團隊中的來賓許可權設定](media/manage-guest-access-image1.png)

5. <span data-ttu-id="72561-136">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="72561-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="72561-137">外部存取 (同盟) 與來賓存取</span><span class="sxs-lookup"><span data-stu-id="72561-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="72561-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="72561-138">See also</span></span>

[<span data-ttu-id="72561-139">使用 Microsoft 365 設定安全的共同作業</span><span class="sxs-lookup"><span data-stu-id="72561-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="72561-140">封鎖特定團隊的來賓使用者</span><span class="sxs-lookup"><span data-stu-id="72561-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="72561-141">Set-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="72561-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)