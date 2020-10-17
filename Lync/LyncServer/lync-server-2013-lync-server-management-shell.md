---
title: Lync Server 2013： Lync Server 管理命令介面
description: Lync Server 2013： Lync Server 管理命令介面。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45727c42899defcf20ce36e2a27a9268a52ecd71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543179"
---
# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理命令介面

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-09-20_

<div>


> [!NOTE]  
> 商務用 Skype Cmdlet 參考已移至 docs.microsoft.com。 按一下下列連結將會帶您前往 [新增 docs.microsoft.com] 頁面。 內容現在已開啟，且可透過 GitHub 進行社區貢獻。 對共同作業感興趣？ 請參閱下列位置的讀我檔案： <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 引進了一組龐大的新功能與改進功能，與 Microsoft Office 通訊伺服器 2007 R2 中提供的功能相較。 其中一項改良功能是管理實作的方式。 例如，有一個新的使用者介面（稱為 Lync Server 控制台），它代表與 Microsoft 管理主控台使用大部分人員的大量班次。 其他可管理性的重大改善是包含 Windows PowerShell。

Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。 它包括命令列環境、產品特定命令，以及完整指令碼語言。 Windows PowerShell 第一次是在2006中新增為 Windows 作業系統的可下載版本，已融入為 Microsoft Exchange Server 2007 的可管理性命令列介面。 從該點繼續成長，並已合併至大多數的 Microsoft Server 產品中，最新的是 Microsoft Lync Server 2013。 Lync Server 2010 引進接近550產品特有的 Cmdlet，您可以用來管理部署的各個層面。

下列各節包含 Cmdlet 及其描述的清單。 此資訊也可以直接從命令列取得。 只需在 Lync Server 管理命令介面命令提示字元處輸入下列命令：

    Get-Help <cmdlet name> -Full

例如，若要從命令提示字元擷取 **New-CsVoicePolicy** Cmdlet 的說明，請輸入下列命令：

    Get-Help New-CsVoicePolicy -Full

有關在 Lync Server 2013 中瞭解 Windows PowerShell 的事項：

  - 若要執行 Lync Server Cmdlet，請開啟 Lync Server 管理命令介面。
    
    <div>
    

    > [!WARNING]  
    > 如果您開啟的是 Windows PowerShell 視窗，而不是 Lync Server 管理命令介面，依預設，您將無法執行 Lync Server Cmdlet。 若要從 Windows PowerShell 內執行 Lync Server Cmdlet，請先在 Windows PowerShell 命令提示字元處輸入下列命令：<BR>Import-Module Lync

    
    </div>

  - Lync Server 管理命令介面會自動安裝在每一部 Lync Server Enterprise Edition 前端伺服器或 Standard Edition server 上。

  - 有關 Windows PowerShell 和 Microsoft Lync Server 2013 Cmdlet 的新增及更新資訊、範例腳本及協助，可在 Lync Server Windows PowerShell 博客中取得 [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) 。

</div>

<span> </span>

</div>

</div>

</div>

