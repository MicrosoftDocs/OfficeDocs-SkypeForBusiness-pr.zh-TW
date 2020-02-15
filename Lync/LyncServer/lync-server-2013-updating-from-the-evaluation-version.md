---
title: Lync Server 2013： 從的評估版本更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 703362f34c367d301e7d47e1bdc65f16a497ce88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>從 Lync Server 2013 的評估版本更新

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-20 個_

如果您已安裝 Microsoft Lync Server 2013 的評估版本，您最後需要更新，安裝正版軟體;這是因為的評估版本已安裝後的 180 天後到期。 不過，您不需要完全解除安裝評估版本，然後再安裝授權版本。 相反地，在您取得有效的授權金鑰之後，您可以藉由執行下列程序做為 Lync Server 前端伺服器、 Director 或 Edge Server 的每部電腦上更新 Lync Server 2013 評估版。 請注意，您不需要更新執行其他伺服器角色 (如監控伺服器或封存伺服器) 的電腦。

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>從 Microsoft Lync Server 2013 的評估版本更新

若要更新為授權版本軟體的 [從 Lync Server 2013 評估版的電腦：

**從 Microsoft Lync Server 2013 的評估版本更新**

1.  以本機系統管理員身分登入電腦。

2.  按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

3.  在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER:
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    請注意，您可能需要指定檔案 server.msi 的完整路徑。 此檔案可以在 Lync Server 磁碟區媒體安裝檔案的安裝資料夾中找到。

4.  安裝程式完成執行之後，從命令提示字元中輸入下列命令，然後按 ENTER 鍵：
    
        Enable-CsComputer

5.  重複此程序在任何其他前端伺服器、 Director 或 Edge 伺服器執行 Lync Server 評估複本。 也應該使用 Lync Server 媒體安裝檔案已部署任何 Branch Office 伺服器上執行此程序。

如果您不確定給定電腦上執行 Lync Server 的評估版本您可以確認藉由執行從 Lync Server 管理命令介面中的下列命令：

    Get-CsServerVersion

[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) Cmdlet 會分析本機電腦，並回報下列其中一項：

  - Lync Server 的大量授權金鑰，已安裝在電腦上，這表示沒有更新是必要的。

  - 必須更新已表示電腦安裝 Lync Server 評估授權金鑰。

  - 電腦上不需要大量授權金鑰。只有在前端伺服器、Director 及 Edge Server 上才需要從評估版本更新為授權版本。

</div>

</div>

<span> </span>

</div>

</div>

</div>

