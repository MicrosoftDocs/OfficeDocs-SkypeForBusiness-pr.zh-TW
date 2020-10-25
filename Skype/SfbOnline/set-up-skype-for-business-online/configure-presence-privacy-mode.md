---
title: 設定目前狀態隱私權模式
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
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
- ms.lync.lac.OrgPresencePrivacy
description: '瞭解如何為您的使用者設定隱私權模式，讓他們能夠更好地控制人們查看其可用性的方式。 '
ms.openlocfilehash: a2b4ed11f1d56927a4bc7eed6ce36b5b04411509
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753438"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="56b23-103">設定目前狀態隱私權模式</span><span class="sxs-lookup"><span data-stu-id="56b23-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56b23-104">Microsoft 團隊系統管理中心已將商務用 Skype 系統管理中心 (舊版入口網站) 。</span><span class="sxs-lookup"><span data-stu-id="56b23-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="56b23-105">管理商務用 Skype 的所有設定現在都是在團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="56b23-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="56b23-106">您必須獲指派全域系統管理員或商務用 Skype 系統管理員的 [AZURE AD 管理員角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能管理團隊系統管理中心的商務用 skype 功能。</span><span class="sxs-lookup"><span data-stu-id="56b23-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="56b23-107">若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="56b23-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="56b23-108">商務用 Skype Online 的 [目前狀態] 設定可讓人員更進一步控制誰能看到他們在會議中，還是不在辦公室。</span><span class="sxs-lookup"><span data-stu-id="56b23-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="56b23-109">如需商務用 Skype 目前狀態及隱私權設定的詳細資料，請參閱 [在商務用 Skype Online 中設定目前狀態](configure-presence-in-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="56b23-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="56b23-110">針對貴組織中的所有人選擇預設的 [線上狀態] 設定</span><span class="sxs-lookup"><span data-stu-id="56b23-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="56b23-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="56b23-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="56b23-112">移至商務用 Skype Online 系統管理中心 > **組織 > 一般**]。</span><span class="sxs-lookup"><span data-stu-id="56b23-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="56b23-113">在 [目前 **狀態隱私權模式]** 底下，選擇設定，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="56b23-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="56b23-114">**設定**</span><span class="sxs-lookup"><span data-stu-id="56b23-114">**Setting**</span></span>|<span data-ttu-id="56b23-115">**誰可以查看使用者的目前狀態**</span><span class="sxs-lookup"><span data-stu-id="56b23-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56b23-116">**自動顯示目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="56b23-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="56b23-117">任何不屬於 [ **外部** ] 或 [ **封鎖** ] 隱私權群組的商務用 Skype 使用者。</span><span class="sxs-lookup"><span data-stu-id="56b23-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="56b23-118">**只向使用者的連絡人顯示目前狀態資訊**</span><span class="sxs-lookup"><span data-stu-id="56b23-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="56b23-119">使用者連絡人清單中不屬於 [ **外部** ] 或 [ **封鎖** ] 隱私權群組的任何人。</span><span class="sxs-lookup"><span data-stu-id="56b23-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="56b23-120">個別使用者可以在 [商務用 Skype **選項** ] 對話方塊中變更此設定。</span><span class="sxs-lookup"><span data-stu-id="56b23-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="56b23-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="56b23-121">Related topics</span></span>
[<span data-ttu-id="56b23-122">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="56b23-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="56b23-123">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="56b23-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
