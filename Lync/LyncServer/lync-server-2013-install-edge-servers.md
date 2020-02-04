---
title: Lync Server 2013：安裝 Edge Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22d1961a158ead735ae63d20bb2bd233d6ed5958
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763757"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>安裝 Lync Server 2013 的 Edge Server

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

您可以使用 Lync Server 部署嚮導，在 Edge 伺服器上安裝 Lync Server 2013。 在每個邊緣伺服器上執行部署嚮導，您就可以完成設定 Edge 伺服器所需的大部分工作。 若要在 Edge 伺服器上部署 Lync Server 2013，您必須已執行拓撲建立器，才能定義及發佈 Edge 伺服器拓撲，並將它匯出到從 Edge 伺服器提供的媒體中。 如需詳細資訊，請參閱[Lync server 2013 中的外部使用者存取案例](lync-server-2013-scenarios-for-external-user-access.md)，並[匯出 lync server 2013 拓朴，並將其複製到外部媒體以進行 edge 安裝](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。

使用 [部署嚮導] 安裝每個 Edge 伺服器、安裝並指派所需的憑證，然後啟動所需的服務之後，您就可以使用在[Lync server 2013 中設定外部使用者存取支援](lync-server-2013-configuring-support-for-external-user-access.md)中的資訊來完成設定，以啟用及設定外部使用者存取，以及[驗證 lync server 2013 中的 Edge 部署中](lync-server-2013-verifying-your-edge-deployment.md)的資訊，包括伺服器與用戶端連線。

<div>

## <a name="to-install-an-edge-server"></a>若要安裝邊緣伺服器

1.  登入您想要將 Edge 伺服器安裝為本機管理員群組成員的電腦，或是具有同等使用者權利和許可權的帳戶。

2.  請確定您使用拓撲結構建立器所建立的拓撲設定檔案，然後匯出並複製到外部媒體，這是在 Edge 伺服器上提供的（例如，存取您複寫拓撲設定檔的 USB 磁片磁碟機），或驗證存取您複製檔案的網路共用位置。

3.  啟動 [部署] 嚮導。
    
    <div>
    

    > [!NOTE]  
    > 如果您收到一則訊息，指出您需要安裝 Microsoft Visual c + + 可再發行的資訊，請按一下<STRONG>[是]</STRONG>。 在下一個對話方塊中，您可以接受預設的<STRONG>安裝位置</STRONG>，或按一下<STRONG>[流覽]</STRONG>以選取替換位置，然後按一下 [<STRONG>安裝</STRONG>]。 在下一個對話方塊中，選取 [<STRONG>我接受授權合約中的條款</STRONG>] 核取方塊，然後按一下<STRONG>[確定]</STRONG>。

    
    </div>

4.  在 [部署嚮導] 中，按一下 [**安裝或更新 Lync Server 系統**]。

5.  嚮導決定部署狀態之後，請執行**步驟1。安裝本機配置存放區**，按一下 [**執行**]，然後執行下列動作：
    
      - 在 [**設定中央管理儲存的本機複本**] 對話方塊中，按一下 [從檔案匯**入] （適用于 Edge 伺服器）**，移至匯出拓撲設定檔案的位置，選取 .Zip 檔案，按一下 [**開啟**]，然後按一下 **[下一步]**。
    
      - [部署] 嚮導會從配置檔案中讀取配置資訊，並將 XML 設定檔寫入本機電腦。
    
      - 完成**執行命令**程式後，請按一下 **[完成]**。

6.  在 [部署嚮導] 中，按一下 [**步驟2：設定] 或 [移除 Lync Server 元件**] 來安裝 lync server 2013 edge 元件（儲存在本機電腦上的 XML 設定檔中指定）。

7.  完成安裝後，請使用[設定 Lync Server 2013 的邊緣憑證](lync-server-2013-set-up-edge-certificates.md)中的資訊來安裝並指派所需的憑證，然後再啟動服務。

</div>

</div>

<span> </span>

</div>

</div>

</div>

