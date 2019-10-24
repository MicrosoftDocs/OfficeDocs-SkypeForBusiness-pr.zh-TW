---
title: Outlook 網頁版的商務用 Skype Online 支援
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
f1keywords: None
ms.custom:
- Setup
description: Office 365 中的 outlook 網頁版（Outlook Web App）從流覽列提供基本的商務用 Skype web 用戶端。 這個基本用戶端可供系統管理員尚未針對其 Office 365 組織設定 vanity URL 的線上使用者使用。 只要使用者的帳戶處於線上狀態且沒有 vanity URL，即使其組織有一些託管于內部部署的使用者帳戶，他們仍會看到體驗。 在內部部署使用者帳戶（無論是否有 vanity URL）或由 Microsoft 管理的使用者，都會在 Outlook web app 中看到 Lync 體驗。
ms.openlocfilehash: 3a985bd8ad0a04198501ca8d1ec780496c59f561
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "37642515"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="d0158-106">Outlook 網頁版的商務用 Skype Online 支援</span><span class="sxs-lookup"><span data-stu-id="d0158-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="d0158-107">Office 365 中的 outlook 網頁版（Outlook Web App）從流覽列提供基本的商務用 Skype web 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d0158-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="d0158-108">這個基本用戶端可供系統管理員尚未針對其 Office 365 組織設定 vanity URL 的線上使用者使用。</span><span class="sxs-lookup"><span data-stu-id="d0158-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="d0158-109">只要使用者的帳戶處於線上狀態且沒有 vanity URL，即使其組織有一些託管于內部部署的使用者帳戶，他們仍會看到體驗。</span><span class="sxs-lookup"><span data-stu-id="d0158-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="d0158-110">在內部部署使用者帳戶（無論是否有 vanity URL）或由 Microsoft 管理的使用者，都會在 Outlook web app 中看到 Lync 體驗。</span><span class="sxs-lookup"><span data-stu-id="d0158-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="d0158-111">下表摘要列出您可能擁有的不同設置，以及所使用的網頁用戶端。</span><span class="sxs-lookup"><span data-stu-id="d0158-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d0158-112">**使用者帳戶位於**</span><span class="sxs-lookup"><span data-stu-id="d0158-112">**User account is located**</span></span> <br/> |<span data-ttu-id="d0158-113">**已設定 Vanity URL，或有專屬的組織**</span><span class="sxs-lookup"><span data-stu-id="d0158-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="d0158-114">**商務用 Skype 或 Lync 體驗？**</span><span class="sxs-lookup"><span data-stu-id="d0158-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="d0158-115">Online</span><span class="sxs-lookup"><span data-stu-id="d0158-115">Online</span></span>  <br/> |<span data-ttu-id="d0158-116">不</span><span class="sxs-lookup"><span data-stu-id="d0158-116">No</span></span>  <br/> |<span data-ttu-id="d0158-117">商務用 Skype 網頁版體驗</span><span class="sxs-lookup"><span data-stu-id="d0158-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="d0158-118">Online</span><span class="sxs-lookup"><span data-stu-id="d0158-118">Online</span></span>  <br/> |<span data-ttu-id="d0158-119">是的</span><span class="sxs-lookup"><span data-stu-id="d0158-119">Yes</span></span>  <br/> |<span data-ttu-id="d0158-120">Lync web 體驗</span><span class="sxs-lookup"><span data-stu-id="d0158-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d0158-121">混合式但駐留在線上</span><span class="sxs-lookup"><span data-stu-id="d0158-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="d0158-122">不</span><span class="sxs-lookup"><span data-stu-id="d0158-122">No</span></span>  <br/> |<span data-ttu-id="d0158-123">商務用 Skype 網頁版體驗</span><span class="sxs-lookup"><span data-stu-id="d0158-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="d0158-124">混合式但駐留在線上</span><span class="sxs-lookup"><span data-stu-id="d0158-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="d0158-125">是的</span><span class="sxs-lookup"><span data-stu-id="d0158-125">Yes</span></span>  <br/> |<span data-ttu-id="d0158-126">Lync web 體驗</span><span class="sxs-lookup"><span data-stu-id="d0158-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d0158-127">混合式但以內部部署為宿主</span><span class="sxs-lookup"><span data-stu-id="d0158-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="d0158-128">不</span><span class="sxs-lookup"><span data-stu-id="d0158-128">No</span></span>  <br/> |<span data-ttu-id="d0158-129">Lync web 體驗</span><span class="sxs-lookup"><span data-stu-id="d0158-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d0158-130">混合式但以內部部署為宿主</span><span class="sxs-lookup"><span data-stu-id="d0158-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="d0158-131">是的</span><span class="sxs-lookup"><span data-stu-id="d0158-131">Yes</span></span>  <br/> |<span data-ttu-id="d0158-132">Lync web 體驗</span><span class="sxs-lookup"><span data-stu-id="d0158-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d0158-133">在內部部署上純粹</span><span class="sxs-lookup"><span data-stu-id="d0158-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="d0158-134">不</span><span class="sxs-lookup"><span data-stu-id="d0158-134">No</span></span>  <br/> |<span data-ttu-id="d0158-135">Lync web 體驗</span><span class="sxs-lookup"><span data-stu-id="d0158-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="d0158-136">在內部部署上純粹</span><span class="sxs-lookup"><span data-stu-id="d0158-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="d0158-137">是的</span><span class="sxs-lookup"><span data-stu-id="d0158-137">Yes</span></span>  <br/> |<span data-ttu-id="d0158-138">Lync web 體驗</span><span class="sxs-lookup"><span data-stu-id="d0158-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="d0158-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="d0158-139">Related topics</span></span>
[<span data-ttu-id="d0158-140">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="d0158-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="d0158-141">讓商務用 Skype 使用者新增 Skype 連絡人</span><span class="sxs-lookup"><span data-stu-id="d0158-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
