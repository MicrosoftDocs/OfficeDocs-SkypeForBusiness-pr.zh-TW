---
title: Lync Server 2013： 管理應用程式層級回應群組設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1dccc404350e10b61ea0917c0bd6b6d7e44b333
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a>管理 Lync Server 2013 中的應用程式層級回應群組設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-01_

回應群組應用程式的應用程式層級設定包含預設的等候音樂上保留設定、 預設的等候音樂上保留音訊檔案、 代理人回電寬限期，以及來電內容設定。 您可以定義只有一組每個集區的應用程式層級設定。 若要檢視應用程式層級設定，請使用**Get-csrgsconfiguration**指令程式。 若要修改的應用程式層級設定，請使用**Set-csrgsconfiguration** cmdlet。

當通話處於保留狀態，只有當不定義任何自訂等候音樂，就會播放預設等候音樂。 呼叫內容是僅供指派給互動式工作流程的佇列。 如果啟用來電內容時，代理程式可以看到資訊，例如來電者時收到通話時的等待時間或工作流程的問題和解答。

<div>

## <a name="to-modify-response-group-application-level-settings"></a>若要修改回應群組應用程式層級設定

1.  以 RTCUniversalServerAdmins 群組成員身分或其中一個預先定義的系統管理角色支援回應群組的成員身分登入。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  在命令列中執行：
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    例如：
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    若要指定要當成預設等候音樂音訊檔，您必須先匯入的音訊檔案。 例如：
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a>請參閱


[Get-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[Set-csrgsconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[Import-csrgsaudiofile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

