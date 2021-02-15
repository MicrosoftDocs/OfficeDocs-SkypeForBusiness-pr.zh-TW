---
title: Microsoft Teams 中的公開預覽
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解 Microsoft Teams 中的公開預覽。嘗試新功能並提供意見反應。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 60ed1c821389fb56d6e6bfb4ab4a37e562be726a
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196217"
---
# <a name="microsoft-teams-public-preview"></a><span data-ttu-id="a0f6e-104">Microsoft Teams 公開預覽</span><span class="sxs-lookup"><span data-stu-id="a0f6e-104">Microsoft Teams Public Preview</span></span>

> [!NOTE]
> <span data-ttu-id="a0f6e-p102">預覽中包含的功能可能不完整，且在公開發行之前可能會變更。提供預覽版僅針對評估和探索目的。Office 365 政府社群雲端 (GCC) 中不支援。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-p102">Features included in preview might not be complete, and might undergo changes before becoming available in the public release. They're provided for evaluation and exploration purposes only. Not supported in Office 365 Government Community Cloud (GCC).</span></span>

<span data-ttu-id="a0f6e-p103">Microsoft Teams 的公開預覽可提供 Teams 中尚未發行功能的早期存取。預覽版可讓您探索並測試即將推出的功能。我們也歡迎您提供對於公開預覽中任何功能的意見反應。公開預覽將針對每個 Teams 使用者啟用，因此您不需要擔心會影響整個組織。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-p103">Public Preview for Microsoft Teams provides early access to unreleased features in Teams. Previews allow you to explore and test upcoming features. We also welcome feedback on any feature in public previews. Public preview is enabled per Team user, so you don't need to worry about affecting your entire organization.</span></span>

<span data-ttu-id="a0f6e-112">如需 Teams 公開預覽中所提供內容的清單，請瀏覽 [Office 目前通道 (預覽) 的版本資訊](https://docs.microsoft.com/officeupdates/current-channel-preview)。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-112">For a list of what's available in the Teams public preview, visit [Release Notes for Office Current Channel (Preview)](https://docs.microsoft.com/officeupdates/current-channel-preview).</span></span>

## <a name="set-the-update-policy"></a><span data-ttu-id="a0f6e-113">設定更新原則</span><span class="sxs-lookup"><span data-stu-id="a0f6e-113">Set the Update policy</span></span>

<span data-ttu-id="a0f6e-114">公開預覽將針對以每個使用者為基礎啟用，而開啟公開預覽的選項會在系統管理原則中控制。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-114">Public preview is enabled on a per-user basis, and the option to turn on public preview is controlled in an admin policy.</span></span> <span data-ttu-id="a0f6e-115">更新原則可用來管理會在 Teams 應用程式中看到搶鮮版或預覽版功能的 Teams 和 Office 預覽版使用者。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-115">Update policies are used to manage Teams and Office preview users who will see pre-release or preview features in the Teams app.</span></span> <span data-ttu-id="a0f6e-116">您可以使用全域 (全組織預設值) 原則並進行自訂，或為您的使用者建立一或多個自訂原則。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-116">You can use the Global (Org-wide default) policy and customize it, or create one or more custom policies for your users.</span></span> <span data-ttu-id="a0f6e-117">因為該原則不會覆寫全域原則，必須將原則指派給特定使用者。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-117">The policy needs to be assigned to specific users because it doesn't over-write the global policy.</span></span>

1. <span data-ttu-id="a0f6e-118">登入系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-118">Sign in to the admin center.</span></span>
2. <span data-ttu-id="a0f6e-119">選取 [Teams **]** > [更新原則 **]**。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-119">Select **Teams**>**Update policies**.</span></span>

   ![選取 [更新原則] 選項](media/updatePolicies.png)

3. <span data-ttu-id="a0f6e-121">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-121">Select **Add**.</span></span>
4. <span data-ttu-id="a0f6e-122">為更新原則命名，新增描述，然後開啟 [顯示預覽功能 **]**。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-122">Name the update policy, add a description, and turn on **Show preview features**.</span></span>

<span data-ttu-id="a0f6e-123">您也可以使用 `CsTeamsUpdateManagementPolicy` Cmdlet 透過 PowerShell 設定原則。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-123">You can also set the policy using PowerShell using the `CsTeamsUpdateManagementPolicy` cmdlet.</span></span>

## <a name="enable-public-preview"></a><span data-ttu-id="a0f6e-124">啟用公開預覽</span><span class="sxs-lookup"><span data-stu-id="a0f6e-124">Enable public preview</span></span>

<span data-ttu-id="a0f6e-125">若要在桌面或 Web 用戶端上啟用公開預覽，您必須執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="a0f6e-125">To enable the public preview on a desktop or web client, you need to do the following tasks:</span></span>

1. <span data-ttu-id="a0f6e-126">選取您的設定檔以顯示 Teams 功能表。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-126">Select your profile to display the Teams menu.</span></span>
2. <span data-ttu-id="a0f6e-127">選取 [關於] → [公開預覽]。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-127">Select **About** → **Public preview**.</span></span>
3. <span data-ttu-id="a0f6e-128">選取 [切換至公開預覽]。</span><span class="sxs-lookup"><span data-stu-id="a0f6e-128">Select **Switch to Public preview**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0f6e-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="a0f6e-129">Related topics</span></span>

[<span data-ttu-id="a0f6e-130">公開開發人員預覽</span><span class="sxs-lookup"><span data-stu-id="a0f6e-130">Public developer preview</span></span>](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

