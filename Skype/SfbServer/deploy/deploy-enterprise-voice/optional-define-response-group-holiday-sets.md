---
title: 可選在商務用 Skype 中定義回應群組假日集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 在商務用 Skype Server Enterprise Voice 中建立或修改回應群組假日集。
ms.openlocfilehash: cd277412a9cef2c474b8ba60459e216482f2d872
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193640"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="e1b06-103">可選在商務用 Skype 中定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="e1b06-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="e1b06-104">在商務用 Skype Server Enterprise Voice 中建立或修改回應群組假日集。</span><span class="sxs-lookup"><span data-stu-id="e1b06-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="e1b06-105">[假日設定] 定義回應群組在商務中關閉的天數, 並指定要在這些日期採取的動作。</span><span class="sxs-lookup"><span data-stu-id="e1b06-105">Holiday settings define the days that a response group is closed for business and specify the action to take on those days.</span></span> <span data-ttu-id="e1b06-106">假日集是套用至回應群組的假日集合。</span><span class="sxs-lookup"><span data-stu-id="e1b06-106">A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e1b06-107">如果工作流程定義為受管理的工作流程, 則會指派任何使用者 CsResponseGroupManager 角色, 即可設定及修改他們所管理之工作流程的假日。</span><span class="sxs-lookup"><span data-stu-id="e1b06-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="e1b06-108">建立假日集</span><span class="sxs-lookup"><span data-stu-id="e1b06-108">To create a holiday set</span></span>

1. <span data-ttu-id="e1b06-109">以 RTCUniversalServerAdmins 群組成員的身分登入, 或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="e1b06-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="e1b06-110">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="e1b06-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e1b06-111">針對您想要定義的每一個假日, 請執行:</span><span class="sxs-lookup"><span data-stu-id="e1b06-111">For each holiday you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="e1b06-112">若要建立包含您定義之假日的假日集, 請執行:</span><span class="sxs-lookup"><span data-stu-id="e1b06-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="e1b06-113">下列範例顯示包含兩個假日的假日集:</span><span class="sxs-lookup"><span data-stu-id="e1b06-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="e1b06-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e1b06-114">See also</span></span>

[<span data-ttu-id="e1b06-115">在商務用 Skype 中設計及建立回應群組工作流程</span><span class="sxs-lookup"><span data-stu-id="e1b06-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="e1b06-116">新-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="e1b06-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="e1b06-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="e1b06-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
