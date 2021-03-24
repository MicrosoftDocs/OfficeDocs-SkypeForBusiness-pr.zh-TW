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
description: '瞭解如何設定商務用 Skype，以便查看同事的可用性。 '
ms.openlocfilehash: 807b2dd15b3bdbe1fac42192ed9052b26bf1f256
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093487"
---
# <a name="configure-presence-in-skype-for-business-online"></a><span data-ttu-id="fac07-103">設定商務用 Skype Online 的顯示狀態</span><span class="sxs-lookup"><span data-stu-id="fac07-103">Configure presence in Skype for Business Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fac07-104">Microsoft Teams 系統管理中心已取代商務用 Skype 系統管理中心 (舊版) 。</span><span class="sxs-lookup"><span data-stu-id="fac07-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="fac07-105">管理商務用 Skype 的所有設定現在都位於 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="fac07-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="fac07-106">您必須被指派全域系統管理員或商務用 Skype 系統管理員的 Azure [AD](/azure/active-directory/roles/permissions-reference) 系統管理員角色，才能在 Teams 系統管理中心管理商務用 Skype 功能。</span><span class="sxs-lookup"><span data-stu-id="fac07-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="fac07-107">若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="fac07-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="fac07-108">根據預設，任何可以使用商務用 Skype 與您組織中其中一個人通訊的人，也可以查看該人員是否在線上。</span><span class="sxs-lookup"><span data-stu-id="fac07-108">By default, anyone who can communicate with one of the people in your organization using Skype for Business can also see whether that person is online.</span></span> <span data-ttu-id="fac07-109">商務用 Skype 會顯示人員是否可在線上、會議、離線或其他指示器中使用。</span><span class="sxs-lookup"><span data-stu-id="fac07-109">Skype for Business shows whether a person is available online, in a meeting, offline, or another indicator.</span></span>

![商務用 Skype 中的人員線上狀態範例。](../images/f0849132-1ddb-480f-bca6-cfe9eaa0486d.png)

<span data-ttu-id="fac07-111">做 **[為商務](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 用 Skype 的系統管理員，您可以選擇誰可以看到他們在商務用 Skype 中的線上形象。</span><span class="sxs-lookup"><span data-stu-id="fac07-111">As the **[admin](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** for everyone in your business, you can choose who sees their online presence in Skype for Business.</span></span>

<span data-ttu-id="fac07-112">![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="fac07-112">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="fac07-113">請前往系統管理中心>**系統管理中心**  >  **商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="fac07-113">Go to the admin center > **Admin centers** > **Skype for Business**.</span></span>

2. <span data-ttu-id="fac07-114">在商務 **用 Skype 系統管理中心\*\*\*\*，選擇組織**。</span><span class="sxs-lookup"><span data-stu-id="fac07-114">In the **Skype for Business admin center**, choose **organization**.</span></span>

3. <span data-ttu-id="fac07-115">在 **目前狀態隱私權模式中**，選取下列其中一個設定， **然後選擇儲存**。</span><span class="sxs-lookup"><span data-stu-id="fac07-115">Under **presence privacy mode**, select one of the following settings, and then choose **Save**.</span></span>

|<span data-ttu-id="fac07-116">**設定**</span><span class="sxs-lookup"><span data-stu-id="fac07-116">**Setting**</span></span>|<span data-ttu-id="fac07-117">**誰可以查看使用者目前狀態**</span><span class="sxs-lookup"><span data-stu-id="fac07-117">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fac07-118">**自動顯示目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="fac07-118">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="fac07-119">任何商務用 Skype 使用者，如果尚未新增到某人的外部或封鎖清單，將能看到該人員的線上狀態。</span><span class="sxs-lookup"><span data-stu-id="fac07-119">Any Skype for Business user in your business who has not been added to a person's **External** or **Blocked** list will be able to see that person's online presence.</span></span> <br/> |
|<span data-ttu-id="fac07-120">**只向使用者的連絡人顯示目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="fac07-120">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="fac07-121">人員連絡人清單中尚未新增到其外部或封鎖清單中的 **任何人**。 </span><span class="sxs-lookup"><span data-stu-id="fac07-121">Anyone in a person's Contacts list who they have not added to their **External** or **Blocked** list.</span></span> <br/> <span data-ttu-id="fac07-122">個人可以在商務用 Skype App 中重寫您的預設設定：**設定**  >  **工具**  >  **選項**。</span><span class="sxs-lookup"><span data-stu-id="fac07-122">Individuals can override your default settings in their Skype for Business app: **Settings** > **Tools** > **Options**.</span></span> <br/> |

<span data-ttu-id="fac07-123">有關使用者在商務用 Skype 中可變更內容的資訊，請參閱以下文章：</span><span class="sxs-lookup"><span data-stu-id="fac07-123">For information about what your users can change in Skype for Business, see these articles:</span></span>

- [<span data-ttu-id="fac07-124">控制在商務用 Skype 中存取您的目前狀態資訊</span><span class="sxs-lookup"><span data-stu-id="fac07-124">Control access to your presence information in Skype for Business</span></span>](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)

- [<span data-ttu-id="fac07-125">在商務用 Skype 中設定狀態選項</span><span class="sxs-lookup"><span data-stu-id="fac07-125">Set Status options in Skype for Business</span></span>](https://support.office.com/article/efd25395-c8ef-4510-b9cb-6f70e2fff8a0)

## <a name="related-topics"></a><span data-ttu-id="fac07-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="fac07-126">Related topics</span></span>

[<span data-ttu-id="fac07-127">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="fac07-127">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fac07-128">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="fac07-128">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)