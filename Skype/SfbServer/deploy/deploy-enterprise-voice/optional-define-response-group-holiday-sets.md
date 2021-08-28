---
title: " (選用) 定義回應群組假日集商務用 Skype"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 在商務用 Skype Server 企業語音中建立或修改回應群組假日集。
ms.openlocfilehash: 1c97e791285310e673dc647f76cb8cd733ffd52a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579957"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a> (選用) 定義回應群組假日集商務用 Skype
 
在商務用 Skype Server 企業語音中建立或修改回應群組假日集。
  
假日設定會定義回應群組關閉的不營業日期，並且指定在這些日子採取的動作。假日集為套用至回應群組的假日集合。
  
> [!NOTE]
> 如果已將工作流程設定為受管理的工作流程，則任何已指派 CsResponseGroupManager 角色的使用者都可以設定和修改其所管理之工作流程的假日。 
  
### <a name="to-create-a-holiday-set"></a>建立假日集

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 對於您要定義的每個假日，請執行：
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    若要建立包含您所定義之假日的假日集，請執行：
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    下列範例顯示包含兩個假日的假日集：
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>另請參閱

[在商務用 Skype 中設計及建立回應群組工作流程](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)