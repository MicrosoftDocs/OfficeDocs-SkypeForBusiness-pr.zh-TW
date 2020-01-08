---
title: Lync Server 2013：在伺服器上啟動服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c0c14aea9966e61703e85dd2aff8a2e448d5eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>針對 Lync Server 2013 在伺服器上啟動服務

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-09-03_

若要成功完成此程式，您應該以 RTCUniversalServerAdmins 群組成員的使用者身分登入，或是委派正確的許可權。 如需委派許可權的詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)主題。

在伺服器上安裝本機配置存放區之後，請安裝 Lync Server 2013 元件，並在前端伺服器或前端伺服器上設定憑證，您必須在伺服器上啟動 Lync Server 2013 服務。 使用下列程式在您部署中的每個前端伺服器上啟動服務。

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>在標準版或前端伺服器上啟動服務

1.  在 Lync Server 部署嚮導中，在 [ **Lync server 2013** ] 頁面上，按一下 [**步驟4：啟動服務**] 旁的 [**執行**]。

2.  在 [**啟動服務**] 頁面上，按一下 **[下一步]** ，即可在伺服器上啟動 Lync Server Services。

3.  在 [**執行命令**] 頁面上，已成功啟動所有服務之後，按一下 **[完成]**。
    
    <div>
    

    > [!IMPORTANT]  
    > 在伺服器上啟動服務的命令是一種最佳的方式，可報表服務已開始進行。 它可能不會反映服務的實際狀態。 我們建議您立即使用 [步驟<STRONG>服務狀態] （選用）</STRONG>來開啟 Microsoft 管理主控台（MMC <STRONG>），並</STRONG>確認服務已順利啟動。 如果有任何 Lync Server 服務尚未啟動，您可以在 MMC 中以滑鼠右鍵按一下該服務，然後按一下 [<STRONG>啟動</STRONG>]。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

