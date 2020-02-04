---
title: Lync Server 2013：啟用呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b89c9b888dc610d60b2abbcefd4c9c67e9b0572e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中啟用呼叫許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。 在您設定 CAC 網路之後，您必須啟用 CAC 來強制執行頻寬限制。 您可以使用 Lync Server [控制台] 來執行這項作業。

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>從 Lync Server [控制台] 啟用 CAC

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**全域**]。

4.  在 [**全域**] 頁面上，按一下 [**全域**配置]。
    
    <div>
    

    > [!NOTE]  
    > 您只能針對任何 Microsoft Lync Server 2013 部署設定一個網路，因此清單中永遠不會有一個以上的網路設定。 您無法重新命名全域配置。

    
    </div>

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

6.  在 [**編輯全域設定**] 頁面上，選取 [**啟用通話許可控制**] 核取方塊，然後按一下 [**確認**]。

當您按一下 [**提交**] 時，就會執行設定測試。 [**編輯全域設定**] 對話方塊隨即關閉，並返回 [**全域**] 頁面。 如果您的網路設定中發現任何錯誤或不一致，都將會收到警告，避免它無法正常運作（例如，如果每個地區都未透過 interregion 路線連線到其他所有區域）。

如果您對網路設定進行變更，您可以開啟 [全域設定] 並按一下 [ **Commit**]，再次執行驗證檢查。 您不需要先停用 CAC，請選取核取方塊，然後按一下 [ **Commit**] （確認）。 您可以隨時執行此動作，而不需變更任何設定。

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的通話許可控制概覽](lync-server-2013-overview-of-call-admission-control.md)  


[在 Lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)  
[CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[移除-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

