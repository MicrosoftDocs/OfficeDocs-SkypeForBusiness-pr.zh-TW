---
title: 確認拓撲資訊
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5987dc071abb888f8d1f6eca0d3082f2a8ab7523
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>確認拓撲資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-26_

確認已順利完成合併的第一個步驟是檢視合併與 Lync Server 2013 的 Office Communications Server 2007 R2 拓撲資訊。 在拓撲產生器中，[ **BackCompatSite** ] 節點會顯示每個 Office Communications Server 2007 R2 集區和所合併的伺服器的完整的網域名稱 (FQDN)。

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>若要在拓撲產生器中檢視 BackCompatSite

1.  在 Office Communications Server 2007 R2 環境中，開啟 Office Communications Server 2007 R2 系統管理工具]，然後記下舊版集區和伺服器的 Fqdn。

2.  在 Lync Server 2013 環境中，開啟拓撲產生器]，然後展開 [ **BackCompatSite** ] 節點。

3.  確認所合併的伺服器與集區的 fqdn 均有顯示。
    
    <div>
    

    > [!NOTE]  
    > 您的前端伺服器或 Standard Edition server 上沒看到<STRONG>BackCompatSite</STRONG>中組合的伺服器角色的任何資訊。 顯示所需的 Office Communications Server 2007 R2 和 Lync Server 2013 之間的互通性伺服器角色。

    
    </div>

![拓撲產生器 BackCompatSite] 對話方塊](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "拓撲產生器 BackCompatSite] 對話方塊")

您也可以使用 Lync Server 2013 控制台檢視合併後的拓撲。 在 Lync Server 2013 控制台中，您可以看到每個伺服器 FQDN、 集區 FQDN] 中，並合併拓撲的網站名稱。 合併的伺服器有**BackCompatSite**的**網站**名稱。

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>若要在 Lync Server 2013 Control Panel 中檢視合併後的拓撲

1.  開啟 Lync Server 2013 控制台。

2.  按一下 **[拓撲]**。

3.  在 [**狀態**] 索引標籤，確認伺服器和集區所合併出現的 [**網站**] 欄中尋找**BackCompatSite** 。

![Lync Server Control Panel 顯示合併後的拓撲](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "Lync Server Control Panel 顯示合併後的拓撲")

若要查看合併的集區相關的詳細資料，請使用**Get-cspool** cmdlet。 除了在拓撲產生器和 Lync Server 2013 控制台的資訊，此 cmdlet 會顯示 [Lync Server 2013 集區執行的服務。

<div>


> [!NOTE]  
> 當您執行合併列印精靈在拓撲產生器之後發行拓撲時，會議目錄被合併到 Lync Server 2013。 藉由執行<STRONG>Get-csconferencedirectory</STRONG> cmdlet 可驗證會議目錄。



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>若要檢視合併後集區上的服務

1.  開啟 [Lync Server 2013 管理命令介面]。

2.  在命令列輸入下列命令：
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    例如：
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>若要確認會議目錄合併

1.  開啟 [Lync Server 2013 管理命令介面]。

2.  在命令列輸入下列命令：
    
        Get-CsConferenceDirectory

3.  確認集區或您要合併的伺服器的所有會議目錄都皆已在 Lync Server 2013。

</div>

</div>

<span> </span>

</div>

</div>

</div>

