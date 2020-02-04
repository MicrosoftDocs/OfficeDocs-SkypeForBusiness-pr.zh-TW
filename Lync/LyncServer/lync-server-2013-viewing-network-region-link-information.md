---
title: Lync Server 2013：查看網路區域連結資訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看網路區域連結資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以在 [呼叫許可控制] （CAC）中，查看兩個網路區域之間的連結。 網路中的區域是透過物理廣域網路（WAN）連線來連結。 您可以使用 Lync Server [控制台] 來查看兩個網路區域之間的現有連結。 如需建立或修改網路區域連結的詳細資料，請參閱[在 Lync Server 2013 中設定網路區域連結](lync-server-2013-configuring-network-region-links.md)。

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>在 Lync Server [控制台] 中查看 [網路區域] 連結

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**網路**設定]，然後按一下 [**地區連結**]。

4.  在 [**地區連結**] 頁面上，按一下您要查看的區域連結。
    
    <div>
    

    > [!NOTE]  
    > 您一次只能查看一個區域連結的相關資訊。

    
    </div>

5.  從 [**編輯**] 功能表中，選取 [**顯示詳細資料**]。

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看網路區域連結資訊

您可以使用 Windows PowerShell 和**CsNetworkRegionLink** Cmdlet 來查看網路區域連結。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-network-region-link-information"></a>若要查看網路區域連結資訊

  - 若要查看所有網路區域連結的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER 鍵：
    
        Get-CsNetworkRegionLink
    
    這個命令會傳回如下所示的資訊：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

如需詳細資訊，請參閱[CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定網路網站連結](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

