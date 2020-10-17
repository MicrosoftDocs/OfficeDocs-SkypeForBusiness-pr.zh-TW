---
title: Lync Server 2013：安裝 Windows PowerShell 3。0
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de45679983221d80171dde8dd37397a8b3a965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534780"
---
# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>安裝 Lync Server 2013 的 Windows PowerShell 3。0

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-27_

若要順利部署 Lync Server 2013，您需要在 Lync Server 拓撲中的每一部電腦上，Windows PowerShell 3.0。

現在，針對執行 Windows Server 2012 或 Windows Server 2012 R2 的系統，您不需要執行任何動作，而且可以繼續進行部署的下一個階段，因為這些作業系統都附帶 PowerShell 3.0。

<div>


> [!IMPORTANT]  
> 但是針對執行 Windows Server 2008 R2 SP1 的系統，在安裝 Lync Server 2013 之前，您必須先將 PowerShell 3.0 安裝成必要條件，否則無法運作。 若要安裝 PowerShell 3.0，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>。 這是 PowerShell 3.0 下載頁面的直接連結，以及與成功安裝相關的資訊。



</div>

在您完成安裝之後，或者您只想要檢查並確定在繼續 Lync Server 部署之前，請確認伺服器上的 PowerShell 3.0 是非常直接的，否則您會這麼做：

1.  在您要檢查的伺服器上，依序選擇 [ **開始**]、[ **所有程式**]、[ **配件**]、[ **Windows PowerShell**]，然後按一下 [ **windows PowerShell**]。

2.  在 [Windows PowerShell] 主控台中，于命令提示字元處輸入下列命令，然後按 ENTER：
    
        Get-Host | Select-Object Version

3.  如果已安裝 Windows PowerShell 3.0，您將會看到輸出，如下所示：
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

