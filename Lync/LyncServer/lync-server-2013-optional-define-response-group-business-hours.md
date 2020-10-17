---
title: Lync Server 2013： (選用) 定義回應群組上班時間
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
ms.openlocfilehash: 891dd05caf5e2ec3411da73c1151ae61c2d0630c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524460"
---
# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a> (選用) 在 Lync Server 2013 中定義回應群組上班時間

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

<div>

## <a name="defining-business-hours"></a>定義上班時間

上班時間設定定義工作流程何時可以接聽來電，並指定要對上班時間以外的來電採取的動作。 回應群組管理員可以使用 **CsRgsHoursOfBusiness** 指令程式來建立您可以用於任何回應群組數目的預先定義排程。

<div>


> [!TIP]  
> 當您建立或修改工作流程時，您可以指定僅適用于該工作流程的自訂排程。 如需詳細資訊，請參閱 <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">建立或修改 Lync server 2013 中的群組搜尋工作流程</A> 或 <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">在 lync Server 2013 中建立或修改互動式工作流程</A>。



</div>

<div>


> [!NOTE]  
> 如果工作流程定義為受管理的工作流程，則獲指派 CsResponseGroupManager 角色的任何使用者都可以為其管理的工作流程設定及修改自訂的上班時間。



</div>

<div>


> [!IMPORTANT]  
> 下列 Cmdlet 中的參數使用24小時標記法 (例如，20： 00 = 8： 00 P.M. ) 。



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a>建立預先定義的上班時間集合

1.  以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  對於您要定義的每個唯一時間範圍，請執行：
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    若要建立使用您所定義之範圍的上班時間集合，請執行：
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    下列範例會將工作日的上班時間指定為上午 9:00 到下午 5:00，星期六則為上午 8:00 到上午 10:00 以及下午 2:00 到下午 6:00，星期日不上班：
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改群組搜尋工作流程](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[在 Lync Server 2013 中建立或修改互動式工作流程](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[新 CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

