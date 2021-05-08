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
description: 瞭解 PSTN 通話的通話方案已知問題，以及您可以採取哪些處理方式。
ms.openlocfilehash: 9c660ee3b173f104e26816460db45c5bcf400837
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238019"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="fa842-103">通話方案已知問題</span><span class="sxs-lookup"><span data-stu-id="fa842-103">Calling Plans known issues</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="fa842-104">通話方案是線上通話的商務用 Skype功能。</span><span class="sxs-lookup"><span data-stu-id="fa842-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="fa842-105">以下是目前正在追蹤並積極調查的目前問題。</span><span class="sxs-lookup"><span data-stu-id="fa842-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="fa842-106">當功能在未來建立中更新時，這些衝突可能會解決。</span><span class="sxs-lookup"><span data-stu-id="fa842-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="fa842-107">通話方案已知問題</span><span class="sxs-lookup"><span data-stu-id="fa842-107">Calling Plans known issues</span></span>

|<span data-ttu-id="fa842-108">**已知問題**</span><span class="sxs-lookup"><span data-stu-id="fa842-108">**Known issue**</span></span>|<span data-ttu-id="fa842-109">**註解**</span><span class="sxs-lookup"><span data-stu-id="fa842-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa842-110">從 Tech Preview 授權轉換為通話方案生產授權不會自動更新授權。</span><span class="sxs-lookup"><span data-stu-id="fa842-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="fa842-111">首先購買您的新授權，以便準備好指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="fa842-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="fa842-112">從使用者 (技術預覽版) 促銷，然後立即指派新的國內通話方案及/或國內及國際通話方案授權給使用者。 </span><span class="sxs-lookup"><span data-stu-id="fa842-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="fa842-113">如果您要移除並新增多個使用者授權，從使用 Windows PowerShell 的所有使用者移除授權，然後立即指派授權給所有同時使用 Windows PowerShell 的使用者，這Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="fa842-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="fa842-114">這麼做可確保處理大量使用者授權指派時，服務不會中斷。</span><span class="sxs-lookup"><span data-stu-id="fa842-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="fa842-115">有關 PowerShell 腳本範例，請參閱指派[商務用 Skype及Microsoft Teams授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="fa842-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="fa842-116">**注意：** 如果您為混合式使用者使用內部部署 PSTN 連接，則只需要指派 **電話系統授權。**</span><span class="sxs-lookup"><span data-stu-id="fa842-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="fa842-117">您 **也不應該** 指派語音通話方案。</span><span class="sxs-lookup"><span data-stu-id="fa842-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="fa842-118">不過，如果您在 Microsoft 365 或 Office 365 中為 Microsoft 365 或 Office 365 中的使用者啟用通話方案，您仍然需要為這些使用者指派國內通話方案或國內和國際通話方案授權。 </span><span class="sxs-lookup"><span data-stu-id="fa842-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="fa842-119">請參閱[指派商務用 Skype和Microsoft Teams授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="fa842-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa842-120">如果您需要取得更多電話號碼，請聯絡商務產品支援人員 [- 系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="fa842-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="fa842-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa842-121">Related topics</span></span>
[<span data-ttu-id="fa842-122">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="fa842-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="fa842-123">用於通話方案的各種電話號碼</span><span class="sxs-lookup"><span data-stu-id="fa842-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="fa842-124">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="fa842-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="fa842-125">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="fa842-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="fa842-126">[商務用 Skype線上：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fa842-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
