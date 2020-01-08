---
title: Lync Server 2013：從評估版本更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b00fed276229cbaf0e960e28e622e490fb0bfbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>從 Lync Server 2013 評估版更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

如果您已安裝 Microsoft Lync Server 2013 評估版，最終必須更新該安裝軟體的授權複本;這是因為評估版本在安裝後會過期180天。 不過，您不需要完全卸載評估版本，然後再安裝授權版本。 在取得有效的授權金鑰之後，您可以在充當 Lync Server 前端伺服器、控制器或邊緣伺服器的每個電腦上執行下列程式，以更新 Lync Server 2013 的評估版本。 請注意，您不需要更新執行其他伺服器角色（例如監視伺服器或存檔伺服器）的電腦。

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>從評估版的 Microsoft Lync Server 2013 更新

若要將電腦從 Lync Server 2013 評估版更新為軟體的授權版本：

**從評估版的 Microsoft Lync Server 2013 更新**

1.  以本機系統管理員的身分登入電腦。

2.  按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER：
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    請注意，您可能需要指定檔案伺服器 .msi 的完整路徑。 您可以在 Lync Server Volume 媒體安裝檔案的 [設定] 資料夾中找到此檔案。

4.  安裝程式完成後，請從命令提示字元輸入以下內容，然後按 ENTER：
    
        Enable-CsComputer

5.  在執行 Lync Server 評估複本的任何其他前端伺服器、控制器或邊緣伺服器上，重複此程式。 您也應該在任何使用 Lync Server 媒體安裝檔案部署的分支機搆伺服器上執行此程式。

如果您不確定 Lync Server 的評估版本是否在指定的電腦上執行，您可以從 Lync Server Management Shell 中執行下列命令，以驗證：

    Get-CsServerVersion

[CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) Cmdlet 會分析本機電腦，並傳回下列其中一項：

  - Lync Server 大量授權金鑰已安裝在電腦上，這表示不需要更新。

  - 已安裝 Lync Server 評估版授權金鑰，這表示電腦必須更新。

  - 電腦上不需要大量的授權金鑰。 只有在前端伺服器、控制器和 Edge 伺服器上才需要從評估版更新為授權版本。

</div>

</div>

<span> </span>

</div>

</div>

</div>

