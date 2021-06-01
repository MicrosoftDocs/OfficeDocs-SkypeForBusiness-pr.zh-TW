---
title: 網頁版 Outlook 的商務用 Skype Online 支援
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Outlook流覽 (Outlook Web App) 網頁Microsoft 365 Office 365流覽商務用 Skype提供基本網頁用戶端。 此基本用戶端適用于其系統管理員尚未為使用者或使用者Microsoft 365虛Office 365。 只要使用者帳戶處於線上狀態且沒有虛名 URL，即使其組織有一些內部部署使用者帳戶，他們仍可看到體驗。 擁有內部部署使用者帳戶的使用者 (無論他們是否有虛名 URL) 或是由 Microsoft 管理的使用者，都會在 Outlook Web 應用程式中看到 Lync 體驗。
ms.openlocfilehash: aa6f82f6647db1816c630486bee0d415d05b3b77
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239568"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="44b87-106">網頁版 Outlook 的商務用 Skype Online 支援</span><span class="sxs-lookup"><span data-stu-id="44b87-106">Skype for Business Online support in Outlook on the web</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="44b87-107">Outlook流覽 (Outlook Web App) 網頁Microsoft 365 Office 365流覽商務用 Skype提供基本網頁用戶端。</span><span class="sxs-lookup"><span data-stu-id="44b87-107">Outlook on the web (Outlook Web App) in Microsoft 365 or Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="44b87-108">此基本用戶端適用于其系統管理員尚未為使用者或使用者Microsoft 365虛Office 365。</span><span class="sxs-lookup"><span data-stu-id="44b87-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Microsoft 365 and Office 365.</span></span> <span data-ttu-id="44b87-109">只要使用者帳戶處於線上狀態且沒有虛名 URL，即使其組織有一些內部部署使用者帳戶，他們仍可看到體驗。</span><span class="sxs-lookup"><span data-stu-id="44b87-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="44b87-110">擁有內部部署使用者帳戶的使用者 (無論他們是否有虛名 URL) 或是由 Microsoft 管理的使用者，都會在 Outlook Web 應用程式中看到 Lync 體驗。</span><span class="sxs-lookup"><span data-stu-id="44b87-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="44b87-111">下表摘要列出您可能擁有的不同設定，以及所使用的 Web 用戶端。</span><span class="sxs-lookup"><span data-stu-id="44b87-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="44b87-112">**使用者帳戶位於**</span><span class="sxs-lookup"><span data-stu-id="44b87-112">**User account is located**</span></span> <br/> |<span data-ttu-id="44b87-113">**虛名 URL 已設成或有專用組織**</span><span class="sxs-lookup"><span data-stu-id="44b87-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="44b87-114">**商務用 Skype Lync 體驗？**</span><span class="sxs-lookup"><span data-stu-id="44b87-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="44b87-115">線上</span><span class="sxs-lookup"><span data-stu-id="44b87-115">Online</span></span>  <br/> |<span data-ttu-id="44b87-116">否</span><span class="sxs-lookup"><span data-stu-id="44b87-116">No</span></span>  <br/> |<span data-ttu-id="44b87-117">商務用 Skype網頁體驗</span><span class="sxs-lookup"><span data-stu-id="44b87-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="44b87-118">線上</span><span class="sxs-lookup"><span data-stu-id="44b87-118">Online</span></span>  <br/> |<span data-ttu-id="44b87-119">是</span><span class="sxs-lookup"><span data-stu-id="44b87-119">Yes</span></span>  <br/> |<span data-ttu-id="44b87-120">Lync Web 體驗</span><span class="sxs-lookup"><span data-stu-id="44b87-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="44b87-121">混合式但線上家用</span><span class="sxs-lookup"><span data-stu-id="44b87-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="44b87-122">否</span><span class="sxs-lookup"><span data-stu-id="44b87-122">No</span></span>  <br/> |<span data-ttu-id="44b87-123">商務用 Skype網頁體驗</span><span class="sxs-lookup"><span data-stu-id="44b87-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="44b87-124">混合式但線上家用</span><span class="sxs-lookup"><span data-stu-id="44b87-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="44b87-125">是</span><span class="sxs-lookup"><span data-stu-id="44b87-125">Yes</span></span>  <br/> |<span data-ttu-id="44b87-126">Lync Web 體驗</span><span class="sxs-lookup"><span data-stu-id="44b87-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="44b87-127">混合式，但位於 prem 上</span><span class="sxs-lookup"><span data-stu-id="44b87-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="44b87-128">否</span><span class="sxs-lookup"><span data-stu-id="44b87-128">No</span></span>  <br/> |<span data-ttu-id="44b87-129">Lync Web 體驗</span><span class="sxs-lookup"><span data-stu-id="44b87-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="44b87-130">混合式，但位於 prem 上</span><span class="sxs-lookup"><span data-stu-id="44b87-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="44b87-131">是</span><span class="sxs-lookup"><span data-stu-id="44b87-131">Yes</span></span>  <br/> |<span data-ttu-id="44b87-132">Lync Web 體驗</span><span class="sxs-lookup"><span data-stu-id="44b87-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="44b87-133">純粹在 prem 上</span><span class="sxs-lookup"><span data-stu-id="44b87-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="44b87-134">否</span><span class="sxs-lookup"><span data-stu-id="44b87-134">No</span></span>  <br/> |<span data-ttu-id="44b87-135">Lync Web 體驗</span><span class="sxs-lookup"><span data-stu-id="44b87-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="44b87-136">純粹在 prem 上</span><span class="sxs-lookup"><span data-stu-id="44b87-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="44b87-137">是</span><span class="sxs-lookup"><span data-stu-id="44b87-137">Yes</span></span>  <br/> |<span data-ttu-id="44b87-138">Lync Web 體驗</span><span class="sxs-lookup"><span data-stu-id="44b87-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="44b87-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="44b87-139">Related topics</span></span>
[<span data-ttu-id="44b87-140">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="44b87-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="44b87-141">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="44b87-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
