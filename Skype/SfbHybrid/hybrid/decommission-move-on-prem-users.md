---
title: 將使用者移至雲端
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在解除委任商務用 Skype 內部部署環境之前，移動使用者。
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656669"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="66deb-103">在解除委任內部部署環境之前，移動必要使用者</span><span class="sxs-lookup"><span data-stu-id="66deb-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="66deb-104">本文說明如何在解除委任您的內部部署商務用 Skype 環境之前，將所需使用者移至 Microsoft 雲端。</span><span class="sxs-lookup"><span data-stu-id="66deb-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="66deb-105">這是解除委任內部部署環境之下列步驟的步驟1：</span><span class="sxs-lookup"><span data-stu-id="66deb-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="66deb-106">**步驟1。將所有必要使用者從內部部署移至線上。**</span><span class="sxs-lookup"><span data-stu-id="66deb-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="66deb-107"> (本文) </span><span class="sxs-lookup"><span data-stu-id="66deb-107">(This article)</span></span>

- <span data-ttu-id="66deb-108">步驟 2.</span><span class="sxs-lookup"><span data-stu-id="66deb-108">Step 2.</span></span> <span data-ttu-id="66deb-109">[停用您的混合](cloud-consolidation-disabling-hybrid.md)式設定。</span><span class="sxs-lookup"><span data-stu-id="66deb-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="66deb-110">步驟 3.</span><span class="sxs-lookup"><span data-stu-id="66deb-110">Step 3.</span></span> <span data-ttu-id="66deb-111">[將混合應用程式端點從內部部署移至線上](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="66deb-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="66deb-112">步驟 4.</span><span class="sxs-lookup"><span data-stu-id="66deb-112">Step 4.</span></span> <span data-ttu-id="66deb-113">[移除您的內部部署商務用 Skype 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="66deb-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="66deb-114">將所有必要使用者從內部部署移至雲端</span><span class="sxs-lookup"><span data-stu-id="66deb-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="66deb-115">完成遷移之後，您將繼續使用的任何使用者，必須先從內部部署移至雲端。</span><span class="sxs-lookup"><span data-stu-id="66deb-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="66deb-116">您可以使用內部部署系統管理工具移動使用者。</span><span class="sxs-lookup"><span data-stu-id="66deb-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="66deb-117">如需詳細資訊，請參閱 [在內部部署與雲端之間移動使用者](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="66deb-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="66deb-118">雖然具有內部部署商務用 Skype 伺服器帳戶的使用者可以使用小組，但這些使用者卻沒有小組的完整功能。</span><span class="sxs-lookup"><span data-stu-id="66deb-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="66deb-119">無論是線上或內部部署) ，這些使用者都無法與其他任何使用商務用 Skype 的使用者進行交互操作或同盟 (。</span><span class="sxs-lookup"><span data-stu-id="66deb-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="66deb-120">這些使用者也不能在其團隊用戶端接收 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="66deb-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="66deb-121">因此，您必須將這些使用者移至線上。</span><span class="sxs-lookup"><span data-stu-id="66deb-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="66deb-122">此步驟也可確保在商務用 Skype Server 中建立的任何連絡人或會議都會遷移至小組。</span><span class="sxs-lookup"><span data-stu-id="66deb-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="66deb-123">若要檢查內部部署中是否還有任何其他使用者，請在 [商務用 Skype Server PowerShell] 視窗中執行下列 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="66deb-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="66deb-124">若傳回任何使用者，請複查輸出以判斷是否必須將任何帳戶移至雲端，並針對任何這類使用者執行[下列步驟。](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="66deb-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="66deb-125">針對不再需要的使用者帳戶，請執行下列商務用 Skype Server PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="66deb-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="66deb-126">執行 Disable-CsUser 會移除所有符合篩選準則之使用者的所有商務用 Skype 屬性。</span><span class="sxs-lookup"><span data-stu-id="66deb-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="66deb-127">繼續之前，請先確認這些帳戶已不再需要繼續進行。</span><span class="sxs-lookup"><span data-stu-id="66deb-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="66deb-128">您現在已準備好 [停用混合](cloud-consolidation-disabling-hybrid.md)式設定。</span><span class="sxs-lookup"><span data-stu-id="66deb-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="66deb-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="66deb-129">See also</span></span>

- [<span data-ttu-id="66deb-130">解除您的內部部署商務用 Skype 環境</span><span class="sxs-lookup"><span data-stu-id="66deb-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="66deb-131">停用混合式設定</span><span class="sxs-lookup"><span data-stu-id="66deb-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="66deb-132">將混合應用程式端點從內部部署移至線上</span><span class="sxs-lookup"><span data-stu-id="66deb-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="66deb-133">移除您的內部部署商務用 Skype 部署</span><span class="sxs-lookup"><span data-stu-id="66deb-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




