---
title: Lync Server 2013：安裝 Edge Server
description: Lync Server 2013：安裝 Edge Server。
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
ms.openlocfilehash: e699a7f41b0ee554bc85fb2d9a72a2d9a42870cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559579"
---
# <a name="install-edge-servers-for-lync-server-2013"></a>安裝 Lync Server 2013 的 Edge Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

您可以使用 Lync Server 部署嚮導，在 Edge Servers 上安裝 Lync Server 2013。 在每部 Edge Server 上執行 [部署精靈]，可以完成設定 Edge Server 所需的大部分工作。 若要在 Edge Server 上部署 Lync Server 2013，您必須已執行拓撲產生器來定義及發佈 Edge Server 拓撲，並將其匯出至 Edge Server 所提供的媒體。 如需詳細資訊，請參閱 [Lync server 2013 中外部使用者存取的案例](lync-server-2013-scenarios-for-external-user-access.md) ，並 [匯出 lync server 2013 拓撲，並將其複製到 edge 安裝的外部媒體](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。

使用部署嚮導安裝每一部 Edge Server、安裝並指派必要的憑證，以及啟動必要的服務之後，您可以使用在 Lync server 2013 中設定 [外部使用者存取支援的](lync-server-2013-configuring-support-for-external-user-access.md) 資訊，來完成設定，以啟用及設定外部使用者存取，以及 [驗證 lync server 2013 中的 Edge 部署](lync-server-2013-verifying-your-edge-deployment.md) 中的資訊，以驗證安裝程式，包括伺服器及用戶端連線能力。

<div>

## <a name="to-install-an-edge-server"></a>安裝 Edge Server

1.  以本機 Administrators 群組成員的身分或具有相同使用者權限的帳戶，登入您想要安裝 Edge Server 的電腦。

2.  請確認 Edge (Server 上可以使用拓撲產生器建立的拓撲設定檔，然後匯出並複製到外部媒體，例如，存取您複寫拓撲設定檔的 USB 磁片磁碟機，或驗證您複製檔案的來源網路共用的存取權) 。

3.  啟動部署精靈。
    
    <div>
    

    > [!NOTE]  
    > 如果出現訊息告知必須安裝 Microsoft Visual C++ 可轉散發套件，請按一下 <STRONG>[是]</STRONG>。在下一個對話方塊中，您可以接受預設的 <STRONG>[安裝位置]</STRONG>，也可以按一下 <STRONG>[瀏覽]</STRONG> 選取其他位置，然後按一下 <STRONG>[安裝]</STRONG>。在下一個對話方塊中，選取 <STRONG>[我接受授權合約中的條款]</STRONG> 核取方塊，然後按一下 <STRONG>[確定]</STRONG>。

    
    </div>

4.  在部署精靈中按一下 **[安裝或更新 Lync Server 系統]**。

5.  等精靈決定部署狀態後，在 **[步驟 1：安裝本機設定存放區]** 中按一下 **[執行]**，然後執行下列步驟：
    
      - 在 **[設定中央管理存放區的本機複本]** 對話方塊中，按一下 **[從檔案匯入 (建議 Edge Server 使用)]**，前往匯出拓撲設定檔的位置、選取 .zip 檔案、按一下 **[開啟]**，然後按 **[下一步]**。
    
      - 部署精靈會從設定檔讀取設定資訊，並將 XML 設定檔寫入本機電腦。
    
      - **[執行命令]** 程序完成後，按一下 **[完成]**。

6.  在 [部署嚮導] 中，按一下 [ **步驟2：安裝或移除 Lync Server 元件** ]，以安裝在本機電腦上儲存的 XML 設定檔中所指定的 Lync server 2013 edge 元件。

7.  完成安裝後，請使用 [設定 Lync Server 2013 的 Edge 憑證](lync-server-2013-set-up-edge-certificates.md) 中的資訊，以安裝並指派必要的憑證，然後再啟動服務。

</div>

</div>

<span> </span>

</div>

</div>

</div>

