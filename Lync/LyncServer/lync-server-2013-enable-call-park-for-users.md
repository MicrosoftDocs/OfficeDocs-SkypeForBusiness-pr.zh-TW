---
title: Lync Server 2013：為使用者啟用通話駐留
description: Lync Server 2013：為使用者啟用通話駐留。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7f9ab23b9fa71943efafd588b8c57a2af781b08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561029"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中為使用者啟用通話駐留

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

使用者在語音原則中為通話駐留啟用電話時，無法寄存通話或取得寄存的通話。

<div>


> [!NOTE]  
> 預設會停用所有使用者的通話駐留。



</div>

您可以在全域範圍或網站範圍或使用者範圍上啟用通話駐留。 使用者範圍優先于網站範圍，而網站範圍優先于全域範圍。 如果您有多個語音原則，請複習所有原則以啟用通話駐留，而不只是全域原則。

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>使用 Lync Server 控制台為使用者啟用通話駐留

1.  以 **RTCUniversalServerAdmins** 群組成員的身分，或是 **CsVoiceAdministrator**、 **CsServerAdministrator**或 **CsAdministrator** 系統管理角色的成員身分登入電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[語音路由]**。

4.  按一下 [ **語音原則** ] 索引標籤。

5.  按兩下現有的語音原則，以開啟 [ **編輯語音原則** ] 對話方塊。

6.  在 [ **通話功能**] 底下，選取 [ **啟用通話駐留**]。

7.  按一下 **[確定]** 以儲存語音原則

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>若要使用 Cmdlet 為使用者啟用通話駐留

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 系統管理角色的成員身分登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  運行：
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    例如，若要啟用預設全域語音原則的通話駐留：
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

