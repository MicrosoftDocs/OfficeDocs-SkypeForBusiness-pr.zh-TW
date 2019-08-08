---
title: 在商務用 Skype Server 中啟用企業語音的使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '摘要: 瞭解如何在商務用 Skype Server 中使用企業語音來撥打及接聽通話。'
ms.openlocfilehash: cf9aab0f104582c57e745c95ae5cf8f24f07b3a5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240610"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用企業語音的使用者
 
**摘要:** 瞭解如何在商務用 Skype Server 中使用企業語音來撥打和接聽通話。
  
透過工作部署企業語音或通話之後, 您可以使用下列程式, 讓使用者使用企業語音撥打通話:
  
> [!NOTE]
> 在下列程式中, 只有第一個程式可以使用商務用 Skype Server 的 [控制台] 執行。 在其餘的程式中, 您只能使用商務用 Skype Server Management Shell。 
  
- 啟用企業語音的使用者帳戶。
    
- 可選指派使用者帳戶專用的語音原則。
    
- 可選將使用者帳戶指派給使用者專用的撥號方案。
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>啟用企業語音的使用者帳戶

1. 以 RTCUniversalServerAdmins 群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。
    
2. 開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中, 按一下 [**使用者**]。
    
4. 在 [**搜尋使用者**] 方塊中, 輸入您要啟用之使用者帳戶的全部或部分的顯示名稱、名字、姓氏、安全帳戶管理員 (SAM) 帳戶名稱、SIP 位址或行統一資源識別項 (URI), 然後按一下[**尋找**]。
    
5. 在表格中, 按一下您要為企業語音啟用的使用者帳戶。
    
6. 按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。
    
7. 在 [**編輯商務用 Skype Server 使用者**] 頁面的 [**電話**] 底下, 按一下 [**企業語音**]。
    
8. 按一下 [**行 URI**], 然後輸入唯一的、標準化的電話號碼 (例如電話: + 14255550200)。
    
9. 按一下 [認可]****。
    
若要為使用者啟用企業語音, 請確定使用者已獲指派語音原則和撥號方案, 不論全域 (預設為指派) 或使用者專用。根據預設, 所有使用者都會獲指派全域語音原則和撥號方案。 如果使用者帳戶所在網站的網站層級存在語音原則或撥號方案, 這些網站原則將會自動套用至使用者。 若要將每個使用者的語音原則或撥號方案套用至使用者, 您必須執行**授與 CsVoicePolicy**並**授與 CsDialPlan** Cmdlet。 如需詳細資訊, 請參閱本主題中的下列程式。
## <a name="voice-policy-assignment"></a>語音原則指派

全域及網站層級語音原則會自動指派給所有已啟用企業語音的使用者帳戶。 您也可以建立適用于特定使用者或群組的語音原則。 這些每個使用者的原則必須明確指派給使用者或群組。 如果您想要針對所有已啟用企業語音的使用者使用全域或網站語音原則, 您可以略過此區段, 然後繼續本主題稍後的[撥號計畫作業](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment)區段。
  
### <a name="to-assign-a-user-specific-voice-policy"></a>指派使用者專用的語音原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. 若要將現有的使用者語音原則指派給使用者, 請在命令提示字元執行下列動作:
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    在這個範例中, 使用顯示名稱 Bob 凱利的使用者會獲指派「名稱**VoicePolicyJapan**」的語音原則。
    
## <a name="dial-plan-assignment"></a>撥號方案指派
<a name="BKMK_DialPlanAssignment"> </a>

若要為企業語音或電話撥入式會議的使用者完成使用者帳戶設定, 必須為使用者指派撥號方案。 如果您不明確指派現有的每個使用者撥號方案, 使用者帳戶就會自動使用全域撥號方案, 或 (如果有的話)。 如果您想要針對所有已啟用企業語音的使用者使用全域或網站撥號方案, 您可以略過本節。
  
### <a name="to-assign-a-user-specific-dial-plan"></a>指派使用者專用的撥號方案

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. 若要指派使用者特定的撥號方案, 請在命令提示字元執行下列動作:
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    例如：
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    在這個範例中, 使用顯示名稱 Bob 凱利的使用者會被指派名稱為**DialPlanJapan**的使用者撥號計畫。
    

