---
title: 在商務用 Skype 中管理應用層級回應群組設定
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: 在商務用 Skype Server 企業語音中管理應用層級回應群組設定，例如「暫停音樂」和「回電設定」。
ms.openlocfilehash: 6cce6872bc0e1ee017d46eee4ee547c6e9aabd25
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769611"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a>在商務用 Skype 中管理應用層級回應群組設定
 
在商務用 Skype Server 企業語音中管理應用層級回應群組設定，例如「暫停音樂」和「回電設定」。
  
回應群組應用程式的應用層級設定包括預設的等候音樂設定、預設的等候音樂音訊檔、代理程式回電寬限時間，以及通話內容設定。 您只能為每個集區定義一組應用層級的設定。 若要查看應用層級設定，請使用 **Get-CsRgsConfiguration** Cmdlet。 若要修改應用層級設定，請使用 **Set-CsRgsConfiguration** Cmdlet。
  
只有在未定義自訂等候音樂的情況下，才會播放呼叫保留的預設音樂。 「呼叫內容」只適用于指派給互動式工作流程的佇列。 如果已啟用呼叫內容，代理程式會在接收來電時，看到如來電者等候時間或工作流程問題和答案等資訊。
  
### <a name="to-modify-response-group-application-level-settings"></a>修改回應群組的應用層級設定

1. 以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。
    
2. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
3. 在命令列中執行：
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    例如：
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    若要指定用來做為預設等候音樂的音訊檔，您必須先匯入音訊檔案。 例如：
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a>另請參閱

[Get-CsRgsConfiguration](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[Set-CsRgsConfiguration](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)