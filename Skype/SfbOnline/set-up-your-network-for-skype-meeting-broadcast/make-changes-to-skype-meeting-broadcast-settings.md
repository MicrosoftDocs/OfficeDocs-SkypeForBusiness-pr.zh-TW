---
title: 變更貴組織的 Skype 會議廣播設定
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
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
- SMB
- ms.lync.lac.BroadcastMeetings
description: 您可以啟用 Skype 會議廣播，並變更這些會議的設定與原則。
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753408"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="6a687-103">變更貴組織的 Skype 會議廣播設定</span><span class="sxs-lookup"><span data-stu-id="6a687-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a687-104">Microsoft 團隊系統管理中心已將商務用 Skype 系統管理中心 (舊版入口網站) 。</span><span class="sxs-lookup"><span data-stu-id="6a687-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="6a687-105">管理商務用 Skype 的所有設定現在都是在團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="6a687-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="6a687-106">您必須獲指派全域系統管理員或商務用 Skype 系統管理員的 [AZURE AD 管理員角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能管理團隊系統管理中心的商務用 skype 功能。</span><span class="sxs-lookup"><span data-stu-id="6a687-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="6a687-107">若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。</span><span class="sxs-lookup"><span data-stu-id="6a687-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="6a687-108">您可以啟用 Skype 會議廣播，並變更這些會議的設定與原則。</span><span class="sxs-lookup"><span data-stu-id="6a687-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="6a687-109">**啟用 Skype 會議廣播** 啟用 Skype 會議廣播。</span><span class="sxs-lookup"><span data-stu-id="6a687-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="6a687-110">啟用 Skype 會議廣播之後，您必須為 [Skype 會議廣播設定您的網路](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="6a687-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="6a687-111">如果您想要為企業外部的人員舉行網路研討會和其他廣播，請執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="6a687-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="6a687-112">**針對我的組織啟用 Skype 會議廣播預覽功能** 商務用 Skype 客戶計畫可讓您及早存取新的產品和功能。</span><span class="sxs-lookup"><span data-stu-id="6a687-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="6a687-113">這可讓您的組織快速查看即將推出的內容，以及在我們發佈產品組建至一般大眾之前提供意見反應的機會。</span><span class="sxs-lookup"><span data-stu-id="6a687-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="6a687-114">商務用 Skype preview</span><span class="sxs-lookup"><span data-stu-id="6a687-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="6a687-115">**允許召集人排程匿名會議** 這可讓召集人建立廣播事件，讓組織外的任何人都可以加入，而不需要登入。</span><span class="sxs-lookup"><span data-stu-id="6a687-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="6a687-116">**允許錄製廣播會議** 這可讓簡報者或召集人記錄您必須錄製的任何會議。</span><span class="sxs-lookup"><span data-stu-id="6a687-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="6a687-117">**出席者的支援人員支援 URL** 如果會議廣播出席者需要協助連線或加入廣播會議，請輸入要使用的連結。</span><span class="sxs-lookup"><span data-stu-id="6a687-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6a687-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="6a687-118">Related topics</span></span>

[<span data-ttu-id="6a687-119">為您的 Skype 會議廣播設定網路</span><span class="sxs-lookup"><span data-stu-id="6a687-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
