---
title: 在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 摘要：瞭解如何在商務用 Skype Server 中設定語音原則、PSTN 使用方式記錄和語音路由。
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830443"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>在商務用 Skype 中設定語音原則、PSTN 使用方式記錄和語音路由
 
**摘要：** 瞭解如何在商務用 Skype Server 中設定語音原則、PSTN 使用方式記錄和語音路由。
  
語音原則、PSTN 使用方式記錄和語音路由密切相關。您可以選取一組撥號功能，接著指派一組 PSTN 使用方式記錄給原則，以便指定獲指派語音原則的使用者或群組可獲得哪些權限授權，如此就能設定語音原則。語音路由也會被指派 PSTN 使用方式記錄，這些記錄會用來比對路由與獲授權使用這些路由的使用者。也就是說，使用者可以撥打的電話，只限於使用他們有相符 PSTN 使用方式記錄之路由的電話。
  
新 Enterprise Voice 部署的建議工作流程是：從設定包含適當 PSTN 使用方式記錄的語音原則開始，接著將適當路由關聯給每個 PSTN 使用方式記錄。 
  
> [!NOTE]
> 您也可以建立具有  *使用者*  範圍的語音原則，並將其指派給個別使用者或群組。
  
如需執行每項工作的詳細步驟，請參閱本節程序。
  
## <a name="in-this-section"></a>本節內容

- [在商務用 Skype 中建立或修改語音原則及設定 PSTN 使用方式記錄](voice-policy-and-pstn-usage-records.md)
    
- [在商務用 Skype 中設定語音信箱轉義](configure-voice-mail-escape.md)
    
- [在商務用 Skype 中查看 PSTN 使用方式記錄](view-pstn-usage-records.md)
    
- [在商務用 Skype 中建立或修改語音路由](create-or-modify-a-voice-route.md)
    
- [在商務用 Skype 中匯出或匯入語音路由設定檔](voice-route-configuration-import-export.md)
    
- [在商務用 Skype 中將擱置的變更發佈至語音路由設定](voice-route-config-changes.md)
    

