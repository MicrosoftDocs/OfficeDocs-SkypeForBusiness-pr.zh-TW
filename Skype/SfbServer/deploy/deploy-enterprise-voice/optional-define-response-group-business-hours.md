---
title: 可選在商務用 Skype 中定義回應群組上班時間
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 在商務用 Skype Server Enterprise Voice 中建立或修改回應群組的上班時間。
ms.openlocfilehash: e492715e32b60858176f0034ef4978d0f333dc09
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240383"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>可選在商務用 Skype 中定義回應群組上班時間 
 
在商務用 Skype Server Enterprise Voice 中建立或修改回應群組的上班時間。
  
## <a name="defining-business-hours"></a>定義上班時間

商務時數設定會定義工作流程何時可接聽電話, 以及指定要在上班時間以外的通話時採取的動作。 回應群組系統管理員可以使用**新的 CsRgsHoursOfBusiness** Cmdlet 來建立預先定義的排程, 您可以將這些排程用於任何數量的回應群組。
  
> [!TIP]
> 當您建立或修改工作流程時, 您可以指定只適用于該工作流程的自訂排程。 如需詳細資訊, 請參閱[在商務用 Skype 中設計及建立回應群組工作流程](designing-and-creating-response-group-workflows.md)。 
  
> [!NOTE]
> 如果工作流程定義為受管理的工作流程, 則獲指派 CsResponseGroupManager 角色的任何使用者都可以設定及修改他們所管理之工作流程的自訂上班時間。 
  
> [!IMPORTANT]
> 在下列 Cmdlet 中使用24小時制標記法 (例如, 20:00 = 8:00 = ∞)。 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>若要建立預先定義的上班時間集合

1. 以 RTCUniversalServerAdmins 群組成員的身分登入, 或以支援回應群組的預先定義之系統管理角色的成員的身分登入。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. 針對您要定義的每個時間範圍, 請執行:
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    若要建立使用您定義之範圍的上班時間集合, 請執行:
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    下列範例指定 9:00 A.M. 的上班時間。 到下午5:00 工作日、8:00 A.M。 至 10:00 A.M。 再次從 2:00 P.M. 開始。 到下午6:00 針對星期六, 且無工作日的上班時間:
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>另請參閱

[新-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[新-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
