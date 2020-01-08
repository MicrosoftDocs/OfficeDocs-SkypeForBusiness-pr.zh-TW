---
title: 移動 Exchange 整合訊息連絡人物件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move Exchange Unified Messaging Contact objects
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49733612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 946bf7221ab9f4c5a7111839bca25dabaad31d82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-exchange-unified-messaging-contact-objects"></a>移動 Exchange 整合訊息連絡人物件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-19_

若要將自動語音應答（AA）及訂閱者存取（SA）連絡人物件遷移至新的 Lync Server 2013 部署，您必須先使用**CsExUmContact**和**CsExUmContact** Cmdlet，將舊版 Office 通訊伺服器 2007 R2 部署中的物件移至新的 lync server 2013 部署。 在 Exchange 伺服器上，您可以執行**ExchUCUtil** Windows PowerShell 腳本來針對新部署的 Lync pool 執行下列動作：

  - 將它新增到 [統一訊息 IP 閘道]。

  - 將它新增到 [整合訊息查尋] 群組。

<div>


> [!NOTE]  
> 若要使用<STRONG>CsExUmContact</STRONG>和<STRONG>CsExUmContact</STRONG> Cmdlet，您必須是 [RTCUniversalUserAdmins] 群組的成員，並對儲存連絡人物件的 OU 擁有組織單位（OU）許可權。 您可以使用<STRONG>Grant OUPermission</STRONG> Cmdlet 來授與 OU 許可權。



</div>

<div>

## <a name="to-move-contact-objects-by-using-the-lync-server-management-shell"></a>使用 Lync Server 管理命令介面移動連絡人物件

1.  開啟 Lync Server 管理命令介面。

2.  針對使用 Exchange UM 註冊的每個池（其中 pool1.contoso.net 是 Office 通訊伺服器 2007 R2 部署，pool2.contoso.net 是來自 Lync Server 2013 部署的 pool），請輸入以下命令：
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    若要驗證連絡人物件是否已移動，請執行**CsExumContact** Cmdlet，並確認**RegistrarPool**現在是指向新的池中。

</div>

<div>

## <a name="to-run-the-exchucutil-windows-powershell-script"></a>若要執行 ExchUCUtil Windows PowerShell 腳本

1.  以 Exchange 組織管理員許可權的使用者身分登入 Exchange UM 伺服器。

2.  流覽至 ExchUCUtil Windows PowerShell 腳本。
    
    在 Exchange 2007 中，ExchUCUtil 是位於： **%\\Program Files%\\Microsoft Exchange Server\\腳本\\ExchUCUtil. ps1**
    
    在 Exchange 2010 中，ExchUCUtil 是位於： **%\\Program Files% Microsoft\\Exchange Server\\V14\\腳本\\ExchUCUtil. ps1**

3.  如果 Exchange 是在單一目錄林中部署，請輸入：
    
        exchucutil.ps1
    
    或者，如果 Exchange 是部署在多個目錄林中，請輸入：
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    其中，目錄林 FQDN 會指定部署 Lync Server 2013 的林。
    
    <div>
    

    > [!IMPORTANT]  
    > 執行 exchucutil<EM>後</EM>，請務必重新開機<STRONG>Lync Server 前端</STRONG>服務（rtcsrv）。 否則，Lync Server 2013 在拓撲中不會偵測到統一訊息。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

