---
title: 'Lync Server 2013: （選用） 定義回應群組假日集'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0680d59cb591e193f90bec16e19079dde8600b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="2df15-102">（選用）Lync Server 2013 中的定義回應群組假日集</span><span class="sxs-lookup"><span data-stu-id="2df15-102">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2df15-103">_**上次修改主題：** 2014年-02-07_</span><span class="sxs-lookup"><span data-stu-id="2df15-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="2df15-p101">假日設定會定義回應群組關閉的不營業日期，並且指定在這些日子採取的動作。假日集為套用至回應群組的假日集合。</span><span class="sxs-lookup"><span data-stu-id="2df15-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2df15-106">如果已將工作流程設定為受管理的工作流程，則任何已指派 CsResponseGroupManager 角色的使用者都可以設定和修改其所管理之工作流程的假日。</span><span class="sxs-lookup"><span data-stu-id="2df15-106">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="2df15-107">建立假日集</span><span class="sxs-lookup"><span data-stu-id="2df15-107">To create a holiday set</span></span>

1.  <span data-ttu-id="2df15-108">以 RTCUniversalServerAdmins 群組成員身分或其中一個預先定義的系統管理角色支援回應群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="2df15-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="2df15-109">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="2df15-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2df15-110">對於您要定義的每個假日，請執行：</span><span class="sxs-lookup"><span data-stu-id="2df15-110">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="2df15-111">若要建立包含您所定義之假日的假日集，請執行：</span><span class="sxs-lookup"><span data-stu-id="2df15-111">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="2df15-112">下列範例顯示包含兩個假日的假日集：</span><span class="sxs-lookup"><span data-stu-id="2df15-112">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2df15-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2df15-113">See Also</span></span>


[<span data-ttu-id="2df15-114">建立或修改群組搜尋工作流程在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2df15-114">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="2df15-115">建立或修改互動工作流程在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2df15-115">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="2df15-116">New-csrgsholiday</span><span class="sxs-lookup"><span data-stu-id="2df15-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="2df15-117">New-csrgsholidayset</span><span class="sxs-lookup"><span data-stu-id="2df15-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

