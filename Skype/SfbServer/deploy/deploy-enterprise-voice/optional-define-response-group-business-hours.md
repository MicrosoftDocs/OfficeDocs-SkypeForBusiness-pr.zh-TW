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
description: 在商務用 Skype Server 企業語音中建立或修改回應群組的上班時間。
ms.openlocfilehash: 37195633064ab04f3d24f56b09760fb44b2ddd473da316898d1106cc13ef4bc3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338701"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a> (選用) 在商務用 Skype 中定義回應群組上班時間 
 
在商務用 Skype Server 企業語音中建立或修改回應群組的上班時間。
  
## <a name="defining-business-hours"></a>定義上班時間

上班時間設定定義工作流程何時可以接聽來電，並指定要對上班時間以外的來電採取的動作。 回應群組管理員可以使用 **CsRgsHoursOfBusiness** 指令程式來建立您可以用於任何回應群組數目的預先定義排程。
  
> [!TIP]
> 當您建立或修改工作流程時，您可以指定僅適用于該工作流程的自訂排程。 如需詳細資訊，請參閱[在商務用 Skype 中設計及建立回應群組工作流程](designing-and-creating-response-group-workflows.md)。 
  
> [!NOTE]
> 如果工作流程定義為受管理的工作流程，則獲指派 CsResponseGroupManager 角色的任何使用者都可以為其管理的工作流程設定及修改自訂的上班時間。 
  
> [!IMPORTANT]
> 下列 Cmdlet 中的參數使用24小時標記法 (例如，20： 00 = 8： 00 P.M. ) 。 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>建立預先定義的上班時間集合

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 對於您要定義的每個唯一時間範圍，請執行：
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    若要建立使用您所定義之範圍的上班時間集合，請執行：
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    下列範例會將工作日的上班時間指定為上午 9:00 到下午 5:00，星期六則為上午 8:00 到上午 10:00 以及下午 2:00 到下午 6:00，星期日不上班：
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>另請參閱

[New-CsRgsTimeRange](/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[新 CsRgsHoursOfBusiness](/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)