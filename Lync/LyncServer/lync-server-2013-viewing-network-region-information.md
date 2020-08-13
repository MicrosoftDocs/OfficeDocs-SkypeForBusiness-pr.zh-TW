---
title: Lync Server 2013：查看網路地區資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d59e8182c0ebe904d61dd18e9cd3653f58a6fb4a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看網路地區資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

網路地區會與跨多個地理區域的網路不同部分交互連線。 每個網路地區都必須與中央網站產生關聯。 中央網站是執行通話許可控制服務 (CAC) 頻寬原則服務的資料中心網站。 您可以使用 Lync Server 控制台來查看網路地區。 網路地區包含的設定可決定是否允許透過網際網路的替代路徑進行音訊和視訊連線。 請使用本主題檢視現有的網路地區。 如需建立或修改現有網路地區的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改網路地區](lync-server-2013-creating-or-modifying-network-regions.md)。

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>使用 Lync Server 控制台查看網路區域的相關資訊

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 **[網路設定]** 和 **[地區]**。

4.  在 **[地區]** 頁面上，按一下您要檢視的區域。
    
    <div>
    

    > [!NOTE]  
    > 您一次僅可檢視一個區域。

    
    </div>

5.  在 **[編輯]** 功能表上，按一下 **[顯示詳細資料]**。

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路地區資訊

您可以使用 Windows PowerShell 和**Get-CsNetworkRegion** Cmdlet 來查看網路地區資訊。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-network-region-information"></a>若要查看網路地區資訊

  - 若要查看所有網路區域的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsNetworkRegion
    
    如此將傳回類似如下的資訊：
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

如需詳細資訊，請參閱 [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改網路地區](lync-server-2013-creating-or-modifying-network-regions.md)  
[在 Lync Server 2013 中刪除現有的網路地區](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

