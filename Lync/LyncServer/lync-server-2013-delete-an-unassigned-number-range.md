---
title: Lync Server 2013：刪除未指定的數位範圍
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a80a28cf4ee5b310790a057253ea52ca17a14aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a>在 Lync Server 2013 中刪除未指定的數位範圍

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

使用下列其中一個程式來刪除公告的未指定編號範圍。

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a>使用 Lync Server [控制台] 刪除未指定的數位範圍

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**語音功能**]，然後按一下 [**未指定的號碼**]。

4.  在 [**未指定的號碼**] 頁面上，于 [搜尋] 欄位中，輸入您要刪除的未指派數位範圍的全部或部分名稱。

5.  在產生的數位範圍清單中，按一下名稱，按一下 [**編輯**]，然後按一下 [**刪除**]。

6.  按一下 [**全部確認**]。

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a>使用 Windows PowerShell 刪除未指定的數位範圍

1.  登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令列中，輸入：
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    例如：
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > 如需更多選項的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">移除-CsCallParkOrbit</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改未指定的數位範圍](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[移除-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

