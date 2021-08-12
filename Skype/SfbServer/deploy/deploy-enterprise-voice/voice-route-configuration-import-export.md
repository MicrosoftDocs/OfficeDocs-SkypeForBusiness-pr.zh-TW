---
title: 在商務用 Skype 中匯出或匯入語音路由設定檔
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
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 摘要：瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中匯出或匯入語音路由設定檔。
ms.openlocfilehash: bef3e1caf80ecc2dc065949dcec684ad6e342902cfabf0e9daebab237d09c7ca
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320815"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>在商務用 Skype 中匯出或匯入語音路由設定檔
 
**摘要：** 瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中匯出或匯入語音路由設定檔。
  
如果您想要儲存語音路由設定，但未發佈它，請遵循下列步驟，儲存並取得您的語音路由設定快照。 
  
當您匯入語音路由設定檔 (。 vcfg) ，但目前已對伺服器上的語音路由設定進行變更，商務用 Skype Server 控制台中的 [**語音** 路由] 群組中的頁面會指出有未認可的變更可供語音路由使用。 這些未認可的變更會使兩個設定出現差異且需要重新調整。
  
如果您已對群組內任何頁面上的設定進行任何未認可的變更，則所做的變更會儲存在匯出的語音設定檔中 (。 vcfg) 。 這可讓您在發佈變更之前，在多個會話期間進行語音路由設定變更。 
  
### <a name="to-export-a-voice-routing-configuration"></a>若要匯出語音路由設定

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。
    
2. 開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 **[語音路由]**。
    
4. 在 **[執行]** 功能表上，按一下 **[匯出設定]**。
    
5. 指定位置和檔案名稱，然後按一下 **[儲存]**。
    
### <a name="to-import-a-voice-routing-configuration"></a>若要匯入語音路由設定

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。
    
2. 開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 **[語音路由]**。
    
4. 在 **[執行]** 功能表上，按一下 **[匯入設定]**。
    
5. 尋找您要匯入的組態檔，然後按一下 **[開啟]**。
    
6. 依序按一下 **[認可]** 和 **[全部認可]**。
    
    > [!NOTE]
    > 每當您匯入語音設定檔時，您必須執行 **[全部認可]** 命令來發佈設定變更。 如需詳細資訊，請參閱操作檔中的[商務用 Skype 發佈擱置變更至語音路由](voice-route-config-changes.md)設定。
  

