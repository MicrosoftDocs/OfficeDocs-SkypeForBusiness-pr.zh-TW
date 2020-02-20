---
title: 'Lync Server 2013: Lync Server 管理命令介面'
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
ms.openlocfilehash: f367ec9ff3f990c410a95289c159bb021b053cec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 管理命令介面

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017年-09-20 個_

<div>


> [!NOTE]  
> Skype for Business cmdlet 參照已移至 docs.microsoft.com。 按一下下列連結將帶您前往 [新增 docs.microsoft.com] 頁面。 內容現在是透過 GitHub 開啟來源，並可供社群參與。 參與有興趣嗎？ 請參閱 「 讀我檔案中的儲存機制：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 引進了一大組的相較於什麼是 Microsoft Office Communications Server 2007 R2 中可用的新增和改善功能。 其中一項改良功能是管理實作的方式。 例如，沒有新的使用者介面，稱為 「 Lync Server Control Panel，查看大部分的人員使用 Microsoft Management Console，是用來代表 big shift 鍵。 其他主要的改善管理性是 Windows PowerShell 的相對路徑。

Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。 它包括命令列環境、產品特定命令，以及完整指令碼語言。 Windows PowerShell 第一次中已導入與 Windows 作業系統可下載發行最遲 2006，並已合併為命令列介面的 Microsoft Exchange Server 2007 的管理性。 從該點它可以繼續成長，以及它具有已納入大部分的 Microsoft 伺服器產品，最新版的這些正在 Microsoft Lync Server 2013。 Lync Server 2010 引進了接近 550 特定產品 cmdlet 可以用來管理您的部署的每個層面。

下列各節包含 Cmdlet 及其描述的清單。 此資訊也可以直接從命令列取得。 只在 Lync Server 管理命令介面命令提示字元處輸入下列命令：

    Get-Help <cmdlet name> -Full

例如，若要從命令提示字元擷取 **New-CsVoicePolicy** Cmdlet 的說明，請輸入下列命令：

    Get-Help New-CsVoicePolicy -Full

若要了解 Windows PowerShell 在 Lync Server 2013 中的項目：

  - 若要執行 Lync Server 指令程式，開啟 [Lync Server 管理命令介面]。
    
    <div>
    

    > [!WARNING]  
    > 如果您開啟 Windows PowerShell 視窗，而不是在 Lync Server 管理命令介面]，依預設您將無法執行 Lync Server cmdlet。 若要執行從 Windows PowerShell 中的 Lync Server 指令程式，請先在 Windows PowerShell 命令提示字元處輸入下列命令：<BR>Import-Module Lync

    
    </div>

  - Lync Server 管理命令介面會自動安裝每個 Lync Server Enterprise Edition 前端伺服器或 Standard Edition server 上。

  - 最新及更新的資訊、 範例指令碼，以及開始使用並深入了解 Windows PowerShell 和 Microsoft Lync Server 2013 cmdlet 的說明位於 Lync Server Windows PowerShell 部落格[https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)。

</div>

<span> </span>

</div>

</div>

</div>

