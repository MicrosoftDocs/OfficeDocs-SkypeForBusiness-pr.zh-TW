---
title: 在會議中遮罩Microsoft Teams電話號碼
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在會議中隱藏Microsoft Teams電話號碼
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117711"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="bb34b-103">在會議中遮罩Microsoft Teams電話號碼</span><span class="sxs-lookup"><span data-stu-id="bb34b-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="bb34b-104">為了增加隱私權，使用音訊會議撥入Teams會議的參與者電話號碼會完整顯示給內部參與者。</span><span class="sxs-lookup"><span data-stu-id="bb34b-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="bb34b-105">這些號碼會遮罩組織外部的參與者。</span><span class="sxs-lookup"><span data-stu-id="bb34b-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="bb34b-106">此設定是所有組織的預設值。</span><span class="sxs-lookup"><span data-stu-id="bb34b-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="bb34b-107">遮罩數位會顯示如下圖像所示：</span><span class="sxs-lookup"><span data-stu-id="bb34b-107">The masked number is displayed as shown in the following image:</span></span>

![遮罩電話號碼的範例](media/hiddenPhoneNum.png)

<span data-ttu-id="bb34b-109">針對特定的產業使用案例，系統管理員可以選擇音訊會議參與者的電話號碼在租使用者中組織會議時顯示方式。</span><span class="sxs-lookup"><span data-stu-id="bb34b-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="bb34b-110">系統管理員可以從三個選項中選擇：</span><span class="sxs-lookup"><span data-stu-id="bb34b-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="bb34b-111">電話外部參與者遮罩數位。</span><span class="sxs-lookup"><span data-stu-id="bb34b-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="bb34b-112">屬於會議召集人租使用者的參與者仍然會看到完整的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bb34b-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="bb34b-113">電話除了召集人之外，會議中的每個人都會遮罩數位。</span><span class="sxs-lookup"><span data-stu-id="bb34b-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="bb34b-114">電話數位會取消遮罩，讓會議中的每個人看到這些數位。</span><span class="sxs-lookup"><span data-stu-id="bb34b-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="bb34b-115">此設定會適用于會議中公開電話號碼的所有表面。</span><span class="sxs-lookup"><span data-stu-id="bb34b-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="bb34b-116">使用 Microsoft PowerShell 設定電話號碼遮罩</span><span class="sxs-lookup"><span data-stu-id="bb34b-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="bb34b-117">若要變更公用交換電話網絡 (PSTN) 遮罩設定，請設定 **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) Cmdlet 的參數至其中一個可用的選項。</span><span class="sxs-lookup"><span data-stu-id="bb34b-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="bb34b-118">若要只遮罩外部參與者的電話號碼，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bb34b-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="bb34b-119">若要遮罩會議參與者中除了 (之外) 的電話號碼，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bb34b-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="bb34b-120">若要停用電話號碼遮罩，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bb34b-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```