---
title: 在商務用 Skype 中匯出或匯入語音路由設定檔
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '摘要: 瞭解如何使用商務用 Skype Server 控制台, 在商務用 Skype Server 中匯出或匯入語音路由設定檔。'
ms.openlocfilehash: 14637694e5604419fcd344b43af98263588f117a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193254"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>在商務用 Skype 中匯出或匯入語音路由設定檔
 
**摘要:** 瞭解如何使用商務用 Skype Server 控制台, 在商務用 Skype Server 中匯出或匯入語音路由設定檔。
  
如果您想要儲存語音路由設定, 但不發佈, 請遵循下列步驟來儲存及取得語音路由設定的快照。 
  
當您匯入語音路由設定檔案 (vcfg), 但同時又在伺服器上對語音路由設定進行變更時, 商務用 Skype Server [控制台] 中的 [**語音路由**] 群組中的頁面會顯示[已未提交] 變更為 [語音路由]。 那些未提交的變更是兩個需要調解的設定之間的差異。
  
如果您已對群組內任何頁面上的設定進行任何未提交的變更, 這些變更就會儲存在匯出的語音設定檔案 (vcfg) 中。 這可讓您在發佈變更前, 在多個會話期間進行語音路由設定的變更。 
  
### <a name="to-export-a-voice-routing-configuration"></a>匯出語音路由設定

1. 以 RTCUniversalServerAdmins 群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。
    
2. 開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**語音路由**]。
    
4. 在 [**動作**] 功能表上, 按一下 [**匯出配置**]。
    
5. 指定位置和檔案名, 然後按一下 [**儲存**]。
    
### <a name="to-import-a-voice-routing-configuration"></a>若要匯入語音路由設定

1. 以 RTCUniversalServerAdmins 群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。
    
2. 開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**語音路由**]。
    
4. 在 [**動作**] 功能表上, 按一下 [匯**入配置**]。
    
5. 找出您要匯入的設定檔, 然後按一下 [**開啟**]。
    
6. 按一下 [**認可**], 然後按一下 [**全部確認**]。
    
    > [!NOTE]
    > 每當您匯入語音設定檔案時, 您必須執行 [**全部提交**] 命令才能發佈設定變更。 如需詳細資訊, 請參閱在作業檔中[發佈商務用 Skype 中的語音路由設定的待處理變更](voice-route-config-changes.md)。
  

