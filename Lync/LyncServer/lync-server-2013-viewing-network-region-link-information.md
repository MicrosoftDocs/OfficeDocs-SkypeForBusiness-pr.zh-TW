---
title: Lync Server 2013：查看網路地區連結資訊
description: Lync Server 2013：查看網路地區連結資訊。
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
ms.openlocfilehash: 0134ded9942ebda91050c1f7b0bbcfef018451a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565359"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看網路地區連結資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

您可以透過通話許可控制 (CAC) 檢視兩個網路地區之間的連結。 網路中的地區是透過實體廣域網路 (WAN) 連線相連結。 您可以使用 Lync Server 控制台來查看兩個網路地區之間的現有連結。 如需建立或修改網路地區連結的詳細資訊，請參閱 [在 Lync Server 2013 中設定網路地區連結](lync-server-2013-configuring-network-region-links.md)。

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>在 Lync Server 控制台中查看網路地區連結

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  按一下左導覽列中的 [網路設定]****，然後按一下 [地區連結]****。

4.  在 [區域連結]**** 頁面中，按一下要檢視的區域連結。
    
    <div>
    

    > [!NOTE]  
    > 一次只能檢視一個區域的資訊。

    
    </div>

5.  從 [編輯]**** 功能表中，選取 [顯示詳細資料]****。

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路地區連結資訊

您可以使用 Windows PowerShell 和 **Get-CsNetworkRegionLink** Cmdlet 來查看網路地區連結。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-network-region-link-information"></a>檢視網路地區連結資訊

  - 若要查看所有網路地區連結的資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsNetworkRegionLink
    
    此命令會傳回與下列相似的資訊：
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

如需詳細資訊，請參閱 [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定網路站台連結](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

