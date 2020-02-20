---
title: Lync Server 2013： 設定 public instant messaging 連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4887e419e45f6b6fb165dc7efff407332f3e150a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>設定 Lync Server 2013 中的 public instant messaging 連線

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-08_

如果您的組織想要支援與 AOL 的公用立即訊息 (IM) 連線能力，您將無法使用 Lync Server 部署精靈要求憑證。請改為執行下列程序的步驟。

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>設定 Public Instant Messaging Connectivity

1.  在前端伺服器上，開啟拓撲建置器。展開 Edge 集區，然後以滑鼠右鍵按一下 Edge Server 或 Edge Server 集區。選取 [編輯內容]。

2.  在 [編輯內容] 的 [一般] 下方，選取 [啟用此 Edge 集區的同盟 (連接埠 5061)]。按一下 [確定]。

3.  按一下 [動作]，然後依序選取 [拓撲] 和 [發行]。出現發行拓撲的提示時，按 [下一步]。完成發行時，按一下 [完成]。

4.  在 Edge Server 上，開啟 [Lync Server 部署精靈]。按一下 [安裝或更新 Lync Server 系統]，然後按一下 [安裝或移除 Lync Server 元件]。按一下 [再執行一次]。

5.  在 [安裝 Lync Server 元件] 中按 [下一步]。摘要畫面將顯示所執行的動作。一旦部署完成，按一下 [檢視記錄檔]，檢視出現的記錄檔。按一下 [完成] 即可完成部署。

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>若要為 Edge Server 的外部介面建立憑證要求以支援對 AOL 的公用 IM 連線能力

1.  若有必要的範本可提供給 CA，請在 Edge Server 中使用下列 Windows PowerShell Cmdlet 以要求憑證：
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    使用 Lync Server 的預設憑證名稱是範本的網頁伺服器。 僅指定\<範本名稱\>如果您需要使用不同於預設範本的範本。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的組織想要支援搭配 AOL 的公用 IM 連線，您必須要求要指派給 Access Edge service 的外部邊緣憑證而不是 [憑證] 精靈使用 Windows PowerShell。 這是因為憑證精靈用來要求憑證的 Certificate Authority (CA) 伺服器範本不支援用戶端 EKU 組態。 使用 Windows PowerShell 來建立憑證之前, 的 CA 系統管理員必須建立及部署支援用戶端 EKU 新範本。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

