---
title: 管理商務用 Skype 中的應用層級回應群組設定
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: 在商務用 Skype Server Enterprise Voice 中管理應用程式層級回應群組設定, 例如 [音樂封存] 和 [ringback 設定]。
ms.openlocfilehash: 500ed8942fb859ce41340c94d0568e9e87b1c3d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191128"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>管理商務用 Skype 中的應用層級回應群組設定
 
在商務用 Skype Server Enterprise Voice 中管理應用程式層級回應群組設定, 例如 [音樂封存] 和 [ringback 設定]。
  
回應群組應用程式的應用程式層級設定包括預設的 [以音樂為保留] 設定、預設的 [音樂保留] 音訊檔案、[代理程式 ringback 寬限期], 以及 [通話內容] 設定。 每個 pool 只能定義一組應用層級設定。 若要查看應用程式層級的設定, 請使用**CsRgsConfiguration** Cmdlet。 若要修改應用程式層級的設定, 請使用**CsRgsConfiguration** Cmdlet。
  
只有在已定義 [保留自訂的音樂] 時, 才會播放預設的 [等候音樂] 狀態。 只有在指派給互動式工作流程的佇列中, 才能使用呼叫內容。 如果已啟用呼叫內容, 則代理程式可以在收到來電時, 看到來電者等候時間或工作流程問題與解答等資訊。
  
### <a name="to-modify-response-group-application-level-settings"></a>修改回應群組的應用層級設定

1. 以 RTCUniversalServerAdmins 群組成員的身分登入, 或以支援回應群組的預先定義之系統管理角色的成員的身分登入。
    
2. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
3. 在命令列上執行:
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    例如：
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    若要將音訊檔案指定為保留預設的音樂, 您必須先匯入音訊檔案。 例如：
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>另請參閱

[CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[匯入-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
