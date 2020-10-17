---
title: Lync Server 2013：容錯移轉用於 Lync Server 同盟的 Edge 集區
description: Lync Server 2013：容錯移轉用於 Lync Server 同盟的 Edge 集區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1e7e13ccd35a653d38174f55ace9dc6637ded04
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554909"
---
# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

如果在設定 Lync Server 同盟的 Edge 集區發生問題，則必須變更同盟使用不同的 Edge 集區，同盟才能運作。

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>容錯移轉用於 Lync Server 同盟的 Edge 集區

1.  在前端伺服器上，開啟拓撲產生器。展開 **[Edge 集區]**，然後在目前設定用於同盟的 Edge Server 或 Edge Server 集區上按一下滑鼠右鍵。選取 **[編輯內容]**。

2.  在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]****。按一下 [確定]****。

3.  展開 [Edge 集區]****，然後在現在要用於同盟的 Edge Server 或 Edge Server 集區上按一下滑鼠右鍵。選取 [編輯內容]****。

4.  在 [編輯內容]**** 中，選取 [一般]**** 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。按一下 **[確定]**。

5.  按一下 **[動作]**，依序選取 **[拓撲]** 和 **[發行]**。在 **[發行拓撲]** 出現提示時，按 **[下一步]**。發行完成時，按一下 **[完成]**。

6.  在 Edge Server 上開啟 [Lync Server 部署精靈]。依序按一下 **[安裝或更新 Lync Server 系統]**、**[安裝或移除 Lync Server 元件]**、**[再執行一次]**。

7.  在 [安裝 Lync Server 元件] 中，按 **[下一步]**。摘要畫面會隨著動作的執行顯示各個動作。部署完成後，按一下 **[檢視記錄檔]** 檢視可用的記錄檔。按一下 **[完成]** 完成部署。
    
    如果失敗 Edge 集區所在的網站包含仍在執行的前端伺服器，則必須更新在這些前端集區上的 Web 會議服務及 A/V 會議服務，以使用遠端網站上仍在執行的 Edge 集區。 如需詳細資訊，請參閱 [變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)區。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[在 Lync Server 2013 中回復用於 Lync Server 同盟或 XMPP 同盟的 Edge 集區](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Lync Server 2013 中的 Edge Server 災難性修復](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

