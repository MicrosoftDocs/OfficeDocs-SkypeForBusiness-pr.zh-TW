---
title: 在安全性設定精靈於 IIS 中關閉連接埠後重新啟動伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>在安全性設定精靈於 IIS 中關閉連接埠後重新啟動伺服器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

部分 Lync Server 2013 角色會在網際網路 Information Services （IIS）埠4443上執行 Web 服務。 執行 Lync Server 部署嚮導、引導程式，或使用**Enable-CsComputer** Cmdlet，就會在防火牆中建立例外狀況，並開啟埠。 如果您接著執行 Windows Server 2008 R2 安全性設定向導（或其他強化腳本），埠4443將會遭到封鎖，而且外部用戶端將無法與 Web 服務取得聯繫。 若要重新開啟埠，您可以直接修改防火牆例外狀況，或重新開機伺服器。

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>使用 [部署嚮導] 重新開機伺服器

1.  在 [Lync Server 部署嚮導] 頁面上，按一下 [**步驟2：設定**] 旁的 [**執行**]，或移除 [lync server 元件]。

2.  在 [**安裝 Lync Server 元件**] 頁面上，按一下 **[下一步]**。

3.  在 [**執行命令**] 頁面上，當任務狀態顯示為 [完成] 時，按一下 **[完成]**。
    
    <div>
    

    > [!NOTE]
    > 您也可以使用 CsComputer，或<STRONG>啟用-</STRONG>以重新開機伺服器。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

