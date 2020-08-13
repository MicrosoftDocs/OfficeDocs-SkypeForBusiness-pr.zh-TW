---
title: 容錯回復 Lync Server 同盟或 XMPP 同盟使用的 Edge 集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3531e50efec5d981249e892c692a20095bef9eff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中回復用於 Lync Server 同盟或 XMPP 同盟的 Edge 集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

在用來主控同盟的失敗 Edge 集區回到線上後，請使用此程式來容錯回復 Lync Server 同盟路由和/或 XMPP 同盟路由，以再次使用此還原的 Edge 集區。

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>將同盟回復至還原的 Edge 集區失敗

1.  在現在可以使用的 Edge 集區上，啟動 Edge Services。

2.  如果您想要容錯回復 Lync Server 同盟路由以使用還原的 Edge Server，請執行下列操作：
    
      - 在前端伺服器上，開啟拓撲產生器。展開 **[Edge 集區]**，然後在目前設定用於同盟的 Edge Server 或 Edge Server 集區上按一下滑鼠右鍵。選取 **[編輯內容]**。
    
      - 在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]****。按一下 [確定]****。
    
      - 展開 [ **Edge**集區]，然後以滑鼠右鍵按一下原始 Edge Server 或 Edge server 集區，以供同盟使用。 選取 [編輯內容]****。
    
      - 在 [編輯內容]**** 中，選取 [一般]**** 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。按一下 **[確定]**。
    
      - 按一下 **[動作]**，依序選取 **[拓撲]** 和 **[發行]**。在 **[發行拓撲]** 出現提示時，按 **[下一步]**。發行完成時，按一下 **[完成]**。
    
      - 在 Edge Server 上開啟 [Lync Server 部署精靈]。依序按一下 **[安裝或更新 Lync Server 系統]**、**[安裝或移除 Lync Server 元件]**、**[再執行一次]**。
    
      - 在 [安裝 Lync Server 元件] 中，按 **[下一步]**。摘要畫面會隨著動作的執行顯示各個動作。部署完成後，按一下 **[檢視記錄檔]** 檢視可用的記錄檔。按一下 **[完成]** 完成部署。

3.  如果您想要容錯回復 XMPP 同盟路由以使用還原的 Edge Server，請執行下列操作：
    
      - 執行下列 Cmdlet，將 XMPP 同盟路由 repoint 至 Edge 集區，該集區現在會主控 XMPP 同盟 (在此範例中，EdgeServer1) ：
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        在此範例中，Site1 是包含 Edge 集區的網站，它現在會主控 XMPP 同盟路由，而且 EdgeServer1.contoso.com 是該集區中 Edge Server 的 FQDN。
    
      - 如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。
        
            _xmpp-server._tcp.contoso.com
    
      - 在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。
    
      - 確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。

4.  如果前端集區仍在包含失敗且已還原之 Edge 集區的網站中執行，您應該更新這些前端集區上的 Web 會議服務和 A/V 會議服務，以再次使用本機網站上的 Edge 集區。 如需詳細資訊，請參閱 [變更與 Lync Server 2013 中的前端集區相關聯的 Edge 集](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)區。

5.  如果與失敗 Edge 集區位於相同網站的前端集區也失敗，您現在可以使用 Invoke–CsPoolFailback 來容錯回前端集區。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中容錯移轉用於 Lync Server 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[在 Lync Server 2013 中容錯移轉用於 XMPP 同盟的 Edge 集區](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Lync Server 2013 中的 Edge Server 災難性修復](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

