---
title: Lync Server 2013：查看網路網站資訊
description: Lync Server 2013：查看網路網站資訊。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b46dc91510cb5ff737977871470033374573ba8c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546219"
---
# <a name="viewing-network-site-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看網路網站資訊

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

網路網站是設定在通話許可控制 (CAC) 或增強型 9-1-1 部署之每一個地區內部的辦公室或位置。 您可以在 Lync Server 2013 控制台或 Lync Server 管理命令介面中查看網路網站資訊。 如需建立或修改網站的詳細資訊，請參閱 [在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-creating-or-modifying-network-sites.md)。

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a>在 Lync Server 控制台中查看網路網站資訊

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 [網路設定]**** 和 [網站]****。

4.  在 [網站]**** 頁面上，按一下您要檢視的網站。
    
    <div>
    

    > [!NOTE]  
    > 您一次僅可檢視一個網站的網站資訊。

    
    </div>

5.  在 [編輯]**** 功能表上，按一下 [顯示詳細資料]****。

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來查看網路網站資訊

您可以使用 Windows PowerShell 和 Get-CsNetworkSite Cmdlet 來查看網路網站資訊。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-network-site-information"></a>若要檢視網路網站資訊

  - 若要查看所有網路網站的相關資訊，請在 Lync Server 管理命令介面中輸入下列命令，然後按 ENTER：
    
        Get-CsNetworkSite
    
    如此將傳回類似如下的資訊：
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

如需詳細資訊，請參閱＜[Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)＞Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-creating-or-modifying-network-sites.md)  
[在 Lync Server 2013 中刪除現有的網路網站](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

