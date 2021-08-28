---
title: 在商務用 Skype 中發佈語音路由設定的擱置變更
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 摘要：瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中查看、發佈或取消語音路由設定變更。
ms.openlocfilehash: 2873520be0b5f7709fb493912be18afa807884c2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583187"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>在商務用 Skype 中發佈語音路由設定的擱置變更
 
**摘要：** 瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中查看、發佈或取消語音路由設定變更。
  
變更 [ **語音路由** ] 群組中的任何設定設定後，請執行此程式以複查、發佈或取消暫止的變更。
  
> [!IMPORTANT]
> 請確定一次只能有一個使用者修改語音路由設定的設定。 
  
> [!NOTE]
> 所有擱置的變更都必須同時發佈，只要執行 [ **全部認可** ] 命令即可。 您無法選擇性發行暫止的變更。 在您發佈暫止的變更之前，請執行 [ **檢查未** 認可的變更] 命令，並取消您不想發佈的任何設定變更。
  
> [!NOTE]
> 如果您在提交暫止的變更之前，移離 **語音路由** 群組中的頁面，所有擱置的變更將會遺失。 不過，您可以將目前的設定 (包括任何擱置的變更) 至語音設定檔，然後匯入併發行更新的設定。 如需詳細資訊，請參閱[Export or import a voice route configuration file in 商務用 Skype](voice-route-configuration-import-export.md)。 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>若要檢查、發佈或取消語音路由設定變更

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。
    
2. 開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 **[語音路由]**。
    
4. 在 [ **語音路由** ] 群組的每一頁上進行設定的設定變更。
    
5. 若要在未發佈的情況下複查擱置中的變更，請選取 [從 **認可**] 功能表 **查看未** 認可的變更
    
6. 如果您想要取消任何擱置的變更，請執行下列其中一項操作：
    
   - 從 [**認可**] 功能表中，選取 [**取消所有未** 認可的變更]。
    
   - 流覽至 [ **語音路由** ] 頁面上的 [語音路由] 頁面，其中含有您想要取消的待處理變更，選取具有暫止變更的專案，按一下 [ **認可**]，然後按一下 [ **取消選取的變更**]。
    
7. 在您檢查所有擱置的變更並取消任何不想發佈的變更之後，請按一下 [ **認可**]，然後按一下 [ **全部認可**]。
    
8. 在 [**未** 認可的語音設定設定] 對話方塊中，顯示所有擱置變更的清單，按一下 **[確定]**。 
    
    當商務用 Skype Server 控制台認可變更時，就會出現 [**成功發行的語音路由** 設定] 訊息。
    

