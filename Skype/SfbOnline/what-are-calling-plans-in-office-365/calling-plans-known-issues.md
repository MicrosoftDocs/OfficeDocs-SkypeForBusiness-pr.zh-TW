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
description: '瞭解 Office 365 （PSTN 通話）通話方案的已知問題，以及您可以採取的措施。 '
ms.openlocfilehash: 3441969133c8f67b63b620aff25545b89085858f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692308"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="fa2ec-103">通話方案已知問題</span><span class="sxs-lookup"><span data-stu-id="fa2ec-103">Calling Plans known issues</span></span>

<span data-ttu-id="fa2ec-104">Office 365 中的通話方案是在商務用 Skype Online 中找到的新功能。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="fa2ec-105">下列是目前正在追蹤及主動調查的問題。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="fa2ec-106">當您在 Office 365 和商務用 Skype Online 中的未來組建更新此功能時，可能會解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="fa2ec-107">通話方案已知問題</span><span class="sxs-lookup"><span data-stu-id="fa2ec-107">Calling Plans known issues</span></span>

|<span data-ttu-id="fa2ec-108">**已知問題**</span><span class="sxs-lookup"><span data-stu-id="fa2ec-108">**Known issue**</span></span>|<span data-ttu-id="fa2ec-109">**批註**</span><span class="sxs-lookup"><span data-stu-id="fa2ec-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa2ec-110">從 Tech Preview 授權轉換到通話方案的生產授權時，不會自動更新授權。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="fa2ec-111">您必須先購買新的授權，才能將其指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="fa2ec-112">移除使用者的促銷（技術預覽）授權，然後**立即**將新的**國內通話方案**及/或**國內和國際通話方案**授權指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="fa2ec-113">如果您要移除並新增多個使用者的授權，您必須從使用 Windows PowerShell 的所有使用者移除授權，然後**立即**使用 Windows powershell 指派所有使用者的授權，這相當重要。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="fa2ec-114">如此一來，就能確保處理大量使用者授權指派時，服務不會中斷。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="fa2ec-115">如需 PowerShell 腳本範例，請參閱[指派商務用 Skype 和 Microsoft 團隊授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="fa2ec-116">**注意：** 如果您是針對混合式使用者使用內部部署 PSTN 連線，則*只*需指派**電話系統**授權即可。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="fa2ec-117">您也**不**應該指派語音通話方案。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="fa2ec-118">不過，如果您在 Office 365 中針對 Office 365 中的使用者啟用通話方案，您仍需為這些使用者指派**國內通話方案**或**國內與國際通話方案**授權。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="fa2ec-119">請參閱[指派商務用 Skype 和 Microsoft 團隊授權](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="fa2ec-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fa2ec-120">如果您需要取得更多的電話號碼，請[聯絡商務產品支援-系統管理協助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="fa2ec-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="fa2ec-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa2ec-121">Related topics</span></span>
[<span data-ttu-id="fa2ec-122">移轉電話號碼的常見問題</span><span class="sxs-lookup"><span data-stu-id="fa2ec-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="fa2ec-123">通話方案所用的不同類型的電話號碼</span><span class="sxs-lookup"><span data-stu-id="fa2ec-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="fa2ec-124">管理貴組織的電話號碼</span><span class="sxs-lookup"><span data-stu-id="fa2ec-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="fa2ec-125">緊急通話條款及條件</span><span class="sxs-lookup"><span data-stu-id="fa2ec-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="fa2ec-126">[商務用 Skype Online：緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="fa2ec-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 