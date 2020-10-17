---
title: Lync Server 2013： (選用) Modify DTMF 命令的按鍵對應
description: Lync Server 2013： (選用) Modify DTMF 命令的按鍵對應。
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
ms.openlocfilehash: 7581001c31d929163962378a8734435f6d07c6c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565789"
---
# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a> (選用) 在 Lync Server 2013 中修改 DTMF 命令的按鍵對應

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-30_

電話撥入式會議使用者可按下電話按鍵上的按鍵，以執行雙音多頻率 (DTMF) 命令。 DTMF 命令可讓撥入會議的使用者控制會議設定 (例如，靜音和 unmuting 本身，或使用電話上的小鍵盤鎖定和解除鎖定會議) 。 您可以使用 Cmdlet 來修改 DTMF 命令所使用的金鑰。 這是選擇性的步驟。

<div>


> [!NOTE]  
> 如需這些 Cmdlet 及可能的 DTMF 選項的詳細資訊，請參閱 Lync Server 管理命令介面檔或 Lync Server Management Shell 命令列說明。



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>修改 DTMF 命令的按鍵對應

1.  以 **RTCUniversalServerAdmins** 群組成員的身分，或是 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色的成員身分登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
        Get-CsDialinConferencingDtmfConfiguration
    
    此 Cmdlet 會傳回用於電話撥入式會議的 DTMF 設定。

4.  執行下列 Cmdlet，並指定要變更之每個選項的按鍵：
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    此 Cmdlet 會修改用於電話撥入式會議的 DTMF 設定。
    
    例如：
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    這個範例會將已按下的按鍵換用，以啟用或停用用來啟用或停用的宣告和按鍵，以靜音和取消靜音所有參與者。 因為未指定身分識別，所以這些變更會套用到全域 DTMF 設定。

5.   (選用) 若要為特定網站建立其他 DTMF 命令集，請使用具有網站身分識別的 **set-csdialinconferencingdtmfconfiguration** Cmdlet。 當您為網站建立新的 DTMF 設定時，網站設定會優先于通用設定。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔或 Lync Server Management Shell 命令列說明。

</div>

</div>

<span> </span>

</div>

</div>

</div>

