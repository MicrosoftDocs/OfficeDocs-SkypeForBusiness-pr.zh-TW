---
title: 移動 Exchange 整合通訊連絡人物件
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42abb209eaf59be66c8516401616dcac4f1c94ad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500290"
---
# <a name="move-exchange-unified-messaging-contact-objects"></a>移動 Exchange 整合通訊連絡人物件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

若要將自動語音應答 (AA) 和使用者存取 (SA) 連絡人物件遷移至新的 Lync Server 2013 部署，您必須先使用 **Get-CsExUmContact** 和 **Move-CsExUmContact** Cmdlet，將物件從舊版 Office 通訊伺服器 2007 R2 部署移至新的 lync server 2013 部署。 在 Exchange 伺服器上，您可以執行 **ExchUCUtil** Windows PowerShell 腳本，針對新部署的 Lync 集區執行下列作業：

  - 將其新增至整合通訊 IP 閘道。

  - 將其新增至整合通訊群組搜尋。

<div>


> [!NOTE]  
> 若要使用 <STRONG>Get-CsExUmContact</STRONG> 和 <STRONG>Move-CsExUmContact</STRONG> Cmdlet，您必須是 RTCUniversalUserAdmins 群組的成員，且具備連絡人物件存放所在的組織單位 (OU) 權限。使用 <STRONG>Grant-OUPermission</STRONG> Cmdlet，即可授與此 OU 權限。



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>使用 Lync Server 管理命令介面移動連絡人物件

1.  開啟 Lync Server 管理命令介面。

2.  針對每個註冊于 Exchange UM (的集區，其中 pool1.contoso.net 是 Office 通訊伺服器 2007 R2 部署的集區，而 pool2.contoso.net 是來自 Lync Server 2013) 部署的集區，請在命令列中輸入下列命令：
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    若要確認連絡人物件是否移動，請執行 **Get-CsExumContact** Cmdlet 並確認 **[RegistrarPool]** 現在已指向新集區。

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>執行 ExchUCUtil Windows PowerShell 指令碼

1.  以具備 Exchange 組織系統管理員權限的使用者登入 Exchange UM Server。

2.  流覽至 ExchUCUtil Windows PowerShell 腳本。
    
    在 Exchange 2007 中，ExchUCUtil.ps1 位於： **% Program Files% \\ Microsoft \\ Exchange Server \\ 腳本 \\ExchUCUtil.ps1**
    
    在 Exchange 2010 中，ExchUCUtil.ps1 位於： **% Program Files% \\ Microsoft \\ Exchange Server \\ V14 \\ 腳本 \\ExchUCUtil.ps1**

3.  如果 Exchange 部署在單一樹系中，請輸入：
    
        exchucutil.ps1
    
    或者，如果 Exchange 部署在多個樹系中，請輸入：
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    其中，樹系 FQDN 會指定要在其中部署 Lync Server 2013 的樹系。
    
    <div>
    

    > [!IMPORTANT]  
    > 請務必在執行 exchucutil.ps1 之後<EM></EM>，重新啟動 <STRONG>[Lync Server 前端]</STRONG> 服務 (rtcsrv.exe)。 否則，Lync Server 2013 將不會在拓撲中偵測到整合通訊。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

