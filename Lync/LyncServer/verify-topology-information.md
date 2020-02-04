---
title: 驗證拓撲資訊
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
ms.openlocfilehash: ec6c73f274cb67b527aaf1147f20e83959487255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>驗證拓撲資訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

驗證已成功完成合併的第一個步驟是，要查看您與 Lync Server 2013 合併的 Office 通訊伺服器 2007 R2 拓撲資訊。 在拓撲建立器中， **BackCompatSite**節點會顯示您合併的每個 Office 通訊伺服器 2007 R2 池和伺服器的完整功能變數名稱（FQDN）。

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>在拓撲產生器中查看 BackCompatSite

1.  在您的 Office 通訊伺服器 2007 R2 環境中，開啟 Office 通訊伺服器 2007 R2 管理工具，並記下舊版池和伺服器的 Fqdn。

2.  在 Lync Server 2013 環境中，開啟 [拓撲建立器]，然後展開 [ **BackCompatSite** ] 節點。

3.  確認會顯示您所合併之池和伺服器的 Fqdn。
    
    <div>
    

    > [!NOTE]  
    > 您不會在<STRONG>BackCompatSite</STRONG>中看到在前端伺服器或標準版伺服器上 collocated 的伺服器角色的任何資訊。 顯示 Office 通訊伺服器 2007 R2 和 Lync Server 2013 之間的互通性所需的伺服器角色。

    
    </div>

![拓撲產生器的 [BackCompatSite] 對話方塊](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "拓撲產生器的 [BackCompatSite] 對話方塊")

您也可以使用 Lync Server 2013 [控制台] 來查看合併的拓撲。 在 Lync Server 2013 的 [控制台] 中，您可以查看合併後拓撲的每個伺服器 FQDN、池 FQDN 和網站名稱。 合併伺服器的**網站**名稱為**BackCompatSite**。

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 的 [控制台] 中查看合併的拓撲

1.  開啟 Lync Server 2013 [控制台]。

2.  按一下 [**拓撲**]。

3.  在 [**狀態**] 索引標籤上，請在 [**網站**] 欄中尋找 [ **BackCompatSite** ]，確認您已合併的伺服器和池都出現。

![顯示合併拓撲的 Lync Server 控制台](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "顯示合併拓撲的 Lync Server 控制台")

若要查看合併池的更多詳細資料，請使用**CsPool** Cmdlet。 除了拓撲結構建立器和 Lync Server 2013 [控制台] 中提供的資訊，此 Cmdlet 還會顯示在 Lync Server 2013 池中執行的服務。

<div>


> [!NOTE]  
> 在拓撲建立器中執行合併嚮導後發佈拓撲，會議目錄會合並至 Lync Server 2013。 您可以執行<STRONG>CsConferenceDirectory</STRONG> Cmdlet 來驗證會議目錄。



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>若要在合併的文檔池中查看服務

1.  開啟 Lync Server 2013 管理命令介面。

2.  在命令列中，輸入下列內容：
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    例如：
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>驗證已合併的會議目錄

1.  開啟 Lync Server 2013 管理命令介面。

2.  在命令列中，輸入下列內容：
    
        Get-CsConferenceDirectory

3.  確認目前在 Lync Server 2013 中的是您要合併之池或伺服器的所有會議目錄。

</div>

</div>

<span> </span>

</div>

</div>

</div>

