---
title: Lync Server 2013：啟用通話許可控制
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
ms.openlocfilehash: 857dce2203bf9713676113ba4fa0e8b6f4ec5a60
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>在 Lync Server 2013 中啟用通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

通話許可控制 (CAC) 是由地區、網站和子網路所構成的網路，可讓您根據可用頻寬來限制音訊和視訊傳輸。 在您設定 CAC 網路之後，您必須啟用 CAC 以強制實施頻寬限制。 您可以使用 Lync Server 控制台執行這項作業。

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>從 Lync Server 控制台啟用 CAC

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[網路設定]**，然後按一下 **[全域]**。

4.  在 **[全域]** 頁面上，按一下 **[全域]** 設定。
    
    <div>
    

    > [!NOTE]  
    > 您只能為任何 Microsoft Lync Server 2013 部署設定一個網路，所以清單中永遠不會有一個以上的網路設定。 您無法重新命名 [全域] 設定。

    
    </div>

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

6.  在 **[編輯通用設定]** 頁面上，選取 **[啟用通話許可控制]** 核取方塊，然後按一下 **[認可]**。

當您按一下 **[認可]** 時，便會執行設定的測試。**[編輯通用設定]** 對話方塊隨即關閉，您會回到 **[全域]** 頁面。如果在網路設定中發現任何會使網路無法正常運作 (例如，每個區域未透過區域間路由彼此連線) 的錯誤或不一致情形，您將會收到警告。

如果您變更了網路設定，您可以開啟 [全域] 設定並按一下 **[認可]**，再次執行驗證檢查。您不需要先停用 CAC：使核取方塊保持已勾選狀態並按一下 **[認可]**。您可以隨時這麼做，而不需進行任何設定變更。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的通話許可控制概覽](lync-server-2013-overview-of-call-admission-control.md)  


[在 Lync Server 2013 中規劃通話許可控制](lync-server-2013-planning-for-call-admission-control.md)  
[在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

