---
title: Lync Server 2013：設定網頁伺服器陣列 Fqdn
description: Lync Server 2013：設定網頁伺服器陣列 Fqdn。
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
ms.openlocfilehash: 8a07faac4d4809ffe10e7ca3699e7441e6dbcb7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566659"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>設定 Lync Server 2013 的 web 伺服器陣列 Fqdn

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-29_

當您在拓撲產生器中定義 Standard Edition server、前端集區、Director 或 Director 集區的設定時，會將 [外部 web 服務] 完整功能變數名稱設定 (FQDN) 。 在駐留在 Standard Edition server 或前端集區中的用戶端登入過程中，設定的 web 服務 Fqdn 是透過帶內布建的方式傳送。 如果您需要新增或變更 [外部 web 服務] URL，請使用拓撲產生器來設定或重新設定 web 服務設定，使用本主題中的程式。

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>設定 web 服務的外部集區 FQDN

1.  啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。

2.  在 [拓撲產生器] 的 [ **Standard Edition 前端**]、[ **Enterprise edition 前端**] 及 [ **director**] 下的主控台樹中，以滑鼠右鍵按一下您需要編輯的集區名稱，然後按一下 [ **編輯**內容]。

3.  在 [ **Web 服務** ] 區段中，新增或編輯 [ **外部 Web 服務 FQDN**]。

4.  檢查並調整 HTTP 和 HTTPS 的 **聆聽埠** 。 預設值將會是：
    
      - **聆聽埠：** HTTP 8080，HTTPS 4443
    
      - **已發佈的埠：** HTTP 80，HTTPS 443
    
    其中， **收聽埠** 是外部 web 服務將設定為接收反向 proxy 之要求的埠，而 **已發佈的埠** 是反向 proxy 外部發佈的埠，而且會在頻帶內布建期間傳遞給用戶端。

5.  當您完成新增和更新時，請按一下 **[確定]** 繼續。

6.  以滑鼠右鍵按一下 [ **Lync Server 2013**]，然後按一下 [ **發佈**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 順利發行完成後，可能會出現連結，通知您有需要採取的其他步驟。 連結（如果已按一下）會開啟受拓撲產生器所進行之變更影響的伺服器清單，該清單會要求您在所列的每個伺服器上重新執行 Lync Server 部署嚮導，以更新新增、移除或變更的元件的設定。

    
    </div>

7.  針對組織中的每個 Standard Edition server、前端集區、Director 或 Director 集區，重複執行這些步驟。

</div>

</div>

<span> </span>

</div>

</div>

</div>

