---
title: 安全性設定向導在 IIS 中關閉埠後重新開機伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a72bfcf9facfeaa3ca943275d9cdcb3b1ac7705
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512040"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>安全性設定向導在 IIS 中關閉埠後重新開機伺服器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

某些 Lync Server 2013 角色會在網際網路資訊服務（) 埠4443）上執行 Web 服務 (IIS。 執行 Lync Server 部署嚮導、Bootstrapper.exe 或使用 **Enable-CsComputer** Cmdlet 會在防火牆中建立例外狀況，並開啟埠。 如果您接著執行 Windows Server 2008 R2 安全性設定向導 (或其他強化腳本) ，將會封鎖埠4443，而且外部用戶端將無法連絡 Web 服務。 若要重新開啟埠，您可以直接修改防火牆例外狀況，也可以重新開機伺服器。

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>使用部署嚮導重新開機伺服器

1.  在 [Lync Server 部署嚮導] 頁面上，按一下 [**步驟2：安裝或移除 Lync Server 元件**] 旁邊的 [**執行**]。

2.  在 **[安裝 Lync Server 元件]** 頁面上，按 **[下一步]**。

3.  在 **[執行命令]** 頁面上，當工作狀態顯示為完成後，按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]
    > 您也可以使用 bootstrapper.exe 或 <STRONG>Enable-CsComputer</STRONG> ，以重新開機伺服器。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

