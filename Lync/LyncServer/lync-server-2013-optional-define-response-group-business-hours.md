---
title: 'Lync Server 2013: （選用） 定義回應群組營業時間'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b02ce8434d7912d81855725aa86a11fa377ce44
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a><span data-ttu-id="15820-102">（選用）Lync Server 2013 中的定義回應群組營業時間</span><span class="sxs-lookup"><span data-stu-id="15820-102">(Optional) Define Response Group business hours in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15820-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="15820-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<div>

## <a name="defining-business-hours"></a><span data-ttu-id="15820-104">定義上班時間</span><span class="sxs-lookup"><span data-stu-id="15820-104">Defining Business Hours</span></span>

<span data-ttu-id="15820-105">商務小時設定定義工作流程時可接聽來電，並指定要針對營業時間以外來電採取的動作。</span><span class="sxs-lookup"><span data-stu-id="15820-105">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="15820-106">回應群組管理員可以使用**新增 CsRgsHoursOfBusiness**指令程式來建立預先定義的排程，您可以使用任何數目的回應群組。</span><span class="sxs-lookup"><span data-stu-id="15820-106">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="15820-107">當您建立或修改工作流程時，您可以指定僅適用於該工作流程的自訂排程。</span><span class="sxs-lookup"><span data-stu-id="15820-107">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="15820-108">如需詳細資訊，請參閱<A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">建立或修改群組搜尋工作流程在 Lync Server 2013 中的</A>或<A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">建立或修改互動工作流程在 Lync Server 2013 中的</A>。</span><span class="sxs-lookup"><span data-stu-id="15820-108">For details, see <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or modify a hunt group workflow in Lync Server 2013</A> or <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">Create or modify an interactive workflow in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="15820-109">如果工作流程定義為受管理的工作流程，然後指派 CsResponseGroupManager 角色的任何使用者可以設定和修改其管理的工作流程的自訂營業時間。</span><span class="sxs-lookup"><span data-stu-id="15820-109">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="15820-110">使用 24 小時制表示法，下列指令程式中的參數 (例如，20:00 = 8:00 P.M.)。</span><span class="sxs-lookup"><span data-stu-id="15820-110">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span>



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="15820-111">若要建立預先定義的營業時間集合</span><span class="sxs-lookup"><span data-stu-id="15820-111">To create a predefined business hours collection</span></span>

1.  <span data-ttu-id="15820-112">以 RTCUniversalServerAdmins 群組成員身分或其中一個預先定義的系統管理角色支援回應群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="15820-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="15820-113">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="15820-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="15820-114">對於您要定義的每個唯一時間範圍，請執行：</span><span class="sxs-lookup"><span data-stu-id="15820-114">For each unique range of hours you want to define, run:</span></span>
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    <span data-ttu-id="15820-115">若要建立使用您所定義之範圍的上班時間集合，請執行：</span><span class="sxs-lookup"><span data-stu-id="15820-115">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    <span data-ttu-id="15820-p103">下列範例會將工作日的上班時間指定為上午 9:00 到下午 5:00，星期六則為上午 8:00 到上午 10:00 以及下午 2:00 到下午 6:00，星期日不上班：</span><span class="sxs-lookup"><span data-stu-id="15820-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15820-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="15820-123">See Also</span></span>


[<span data-ttu-id="15820-124">建立或修改群組搜尋工作流程在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15820-124">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="15820-125">建立或修改互動工作流程在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15820-125">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="15820-126">New-csrgstimerange</span><span class="sxs-lookup"><span data-stu-id="15820-126">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[<span data-ttu-id="15820-127">新 CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="15820-127">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

