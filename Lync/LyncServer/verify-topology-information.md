---
title: 確認拓撲資訊
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4330d31b0cdaf10a3586324711aed98ab541b6eb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>確認拓撲資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

成功完成合併的第一個步驟，就是查看您與 Lync Server 2013 合併的 Office 通訊伺服器 2007 R2 拓撲資訊。 在 [拓撲產生器] 中， **BackCompatSite**節點會顯示每個 Office 通訊伺服器 2007 R2 集區和您合併之伺服器的完整功能變數名稱（FQDN）。

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>若要在拓撲產生器中查看 BackCompatSite

1.  在您的 Office 通訊伺服器 2007 R2 環境中，開啟 Office 通訊伺服器 2007 R2 系統管理工具，並記下舊版集區和伺服器的 Fqdn。

2.  在您的 Lync Server 2013 環境中，開啟拓撲產生器，然後展開 [ **BackCompatSite** ] 節點。

3.  確認所合併之集區與伺服器的 Fqdn 是否隨即顯示。
    
    <div>
    

    > [!NOTE]  
    > 對於組合在前端伺服器或 Standard Edition server 上的伺服器角色，您不會看到<STRONG>BackCompatSite</STRONG>中的任何資訊。 只會顯示 Office 通訊伺服器 2007 R2 和 Lync Server 2013 之間互通性所需的伺服器角色。

    
    </div>

![[拓撲產生器 BackCompatSite] 對話方塊](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "[拓撲產生器 BackCompatSite] 對話方塊")

您也可以使用 Lync Server 2013 控制台，以查看合併的拓撲。 在 [Lync Server 2013 控制台] 中，您可以看到合併的拓撲的每一個伺服器 FQDN、集區 FQDN 及網站名稱。 合併伺服器的**網站**名稱為**BackCompatSite**。

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 控制台中查看合併的拓撲

1.  開啟 [Lync Server 2013 控制台]。

2.  按一下 **[拓撲]**。

3.  在 [**狀態**] 索引標籤上，確認您在 [**網站**] 欄中尋找**BackCompatSite** ，以確認已合併的伺服器和集區。

![顯示合併拓撲的 Lync Server 控制台](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "顯示合併拓撲的 Lync Server 控制台")

若要查看有關合併集區的更多詳細資料，請使用**Get-CsPool** Cmdlet。 除了拓撲產生器和 Lync Server 2013 控制台中提供的資訊之外，此 Cmdlet 還會顯示在 Lync Server 2013 集區上執行的服務。

<div>


> [!NOTE]  
> 當您在拓撲產生器中執行合併嚮導後發行拓撲時，會將會議目錄合併至 Lync Server 2013。 您可以執行<STRONG>Get-CsConferenceDirectory</STRONG> Cmdlet 來驗證會議目錄。



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>在合併集區上查看服務

1.  開啟 [Lync Server 2013 管理命令介面]。

2.  在命令列輸入下列命令：
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    例如：
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>驗證合併的會議目錄

1.  開啟 [Lync Server 2013 管理命令介面]。

2.  在命令列輸入下列命令：
    
        Get-CsConferenceDirectory

3.  確認您要合併之集區或伺服器的所有會議目錄現在皆已在 Lync Server 2013。

</div>

</div>

<span> </span>

</div>

</div>

</div>

