---
title: 容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

當您用來主持同盟的邊緣池已重新連線之後，請使用此程式來容錯回復 Lync Server 同盟路由和/或 XMPP 同盟路由，以再次使用此已還原的邊緣池。

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>無法將同盟切回已還原的邊緣池

1.  在現在可以再次使用的邊緣池中，啟動 Edge 服務。

2.  如果您想要將 Lync Server 同盟路由容錯回復到使用已還原的邊緣伺服器，請執行下列動作：
    
      - 在前端伺服器上，開啟 [拓撲建立器]。 展開 [**邊緣池**]，然後以滑鼠右鍵按一下目前針對同盟設定的邊緣伺服器或 edge 伺服器池。 選取 [**編輯屬性**]。
    
      - 在 [**編輯屬性**] 底下的 **[一般**] 底下，清除 **[針對此 Edge 池啟用同盟（埠5061）**]。 按一下 [確定]****。
    
      - 展開 [**邊緣池**]，然後以滑鼠右鍵按一下您想要用於同盟的原始邊緣伺服器或 edge 伺服器池。 選取 [**編輯屬性**]。
    
      - 在 [**編輯屬性**] 底下的 **[一般**] 底下，選取 **[針對此 Edge 池啟用同盟（埠5061）**]。 按一下 [確定]****。
    
      - 按一下 [**動作**]，選取 [**拓撲**]，選取 [**發佈**]。 **發佈拓撲**時出現提示時，請按 **[下一步]**。 發佈完成後，請按一下 **[完成]**。
    
      - 在邊緣伺服器上，開啟 Lync Server 部署嚮導。 按一下 [**安裝或更新 Lync Server 系統**]，然後按一下 [**設定] 或 [移除 Lync server 元件**]。 再次按一下 [**執行**]。
    
      - 在安裝程式 Lync Server 元件上，按一下 **[下一步]**。 [摘要] 畫面會在執行時顯示動作。 完成部署之後，按一下 [**查看記錄**] 以查看可用的記錄檔。 按一下 **[完成]** 以完成部署。

3.  如果您想要將 XMPP 同盟路由容錯回復到使用已還原的邊緣伺服器，請執行下列動作：
    
      - 執行下列 Cmdlet，將 XMPP 同盟路由 repoint 到 Edge 池中，這將會立即託管 XMPP 同盟（在此範例中為 EdgeServer1）：
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        在這個範例中，Site1 是包含邊緣池的網站，現在將託管 XMPP 同盟路由，而 EdgeServer1.contoso.com 是該池中的邊緣伺服器的 FQDN。
    
      - 如果您還沒有可解析到 Edge 池的 XMPP 同盟的 DNS SRV 記錄，而該內容現在將託管 XMPP 同盟，您必須新增該記錄，如下列範例所示。 這個 SRV 記錄的埠值必須是5269。
        
            _xmpp-server._tcp.contoso.com
    
      - 在外部 DNS 伺服器上，將 XMPP 同盟的 DNS A 記錄變更為指向 EdgeServer2.contoso.com。
    
      - 確認現在將由 XMPP 同盟託管的邊緣池已在外部開啟埠5269。

4.  如果前端池仍在包含已失敗且已還原的邊緣池的網站中執行，您應該在這些前端池上更新網路會議服務和 A/V 會議服務，以再次使用其本機網站上的邊緣池。 如需詳細資訊，請參閱[在 Lync Server 2013 中變更與前端池相關聯的邊緣池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。

5.  如果與失敗的邊緣池位於同一網站的前端池也失敗，您現在可以使用 Invoke-CsPoolFailback 來容錯回復前端池。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Lync Server 2013 中的 Edge Server 災害復原](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

