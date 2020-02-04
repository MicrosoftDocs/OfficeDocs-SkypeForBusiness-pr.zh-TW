---
title: Lync Server 2013： Lync Server Management 命令介面
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
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理命令介面

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-09-20_

<div>


> [!NOTE]  
> 商務用 Skype Cmdlet 參考已移至 docs.microsoft.com。 按一下下方的連結，會將您帶到 [新增 docs.microsoft.com] 頁面。 內容現在已開啟來源，且可供 GitHub 的群組發佈。 想要進行共同作業嗎？ 查看存放庫中的讀我檔案：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 引進了一組較大的新功能和改良功能，與 Microsoft Office 通訊伺服器 2007 R2 中提供的功能比較。 其中一個改善是您管理實施的方式。 例如，有一個新的使用者介面（稱為 Lync Server [控制台]），代表在 Microsoft 管理主控台中使用大部分人員的大量班次。 易管理性的另一個主要改進，就是加入了 Windows PowerShell。

Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。 它包含命令列環境、產品特定命令及完整的腳本撰寫語言。 Windows PowerShell 最初是在2006中提供給 Windows 作業系統的可下載版本，並已融入為 Microsoft Exchange Server 2007 可管理性的命令列介面。 從那一開始，我們已將它整合到大部分的 Microsoft 伺服器產品中，最新的是 Microsoft Lync Server 2013。 Lync Server 2010 引進了550個產品專用的 Cmdlet，您可以用來管理您的部署的各個方面。

下列各節包含 Cmdlet 及其描述的清單。 此資訊也可以直接從命令列取得。 只要在 Lync Server 管理命令介面命令提示字元輸入以下內容：

    Get-Help <cmdlet name> -Full

例如，若要從命令提示字元擷取 **New-CsVoicePolicy** Cmdlet 的說明，請輸入下列命令：

    Get-Help New-CsVoicePolicy -Full

有關 Lync Server 2013 中的 Windows PowerShell 須知：

  - 若要執行 Lync Server Cmdlet，請開啟 Lync Server 管理命令介面。
    
    <div>
    

    > [!WARNING]  
    > 如果您開啟的是 Windows PowerShell 視窗，而不是 Lync Server 管理命令介面，預設將無法執行 Lync Server Cmdlet。 若要從 Windows PowerShell 中執行 Lync Server Cmdlet，請先在 Windows PowerShell 命令提示字元中輸入下列內容：<BR>匯入模組 Lync

    
    </div>

  - Lync Server 管理命令介面會自動安裝在每個 Lync Server 企業版前端伺服器或標準版伺服器上。

  - 新功能和更新的資訊、範例腳本，以及有關 Windows PowerShell 和 Microsoft Lync Server 2013 Cmdlet 的說明，可在 Lync Server Windows PowerShell 博客[https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)中取得。

</div>

<span> </span>

</div>

</div>

</div>

