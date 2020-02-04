---
title: Lync Server 2013：刪除組呼叫提貨號碼範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66b95df76c812b50ff9c220ea208406a5ab7cf2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741023"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a>刪除 Lync Server 2013 中的群組呼叫挑選號碼範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

使用下列程式刪除群組通話編號範圍。

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a>刪除呼叫挑選群組的數位範圍

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令列中，輸入：
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    例如：
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > 如需更多選項的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">移除-CsCallParkOrbit</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改通話駐留軌道的範圍](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[移除-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

