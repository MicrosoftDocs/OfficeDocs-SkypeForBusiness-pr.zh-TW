---
title: Lync Server 2013：設定 Web 伺服陣列 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>針對 Lync Server 2013 設定 Web 伺服陣列 FQDN

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-29_

當您在拓撲建立器中定義標準版 server、前端池、控制器或控制器池的設定時，請設定外部 web 服務完整功能變數名稱（FQDN）。 在駐留在標準版 server 或 [前端] 池中的用戶端登入程式期間，已設定的 web 服務 Fqdn 是透過以內提供的方式傳送。 如果您需要新增或變更 [外部 web 服務] URL，您可以使用 [拓撲建立器] 來設定或重新配置 web 服務配置（使用本主題中的程式）。

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>針對 web 服務設定外部池 FQDN

1.  啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。

2.  在拓撲建立器中，在 [**標準版的前端**]、[**企業版] 前端**和 [**控制器**] 底下的 [主控台] 樹狀結構中，以滑鼠右鍵按一下您要編輯的池名稱，然後按一下 [**編輯屬性**]。

3.  在 [ **Web 服務**] 區段中，新增或編輯**外部 Web 服務 FQDN**。

4.  同時查看和調整 HTTP 和 HTTPS 的**偵聽埠**。 預設值將會是：
    
      - **偵聽埠：** HTTP 8080，HTTPS 4443
    
      - **已發佈的埠：** HTTP 80，HTTPS 443
    
    在**偵聽埠**是要將外部 web 服務設定為從反向 proxy 接收要求的埠，而**已發佈的埠**是由反向 proxy 在外部發佈的埠，且會在頻帶內設定中傳遞給用戶端。

5.  當您完成新增和更新時，請按一下 **[確定]** 以繼續進行。

6.  以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [**發佈**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 發佈順利完成後，可能會出現連結，通知您有需要採取的其他步驟。 如果按一下該連結，則會開啟拓撲建立器所做的變更所影響的伺服器清單，這會要求您在每個列出的伺服器上重新執行 Lync Server 部署嚮導，以更新已新增、已移除或變更的元件的配置。

    
    </div>

7.  針對組織中的每個標準版 server、[前端] 池、[主管] 或 [控制器] 池，重複這些步驟。

</div>

</div>

<span> </span>

</div>

</div>

</div>

