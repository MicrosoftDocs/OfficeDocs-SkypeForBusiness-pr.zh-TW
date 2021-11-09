---
title: 在商務用 Skype Server 中為使用者啟用企業語音
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 摘要：瞭解如何使用商務用 Skype Server 中的企業語音，讓使用者能夠撥打和接聽電話。
ms.openlocfilehash: 3dab9488b1d184f5d3dd215f4012933de1ca0245
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864340"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>在商務用 Skype Server 中為使用者啟用企業語音
 
**摘要：** 瞭解如何使用商務用 Skype Server 中的企業語音，讓使用者能夠撥打和接聽電話。
  
在您部署企業語音或呼叫透過工作之後，您可以使用下列程式，讓使用者使用企業語音來撥打電話：
  
> [!NOTE]
> 在下列程式中，只能使用商務用 Skype Server 控制台來執行第一個程式。 對於其餘的程式，您只能使用商務用 Skype Server 管理命令介面。 
  
- 為企業語音啟用使用者帳戶。
    
-  (選用) 指派使用者特有的語音原則的使用者帳戶。
    
-  (選用) 指派使用者特定撥號對應表的使用者帳戶。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>為企業語音啟用使用者帳戶

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator** 或 **CsAdministrator** 系統管理角色的成員身分登入電腦。
    
2. 開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 **[使用者]**。
    
4. 在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。
    
5. 在表格中，按一下您要為企業語音啟用的使用者帳戶。
    
6. 在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。
    
7. 在 [**編輯商務用 Skype Server 使用者**] 頁面的 [**電話語音**] 下，按一下 [**企業語音**]。
    
8. 按一下 [ **行 URI**]，然後輸入唯一的標準化電話號碼 (例如， `tel:+14255550200`) 。
    
9. 按一下 **[認可]**。
    
若要為使用者啟用企業語音，請確定使用者已獲指派語音原則和撥號對應表，不論是預設指派的全域 () 或特定使用者。根據預設，會為所有使用者指派通用語音原則和撥號對應表。 如果語音原則或撥號對應表存在於使用者帳戶所在網站的網站層級上，這些網站原則將會自動套用至使用者。 若要將個別使用者的語音原則或撥號對應表套用至使用者，您必須執行 **Grant-CsVoicePolicy** 和 **Grant-CsDialPlan** Cmdlet。 如需詳細資訊，請參閱本主題中的下列程式。
## <a name="voice-policy-assignment"></a>語音原則指派

全域和網站層級語音原則會自動指派給所有為企業語音啟用的使用者帳戶。 您也可以建立適用于特定使用者或群組的語音原則。 這些每個使用者的原則都必須明確指派給使用者或群組。 如果您想要針對所有已啟用企業語音的使用者使用 global 或 site voice 原則，您可以略過本節並繼續本主題稍後的 [撥號對應表[指派](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)] 區段。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>指派使用者特有的語音原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 若要將現有的使用者語音原則指派給使用者，請在命令提示字元中執行下列命令：
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    在此範例中，具有顯示名稱小明凱利的使用者會被指派名稱為 **VoicePolicyJapan** 的語音原則。
    
## <a name="dial-plan-assignment"></a>撥號對應表指派
<a name="BKMK_DialPlanAssignment"> </a>

若要為企業語音的使用者或電話撥入式會議的使用者完成使用者帳戶設定，必須為使用者指定撥號對應表。 當您未明確指派現有的個別使用者撥號對應表時，使用者帳戶會自動使用全域撥號對應表或網站層級撥號對應表（如果有的話）。 如果您想要針對所有已啟用企業語音的使用者使用全域或網站撥號對應表，您可以略過本節。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>指派使用者特有的撥號對應表

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 若要指派使用者特有的撥號對應表，請在命令提示字元中執行下列命令：
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    在此範例中，具有顯示名稱小明凱利的使用者會被指派名稱為 **DialPlanJapan** 的使用者撥號對應表。
    

