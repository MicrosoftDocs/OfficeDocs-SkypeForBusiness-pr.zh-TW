---
title: Lync Server 2013：設定 Public Instant Messaging Connectivity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980455"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中設定 Public Instant Messaging Connectivity

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

如果您的組織想要支援與 AOL 的公用立即訊息（IM）連線，您就無法使用 Lync Server 部署嚮導來要求認證。 請改為執行下列程式中的步驟。

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>設定公用立即訊息連線能力

1.  在前端伺服器上，開啟 [拓撲建立器]。 展開 [邊緣池]，然後以滑鼠右鍵按一下 Edge 伺服器或 Edge 伺服器池。 選取 [編輯屬性]。

2.  在 [編輯屬性] 底下的 [一般] 底下，選取 [針對此 Edge 池啟用同盟（埠5061）]。 按一下 [確定]。

3.  按一下 [動作]，選取 [拓撲]，選取 [發佈]。 發佈拓撲時出現提示時，請按 [下一步]。 發佈完成後，請按一下 [完成]。

4.  在邊緣伺服器上，開啟 Lync Server 部署嚮導。 按一下 [安裝或更新 Lync Server 系統]，然後按一下 [設定] 或 [移除 Lync Server 元件]。 再次按一下 [執行]。

5.  在安裝程式 Lync Server 元件上，按一下 [下一步]。 [摘要] 畫面會在執行時顯示動作。 完成部署之後，按一下 [查看記錄] 以查看可用的記錄檔。 按一下 [完成] 以完成部署。

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>建立邊緣伺服器外部介面的憑證要求，以支援與 AOL 的公用 IM 連線

1.  當 CA 提供所需的範本時，請從 Edge 伺服器使用下列 Windows PowerShell Cmdlet，以要求憑證
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Lync Server 所用之範本的預設憑證名是 Web 服務器。 如果您需要\<使用不同\>于預設範本的範本，請只指定範本名稱。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的組織想要支援與 AOL 的公用 IM 連線，您必須使用 Windows PowerShell，而不是憑證嚮導，以要求將憑證指派給存取邊緣服務的外部邊緣。 這是因為證書嚮導用來要求憑證的憑證授權單位（CA） Web 服務器範本不支援用戶端 EKU 配置。 在使用 Windows PowerShell 建立憑證前，CA 管理員必須建立並部署支援用戶端 EKU 的新範本。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

