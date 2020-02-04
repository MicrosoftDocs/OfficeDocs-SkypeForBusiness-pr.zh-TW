---
title: Lync Server 2013：針對使用者啟用通話駐留
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
ms.openlocfilehash: cd89ba10f5cae16e88c65e6e56178fc517c71213
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中為使用者啟用通話駐留

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

使用者在語音原則中啟用通話駐留前，不能寄存通話或取得停用通話。

<div>


> [!NOTE]  
> 根據預設，會停用所有使用者的 [通話駐留]。



</div>

您可以在全域範圍或在網站範圍或使用者範圍中啟用通話駐留。 [使用者範圍] 的優先順序高於 [網站範圍]，而 [網站範圍] 的優先順序高於 [全域範圍]。 如果您有多個語音原則，請查看所有原則來啟用通話駐留，而不只是全域原則。

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>使用 Lync Server [控制台] 為使用者啟用通話駐留

1.  以**RTCUniversalServerAdmins**群組的成員或**CsVoiceAdministrator**、 **CsServerAdministrator**或**CsAdministrator**系統管理角色的成員的身分登入電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音路由**]。

4.  按一下 [**語音原則**] 索引標籤。

5.  按兩下現有的語音原則，以開啟 [**編輯語音原則**] 對話方塊。

6.  在 [**呼叫功能**] 底下，選取 [**啟用通話駐留**]。

7.  按一下 **[確定]** 儲存語音原則

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>若要使用 Cmdlet 來為使用者啟用通話駐留

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 系統管理角色的成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  用盡
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    例如，若要針對預設的全域語音原則啟用通話駐留，請執行下列動作：
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立語音原則和設定 PSTN 使用記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

