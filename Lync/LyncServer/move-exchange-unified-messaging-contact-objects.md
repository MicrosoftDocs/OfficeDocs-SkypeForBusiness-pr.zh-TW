---
title: 移動 Exchange 整合通訊連絡人物件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ebfecb0c9c37c802a8ee883e4c2db2f909cf774
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>移動 Exchange 整合通訊連絡人物件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-19_

將自動語音應答 (AA) 及訂戶存取 (SA) 連絡人物件移轉至新的 Lync Server 2013 部署中，您第一次物件從舊版 Office Communications Server 2007 R2 部署移至新的 Lync Server 2013 部署使用**Get-csexumcontact**和**Move-csexumcontact** cmdlet。 在 Exchange 伺服器上，然後執行**ExchUCUtil** Windows PowerShell 指令碼，以執行新部署的 Lync 集區下列動作：

  - 將其新增至整合通訊 IP 閘道。

  - 將其新增至整合通訊群組搜尋。

<div>


> [!NOTE]  
> 若要使用 <STRONG>Get-CsExUmContact</STRONG> 和 <STRONG>Move-CsExUmContact</STRONG> Cmdlet，您必須是 RTCUniversalUserAdmins 群組的成員，且具備連絡人物件存放所在的組織單位 (OU) 權限。使用 <STRONG>Grant-OUPermission</STRONG> Cmdlet，即可授與此 OU 權限。



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>使用 Lync Server 管理命令介面移動連絡人物件

1.  開啟 Lync Server 管理命令介面。

2.  每個集區與 Exchange UM （其中 pool1.contoso.net 是從 Office Communications Server 2007 R2 部署的集區，而 pool2.contoso.net 是從 Lync Server 2013 部署的集區） 註冊在命令列中，輸入下列命令：
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    若要確認連絡人物件是否移動，請執行 **Get-CsExumContact** Cmdlet 並確認 **[RegistrarPool]** 現在已指向新集區。

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>執行 ExchUCUtil Windows PowerShell 指令碼

1.  以具備 Exchange 組織系統管理員權限的使用者登入 Exchange UM Server。

2.  瀏覽至 ExchUCUtil Windows PowerShell 指令碼。
    
    在 Exchange 2007 中，ExchUCUtil.ps1 位於： **%Program Files %\\Microsoft\\Exchange 伺服器\\指令碼\\ExchUCUtil.ps1**
    
    在 Exchange 2010 中，ExchUCUtil.ps1 位於： **%Program Files %\\Microsoft\\Exchange 伺服器\\V14\\指令碼\\ExchUCUtil.ps1**

3.  如果 Exchange 部署在單一樹系中，請輸入：
    
        exchucutil.ps1
    
    或者，如果 Exchange 部署在多個樹系中，請輸入：
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    其中樹系 FQDN 指定部署 Lync Server 2013 時的樹系。
    
    <div>
    

    > [!IMPORTANT]  
    > 請務必在執行 exchucutil.ps1 之後<EM></EM>，重新啟動 <STRONG>[Lync Server 前端]</STRONG> 服務 (rtcsrv.exe)。 否則，Lync Server 2013 將不會偵測整合通訊拓撲中。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

