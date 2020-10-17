---
title: Lync Server 2013：在伺服器上啟動服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d276dfdedacdcb00b4cc19a486fea1103c0bc8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532960"
---
# <a name="start-services-on-servers-for-lync-server-2013"></a>在 Lync Server 2013 的伺服器上啟動服務

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-03_

若要順利完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入，或是委派正確的許可權。 如需委派許可權的詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)主題。

在伺服器上安裝本機設定存放區之後，請安裝 Lync Server 2013 元件，並在前端伺服器或前端伺服器上設定憑證，您必須在伺服器上啟動 Lync Server 2013 服務。 使用下列程式可在部署中的每一部前端伺服器上啟動服務。

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>在 Standard Edition 或前端伺服器上啟動服務

1.  在 [Lync Server 部署嚮導] 的 [ **Lync server 2013** ] 頁面上，按一下 [執行**步驟4：啟動服務**] 旁邊的 [**執行**]。

2.  在 [ **啟動服務** ] 頁面上，按一下 **[下一步]** 以啟動伺服器上的 Lync Server 服務。

3.  在 **[執行命令]** 頁面上順利啟動所有服務之後，按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 在伺服器上啟動服務的命令是報告事實上已啟動服務的最佳方法。 它可能不會反映服務的實際狀態。 建議您使用<STRONG>「</STRONG>逐步<STRONG>服務狀態 (選用) </STRONG>來開啟 MICROSOFT Management Console (MMC) ，並確認已順利啟動服務。 如果尚未啟動任何 Lync Server 服務，您可以在 MMC 中以滑鼠右鍵按一下該服務，然後按一下 [ <STRONG>啟動</STRONG>]。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

