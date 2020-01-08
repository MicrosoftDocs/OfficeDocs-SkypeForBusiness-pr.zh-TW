---
title: 驗證試驗集區與舊版集區共存
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f67b113a4619d90345df9858f348d663383066d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>驗證試驗集區與舊版集區共存

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>驗證 Office 通訊伺服器 2007 R2 管理工具中的資源庫

1.  開啟 Office 通訊伺服器 2007 R2 管理工具。

2.  展開 [**目錄林**] 節點，展開 [**標準版伺服器**] 或 [**企業版池**] 節點，然後展開 [池] 或 [伺服器名稱]。

3.  確定 Office 通訊伺服器 2007 R2 服務正在該池中執行。
    
    ![Office 通訊伺服器 2007 R2 管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "office 通訊伺服器 2007 R2 系統管理主控台")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>確認 Lync Server 2013 [控制台] 中的 [試驗] 池

1.  從屬於 CsAdministrator 角色成員的使用者帳戶登入 Lync Server 2013 前端伺服器。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  按一下 [**拓撲**]。

4.  確認您部署的伺服器存在於您的試驗區池中。
    
    ![Lync Server 控制台拓撲頁面][(images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync server 控制台拓撲] 頁面")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>驗證 Lync Server 2013 服務已啟動

1.  在 Lync Server 2013 前端伺服器上，從 [**管理工具**] 群組開啟 [**服務**] 小工具。

2.  確認列出的服務與下圖中的清單相符。
    
    ![顯示 [lync services 已啟動]服務] 頁面的 [服務] 頁面，(images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "顯示 lync services 已啟動")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

