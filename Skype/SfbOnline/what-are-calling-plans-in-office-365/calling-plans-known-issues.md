---
title: 通話方案已知問題
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
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
- Calling Plans
description: 瞭解 PSTN 通話的通話方案的已知問題，以及您可以採取的措施。
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220733"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="e7907-103">通話方案已知問題</span><span class="sxs-lookup"><span data-stu-id="e7907-103">Calling Plans known issues</span></span>

<span data-ttu-id="e7907-104">通話方案是在商務用 Skype Online 中找到的新功能。</span><span class="sxs-lookup"><span data-stu-id="e7907-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="e7907-105">下列是目前正在追蹤及主動調查的問題。</span><span class="sxs-lookup"><span data-stu-id="e7907-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="e7907-106">在未來組建中更新此功能時，可能會解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="e7907-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="e7907-107">通話方案已知問題</span><span class="sxs-lookup"><span data-stu-id="e7907-107">Calling Plans known issues</span></span>

|<span data-ttu-id="e7907-108">**已知問題**</span><span class="sxs-lookup"><span data-stu-id="e7907-108">**Known issue**</span></span>|<span data-ttu-id="e7907-109">**註解**</span><span class="sxs-lookup"><span data-stu-id="e7907-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e7907-110">從 Tech Preview 授權轉換到通話方案的生產授權時，不會自動更新授權。</span><span class="sxs-lookup"><span data-stu-id="e7907-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="e7907-111">您必須先購買新的授權，才能將其指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="e7907-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="e7907-112">移除使用者的促銷（技術預覽）授權，然後**立即**將新的**國內通話方案**及/或**國內和國際通話方案**授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="e7907-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="e7907-113">如果您要移除並新增多個使用者的授權，您必須從使用 Windows PowerShell 的所有使用者移除授權，然後**立即**使用 Windows powershell 指派所有使用者的授權，這相當重要。</span><span class="sxs-lookup"><span data-stu-id="e7907-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="e7907-114">如此一來，就能確保處理大量使用者授權指派時，服務不會中斷。</span><span class="sxs-lookup"><span data-stu-id="e7907-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="e7907-115">如需 PowerShell 腳本範例，請參閱[指派商務用 Skype 和 Microsoft 團隊授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="e7907-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="e7907-116">**注意：** 如果您是針對混合式使用者使用內部部署 PSTN 連線，則*只*需指派**電話系統**授權即可。</span><span class="sxs-lookup"><span data-stu-id="e7907-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="e7907-117">您也**不**應該指派語音通話方案。</span><span class="sxs-lookup"><span data-stu-id="e7907-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="e7907-118">不過，如果您在 Microsoft 365 或 Office 365 中針對 Microsoft 365 或 Office 365 中的使用者啟用通話方案，您仍需為這些使用者指派**國內通話方案**或**國內與國際通話方案**授權。</span><span class="sxs-lookup"><span data-stu-id="e7907-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="e7907-119">請參閱[指派商務用 Skype 和 Microsoft 團隊授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="e7907-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e7907-120">如果您需要取得更多的電話號碼，請[聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="e7907-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="e7907-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7907-121">Related topics</span></span>
[<span data-ttu-id="e7907-122">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="e7907-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="e7907-123">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="e7907-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="e7907-124">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="e7907-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="e7907-125">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="e7907-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="e7907-126">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="e7907-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
