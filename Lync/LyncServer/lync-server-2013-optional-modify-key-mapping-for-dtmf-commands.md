---
title: 'DTMF 命令的 Lync Server 2013: （選用） 修改按鍵對應'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd1a6d9d2cf2e97f7b04209d1ca8aab7bdc23456
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>（選用）修改 Lync Server 2013 中的 DTMF 命令的按鍵對應

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-30_

電話撥入式會議使用者可以執行雙音多頻 (DTMF) 命令電話鍵台上按下機碼。 DTMF 命令可讓使用者撥入會議使用其電話按鍵來控制會議設定 （例如靜音和解除靜音本身或鎖定及解除鎖定會議）。 您可以使用 cmdlet 來修改 DTMF 命令所使用的機碼。 此步驟是選用的。

<div>


> [!NOTE]  
> 如需這些 cmdlet 及可用 DTMF 選項的詳細資訊，請參閱 Lync Server 管理命令介面文件或 Lync Server 管理命令介面命令列說明。



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>若要修改 DTMF 命令的按鍵對應

1.  **以 RTCUniversalServerAdmins**群組成員或**Cs-serveradministrator**或**CsAdministrator**角色的成員身分登入電腦。

2.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialinConferencingDtmfConfiguration
    
    此 cmdlet 會傳回用於撥入式會議的 DTMF 設定。

4.  執行下列 cmdlet，並指定要按下您想要變更每個選項的機碼：
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    此 cmdlet 會修改用於電話撥入式會議的 DTMF 設定。
    
    例如：
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    此範例可以互換按下啟用或停用宣告並按下靜音和取消靜音所有參與者的索引鍵的索引鍵。 因為指定沒有 Identity，則這些變更會套用至全域 DTMF 設定。

5.  （選用）若要建立 DTMF 命令的特定網站的其他設定，請使用**New CsDialinConferencingDtmfConfiguration**指令程式與網站身分識別。 當您建立新網站的 DTMF 設定時，網站設定優先於全域設定。 如需詳細資訊，請參閱 Lync Server 管理命令介面文件或 Lync Server 管理命令介面命令列說明。

</div>

</div>

<span> </span>

</div>

</div>

</div>

