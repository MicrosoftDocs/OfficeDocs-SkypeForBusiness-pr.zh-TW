---
title: 變更貴Skype的會議廣播設定
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
description: 您可以啟用Skype廣播功能，並變更這些會議的設定和策略。
ms.openlocfilehash: fae53601c858bf67db57352e18dbc9799243f996
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238645"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="5b605-103">變更貴Skype的會議廣播設定</span><span class="sxs-lookup"><span data-stu-id="5b605-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="5b605-104">系統Microsoft Teams系統管理中心已取代 商務用 Skype 系統管理中心 (舊版) 。</span><span class="sxs-lookup"><span data-stu-id="5b605-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="5b605-105">系統管理中心商務用 Skype所有管理Teams設定。</span><span class="sxs-lookup"><span data-stu-id="5b605-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="5b605-106">您必須指派全域系統管理員或系統管理員的[Azure AD](/azure/active-directory/roles/permissions-reference)系統管理員角色商務用 Skype，才能商務用 Skype系統管理中心Teams功能。</span><span class="sxs-lookup"><span data-stu-id="5b605-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="5b605-107">若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)。</span><span class="sxs-lookup"><span data-stu-id="5b605-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="5b605-108">您可以啟用Skype廣播功能，並變更這些會議的設定和策略。</span><span class="sxs-lookup"><span data-stu-id="5b605-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="5b605-109">**啟用Skype廣播** 啟用Skype廣播。</span><span class="sxs-lookup"><span data-stu-id="5b605-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="5b605-110">啟用會議廣播Skype之後，您必須設定[您的網路以Skype廣播](set-up-your-network-for-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="5b605-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="5b605-111">如果您想要為公司外部人員舉辦網路研討會和其他廣播，請執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="5b605-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="5b605-112">**為Skype啟用會議廣播預覽功能** 客戶商務用 Skype計畫可為您提供新產品與功能的提早存取權。</span><span class="sxs-lookup"><span data-stu-id="5b605-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="5b605-113">這樣一來，貴組織就會快速瞭解即將推出哪些功能，以及測試您環境中新功能的機會，並給予意見，然後再將產品建立發佈給一般大眾。</span><span class="sxs-lookup"><span data-stu-id="5b605-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="5b605-114">商務用 Skype預覽</span><span class="sxs-lookup"><span data-stu-id="5b605-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="5b605-115">**允許召集人排程匿名會議** 這可讓召集人建立廣播活動，讓組織外部的任何人無需登錄即可加入。</span><span class="sxs-lookup"><span data-stu-id="5b605-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="5b605-116">**允許錄製廣播會議** 這可讓簡報者或召集人錄製任何會議。</span><span class="sxs-lookup"><span data-stu-id="5b605-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="5b605-117">**出席者的支援 URL** 輸入會議廣播出席者的連結，以在需要連接或出席廣播會議時需要協助時使用。</span><span class="sxs-lookup"><span data-stu-id="5b605-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5b605-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="5b605-118">Related topics</span></span>

[<span data-ttu-id="5b605-119">為您的 Skype 會議廣播設定網路</span><span class="sxs-lookup"><span data-stu-id="5b605-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
