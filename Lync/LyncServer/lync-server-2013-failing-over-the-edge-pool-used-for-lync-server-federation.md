---
title: Lync Server 2013：容錯移轉用於 Lync Server 同盟的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68969c0e7be81eca835661e3fb6a19f1565e623f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982547"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

如果您已將 Lync Server federation 的邊緣池設定為 down，您必須將同盟變更為使用不同的邊緣池才能運作。

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>針對 Lync Server Federation 所用的邊緣池進行容錯移轉

1.  在前端伺服器上，開啟 [拓撲建立器]。 展開 [**邊緣池**]，然後以滑鼠右鍵按一下目前針對同盟設定的邊緣伺服器或 edge 伺服器池。 選取 [**編輯屬性**]。

2.  在 [**編輯屬性**] 底下的 **[一般**] 底下，清除 **[針對此 Edge 池啟用同盟（埠5061）**]。 按一下 [確定]****。

3.  展開 [**邊緣池**]，然後以滑鼠右鍵按一下您要用於同盟的邊緣伺服器或 edge 伺服器池。 選取 [**編輯屬性**]。

4.  在 [**編輯屬性**] 底下的 **[一般**] 底下，選取 **[針對此 Edge 池啟用同盟（埠5061）**]。 按一下 [確定]****。

5.  按一下 [**動作**]，選取 [**拓撲**]，選取 [**發佈**]。 **發佈拓撲**時出現提示時，請按 **[下一步]**。 發佈完成後，請按一下 **[完成]**。

6.  在邊緣伺服器上，開啟 Lync Server 部署嚮導。 按一下 [**安裝或更新 Lync Server 系統**]，然後按一下 [**設定] 或 [移除 Lync server 元件**]。 再次按一下 [**執行**]。

7.  在安裝程式 Lync Server 元件上，按一下 **[下一步]**。 [摘要] 畫面會在執行時顯示動作。 完成部署之後，按一下 [**查看記錄**] 以查看可用的記錄檔。 按一下 **[完成]** 以完成部署。
    
    如果包含失敗的邊緣池的網站包含仍在執行的前端伺服器，您必須更新這些前端池的 Web 會議服務和 A/V 會議服務，才能在仍在執行的遠端網站中使用 Edge 池。 如需詳細資訊，請參閱[在 Lync Server 2013 中變更與前端池相關聯的邊緣池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[在 Lync Server 2013 中容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Lync Server 2013 中的 Edge Server 災害復原](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

