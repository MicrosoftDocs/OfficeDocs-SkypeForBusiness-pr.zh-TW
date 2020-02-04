---
title: Lync Server 2013：(選用) 修改 DTMF 命令的按鍵對應
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
ms.openlocfilehash: 036092f1199ad0e361f8509b36930410685ece21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>(選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

電話撥入式會議使用者可以按電話鍵臺上的按鍵，以執行雙音調多頻率（DTMF）命令。 DTMF 命令可讓撥入會議的使用者控制會議設定（例如靜音及 unmuting 本身，或是使用電話鍵，在通話中鎖定及解除鎖定會議）。 您可以使用 Cmdlet 來修改 DTMF 命令所使用的金鑰。 此為選用步驟。

<div>


> [!NOTE]  
> 如需這些 Cmdlet 和可能的 DTMF 選項的詳細資訊，請參閱 Lync Server 管理命令介面檔或 Lync Server 管理命令列說明。



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>修改 DTMF 命令的金鑰組應

1.  以**RTCUniversalServerAdmins**群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元執行下列動作：
    
        Get-CsDialinConferencingDtmfConfiguration
    
    這個 Cmdlet 會傳回電話撥入式會議所用的 DTMF 設定。

4.  針對您要變更的每個選項，執行下列 Cmdlet，並指定要按下的索引鍵：
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    這個 Cmdlet 會修改用於電話撥入式會議的 DTMF 設定。
    
    例如：
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    這個範例會交換按下來啟用或停用宣告的索引鍵，以及按下以將所有參與者取消靜音和取消靜音的按鍵。 由於沒有指定身分識別，這些變更會套用到全域 DTMF 設定。

5.  可選若要針對特定網站建立其他 DTMF 命令組，請搭配使用**CsDialinConferencingDtmfConfiguration** Cmdlet 搭配網站身分識別。 當您為網站建立新的 DTMF 設定時，網站設定會優先于全域設定。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔或 Lync Server Management Shell 命令列說明。

</div>

</div>

<span> </span>

</div>

</div>

</div>

