---
title: " (選用) 在商務用 Skype 中定義回應群組上班時間"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 在商務用 Skype Server Enterprise Voice 中建立或修改回應群組的上班時間。
ms.openlocfilehash: d4a8101749e7fde06fc4c3d88ab343eb6e4d0f1d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103669"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="4480b-103"> (選用) 在商務用 Skype 中定義回應群組上班時間</span><span class="sxs-lookup"><span data-stu-id="4480b-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="4480b-104">在商務用 Skype Server Enterprise Voice 中建立或修改回應群組的上班時間。</span><span class="sxs-lookup"><span data-stu-id="4480b-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="4480b-105">定義上班時間</span><span class="sxs-lookup"><span data-stu-id="4480b-105">Defining Business Hours</span></span>

<span data-ttu-id="4480b-106">上班時間設定定義工作流程何時可以接聽來電，並指定要對上班時間以外的來電採取的動作。</span><span class="sxs-lookup"><span data-stu-id="4480b-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="4480b-107">回應群組管理員可以使用 **CsRgsHoursOfBusiness** 指令程式來建立您可以用於任何回應群組數目的預先定義排程。</span><span class="sxs-lookup"><span data-stu-id="4480b-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="4480b-108">當您建立或修改工作流程時，您可以指定僅適用于該工作流程的自訂排程。</span><span class="sxs-lookup"><span data-stu-id="4480b-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="4480b-109">如需詳細資訊，請參閱 [在商務用 Skype 中設計及建立回應群組工作流程](designing-and-creating-response-group-workflows.md)。</span><span class="sxs-lookup"><span data-stu-id="4480b-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4480b-110">如果工作流程定義為受管理的工作流程，則獲指派 CsResponseGroupManager 角色的任何使用者都可以為其管理的工作流程設定及修改自訂的上班時間。</span><span class="sxs-lookup"><span data-stu-id="4480b-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4480b-111">下列 Cmdlet 中的參數使用24小時標記法 (例如，20： 00 = 8： 00 P.M. ) 。</span><span class="sxs-lookup"><span data-stu-id="4480b-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="4480b-112">建立預先定義的上班時間集合</span><span class="sxs-lookup"><span data-stu-id="4480b-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="4480b-113">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="4480b-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="4480b-114">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="4480b-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="4480b-115">對於您要定義的每個唯一時間範圍，請執行：</span><span class="sxs-lookup"><span data-stu-id="4480b-115">For each unique range of hours you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="4480b-116">若要建立使用您所定義之範圍的上班時間集合，請執行：</span><span class="sxs-lookup"><span data-stu-id="4480b-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="4480b-p103">下列範例會將工作日的上班時間指定為上午 9:00 到下午 5:00，星期六則為上午 8:00 到上午 10:00 以及下午 2:00 到下午 6:00，星期日不上班：</span><span class="sxs-lookup"><span data-stu-id="4480b-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="4480b-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4480b-124">See also</span></span>

[<span data-ttu-id="4480b-125">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="4480b-125">New-CsRgsTimeRange</span></span>](/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="4480b-126">新 CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="4480b-126">New-CsRgsHoursOfBusiness</span></span>](/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)