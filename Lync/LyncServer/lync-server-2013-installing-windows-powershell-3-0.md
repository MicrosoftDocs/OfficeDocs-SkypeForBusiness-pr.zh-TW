---
title: Lync Server 2013：安裝 Windows PowerShell 3.0
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>針對 Lync Server 2013 安裝 Windows PowerShell 3.0

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-06-27_

若要成功部署 Lync Server 2013，您需要在您的 Lync Server 拓撲中的每一部電腦上都要有 Windows PowerShell 3.0。

現在，對於執行 Windows Server 2012 或 Windows Server 2012 R2 的系統，您不需要執行任何動作，而且可以繼續進行部署的下一個階段，因為這些作業系統隨附 PowerShell 3.0。

<div>


> [!IMPORTANT]  
> 但對於執行 Windows Server 2008 R2 SP1 的系統，您必須先安裝 PowerShell 3.0，才能安裝 Lync Server 2013，否則無法運作。 若要安裝 PowerShell 3.0，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</A>。 這是 PowerShell 3.0 下載頁面的直接連結，以及成功安裝的相關資訊。



</div>

完成安裝之後，或者只要想要在繼續 Lync Server 部署之前檢查並確定，確認 PowerShell 3.0 在伺服器上是相當簡單的做法：

1.  在您想要檢查的伺服器上，選擇 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [ **Windows PowerShell**]，然後按一下 [ **windows powershell**]。

2.  在 Windows PowerShell 主控台中，在命令提示字元中輸入下列命令，然後按 ENTER：
    
        Get-Host | Select-Object Version

3.  如果已安裝 Windows PowerShell 3.0，您會看到如下所示的輸出：
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

