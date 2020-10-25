---
title: 設定商務用 Skype Online 的顯示狀態
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: ce59ac0b-8115-4c6b-8174-e3aef982d3cb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- O365P_OnlinePresenceDesc
description: '瞭解如何設定商務用 Skype，讓您可以查看同事的可用性。 '
ms.openlocfilehash: f2b149a2b6277d356fe4478ee6de12ec6b078f48
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753448"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="cd174-103">設定商務用 Skype Online 的顯示狀態</span><span class="sxs-lookup"><span data-stu-id="cd174-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd174-104">Microsoft 團隊系統管理中心已將商務用 Skype 系統管理中心 (舊版入口網站) 。</span><span class="sxs-lookup"><span data-stu-id="cd174-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="cd174-105">管理商務用 Skype 的所有設定現在都是在團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="cd174-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="cd174-106">您必須獲指派全域系統管理員或商務用 Skype 系統管理員的 [AZURE AD 管理員角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能管理團隊系統管理中心的商務用 skype 功能。</span><span class="sxs-lookup"><span data-stu-id="cd174-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="cd174-107">若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="cd174-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="cd174-108">根據預設，任何可以使用商務用 Skype 與組織中的人員進行通訊的人，也可以查看該人員是否處於線上狀態。</span><span class="sxs-lookup"><span data-stu-id="cd174-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="cd174-109">[商務用 Skype] 會顯示人員是否可在線上、會議、離線或其他標記中取得。</span><span class="sxs-lookup"><span data-stu-id="cd174-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![在商務用 Skype 中某人線上狀態的範例。](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="cd174-111">作為企業中每個人的系統 **[管理員](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** ，您可以選擇誰能在商務用 Skype 中看到他們的線上狀態。</span><span class="sxs-lookup"><span data-stu-id="cd174-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="cd174-112">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="cd174-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="cd174-113">移至系統管理中心 > 系統**管理中心**  >  **商務用 Skype**。</span><span class="sxs-lookup"><span data-stu-id="cd174-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="cd174-114">在 **商務用 Skype 系統管理中心**中，選擇 [ **組織**]。</span><span class="sxs-lookup"><span data-stu-id="cd174-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="cd174-115">在 [目前 **狀態隱私權模式]** 底下，選取下列其中一個設定，然後選擇 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="cd174-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="cd174-116">**設定**</span><span class="sxs-lookup"><span data-stu-id="cd174-116">**Setting**</span></span>|<span data-ttu-id="cd174-117">**誰可以查看使用者的目前狀態**</span><span class="sxs-lookup"><span data-stu-id="cd174-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cd174-118">**自動顯示目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="cd174-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="cd174-119">貴公司中尚未新增至人員 **外部** 或 **封鎖** 清單的任何商務用 Skype 使用者，都能看到該人員的線上狀態。</span><span class="sxs-lookup"><span data-stu-id="cd174-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="cd174-120">**只向使用者的連絡人顯示目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="cd174-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="cd174-121">人員連絡人清單中尚未新增至其 [ **外部** ] 或 [已 **封鎖** ] 清單的任何人。</span><span class="sxs-lookup"><span data-stu-id="cd174-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="cd174-122">個人可以在其商務用 Skype app 中覆寫您的預設設定： [**設定**  >  **工具**]  >  **選項**。</span><span class="sxs-lookup"><span data-stu-id="cd174-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="cd174-123">如需使用者可以在商務用 Skype 中變更哪些內容的相關資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="cd174-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="cd174-124">控制在商務用 Skype 中您目前狀態資訊的存取權</span><span class="sxs-lookup"><span data-stu-id="cd174-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="cd174-125">在商務用 Skype 中設定狀態選項</span><span class="sxs-lookup"><span data-stu-id="cd174-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="cd174-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="cd174-126">Related topics</span></span>

[<span data-ttu-id="cd174-127">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="cd174-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="cd174-128">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="cd174-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


