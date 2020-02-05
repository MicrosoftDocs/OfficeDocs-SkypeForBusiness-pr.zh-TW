---
title: 在商務用 Skype 中發佈 [語音路由設定] 的擱置變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 摘要：瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中查看、發佈或取消語音路由設定變更。
ms.openlocfilehash: 12cf80c2a14d3bad532aaf21a942536f44537300
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766956"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>在商務用 Skype 中發佈 [語音路由設定] 的擱置變更
 
**摘要：** 瞭解如何使用商務用 Skype Server 控制台，在商務用 Skype Server 中查看、發佈或取消語音路由設定變更。
  
在您針對 [**語音路由**] 群組中的頁面變更任何設定設定之後，請執行此程式來審閱、發佈或解除擱置中的變更。
  
> [!IMPORTANT]
> 確定一次只有一個使用者會修改 [語音路由設定] 設定。 
  
> [!NOTE]
> 只要執行 [**全部提交**] 命令，就必須同時發佈所有擱置中的變更。 您無法選擇性地發佈擱置中的變更。 發佈待定變更之前，請先執行 [**查看未提交的變更**] 命令，然後取消任何您不想發佈的設定變更。
  
> [!NOTE]
> 如果您在提交掛起的變更前，移出 [**語音路由**] 群組中的頁面，所有擱置的變更都會遺失。 不過，您可以將目前的設定（包括任何擱置中的變更）匯出到語音設定檔案，然後匯入併發布更新的設定。 如需詳細資訊，請參閱[在商務用 Skype 中匯出或匯入語音路由設定檔](voice-route-configuration-import-export.md)。 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>若要查看、發佈或取消語音路由設定變更

1. 以 RTCUniversalServerAdmins 群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。
    
2. 開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**語音路由**]。
    
4. 針對 [**語音路由**] 群組的每個頁面上的設定變更您想要的設定。
    
5. 若要查看待定的變更而不發佈，請選取 [**確認**] 功能表中的 [**查看未提交的變更**]。
    
6. 如果您想要取消任何待定的變更，請執行下列其中一項操作：
    
   - 從 [**認可**] 功能表中選取 [**取消所有未提交的變更**]。
    
   - 流覽至含有您要取消之待定變更之 [**語音路由**] 頁面的索引標籤，選取含有待定變更的專案，按一下 [**認可**]，然後按一下 [**取消選取的變更**]。
    
7. 審閱完所有擱置的變更並取消任何不想發佈的變更之後，請按一下 [**認可**]，然後按一下 [**全部提交**]。
    
8. 在 [**未提交的語音設定**] 對話方塊中，顯示所有待定變更的清單，按一下 **[確定]**。 
    
    當商務用 Skype Server 控制台提交變更之後，就會出現 [**成功發佈的語音路由**設定] 訊息。
    

