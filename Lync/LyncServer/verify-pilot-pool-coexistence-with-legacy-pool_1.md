---
title: 驗證試驗集區與舊版集區共存
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a7ddba431e1c921df9b3880ee9af73f71584b5f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515920"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>驗證試驗集區與舊版集區共存

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>驗證 Office 通訊伺服器中的集區是否為 2007 R2 系統管理工具

1.  開啟 Office 通訊伺服器 2007 R2 系統管理工具。

2.  依序展開 **[樹系]** 節點及 **[Standard Edition Server]** 或 **[Enterprise Pool]** 節點，然後展開集區或伺服器名稱。

3.  確定集區上的 Office 通訊伺服器 2007 R2 服務正在執行中。
    
    ![Office 通訊伺服器 2007 R2 管理主控台](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office 通訊伺服器 2007 R2 管理主控台")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 控制台中驗證試驗集區

1.  從 CsAdministrator 角色成員的使用者帳戶，登入 Lync Server 2013 前端伺服器。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  按一下 **[拓撲]**。

4.  確認您部署的伺服器位於試驗集區。
    
    ![Lync Server 控制台的拓撲頁面](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server 控制台的拓撲頁面")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>驗證 Lync Server 2013 服務已啟動

1.  在 Lync Server 2013 前端伺服器上，從 [系統**管理工具**] 群組中開啟 [**服務**] 小程式。

2.  確認所列的服務與下圖所示的清單相符。
    
    ![顯示已啟動 Lync 服務的服務頁面](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "顯示已啟動 Lync 服務的服務頁面")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

