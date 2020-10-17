---
title: Lync Server 2013：從評估版本更新
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
ms.openlocfilehash: 21fa1c35cff49205a7287841ac90c5dd9f0a4510
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506690"
---
# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a>從 Lync Server 2013 評估版更新

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-20_

如果您已安裝 Microsoft Lync Server 2013 的評估版，最後必須更新該安裝軟體的授權副本;這是因為評估版本在安裝後會到期180天。 不過，您不需要完全解除安裝評估版本，然後再安裝授權版本。 在取得有效的授權金鑰之後，您可以在擔任 Lync Server 前端伺服器、Director 或 Edge Server 的每一部電腦上執行下列程式，以更新 Lync Server 2013 的評估版。 請注意，您不需要更新執行其他伺服器角色 (如監控伺服器或封存伺服器) 的電腦。

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a>從 Microsoft Lync Server 2013 的評估版本更新

若要將電腦從 Lync Server 2013 評估版更新為軟體的授權版本：

**從 Microsoft Lync Server 2013 的評估版本更新**

1.  以本機系統管理員身分登入電腦。

2.  依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在 Lync Server 管理命令介面中，輸入下列命令，然後按 ENTER：
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    請注意，您可能需要指定檔案 server.msi 的完整路徑。 您可以在 Lync Server 磁片區媒體安裝檔案的 Setup 資料夾中找到此檔案。

4.  安裝程式完成執行之後，從命令提示字元中輸入下列命令，然後按 ENTER 鍵：
    
        Enable-CsComputer

5.  在執行 Lync Server 評估副本的任何其他前端伺服器、Director 或 Edge Server 上重複此程式。 您也應該在任何使用 Lync Server media 安裝檔案部署的分支 Office 伺服器上執行此程式。

如果您不確定 Lync Server 的評估版本是在指定的電腦上執行，您可以在 Lync Server 管理命令介面中執行下列命令，以驗證：

    Get-CsServerVersion

[Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) Cmdlet 會分析本機電腦，並回報下列其中一項：

  - 已在電腦上安裝 Lync Server 大量授權金鑰，這表示不需要更新。

  - 已安裝 Lync Server 評估授權碼，這表示必須更新電腦。

  - 電腦上不需要大量授權金鑰。只有在前端伺服器、Director 及 Edge Server 上才需要從評估版本更新為授權版本。

</div>

</div>

<span> </span>

</div>

</div>

</div>

