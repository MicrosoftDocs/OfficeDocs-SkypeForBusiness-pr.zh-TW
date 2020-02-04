---
title: Lync Server 2013：查看網路區域資訊
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
ms.openlocfilehash: db5610ddee677af989b16c150ffab96308bbb837
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看網路區域資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

網路區域跨多個地理區域互連網路的各個部分。 每個網路區域都必須與一個中央網站建立關聯。 中央網站是在其上執行呼叫許可控制（CAC）頻寬原則服務的資料中心網站。 您可以使用 Lync Server [控制台] 來查看網路區域。 網路區域包括決定是否允許透過網際網路使用替換路徑進行音訊和視頻連線的設定。 您可以使用本主題來查看現有的網路區域。 如需建立或修改現有網路區域的詳細資料，請參閱[在 Lync Server 2013 中建立或修改網路區域](lync-server-2013-creating-or-modifying-network-regions.md)。

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>使用 Lync Server [控制台] 查看網路區域的相關資訊

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區**]。

4.  在 [**地區**] 頁面上，按一下您要查看的地區。
    
    <div>
    

    > [!NOTE]  
    > 一次只能查看一個區域。

    
    </div>

5.  按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路區域資訊

您可以使用 Windows PowerShell 和**CsNetworkRegion** Cmdlet 來查看網路區域資訊。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-network-region-information"></a>若要查看網路區域資訊

  - 若要查看所有網路區域的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkRegion
    
    這會傳回如下所示的資訊：
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

如需詳細資訊，請參閱[CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立或修改網路區域](lync-server-2013-creating-or-modifying-network-regions.md)  
[在 Lync Server 2013 中刪除現有的網路區域](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

