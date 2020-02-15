---
title: Lync Server 2013： 設定 web 伺服陣列 Fqdn
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
ms.openlocfilehash: fedaf9fdc48e067b20a956e8945e43469b967011
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a>設定 web 伺服陣列 Fqdn 的 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-29_

當您定義 Standard Edition server 的設定時，前端集區、 Director 或 Director 集區拓撲產生器] 中設定外部 web 服務完整的網域名稱 (FQDN)。 在登入用戶端的程序期間位於 [Standard Edition server 或前端集區，設定的 web 服務 Fqdn 傳送透過頻內佈建。 如果您需要新增或變更外部 web 服務 URL，您可以使用拓撲產生器來設定或重新設定程序使用本主題中的 web 服務組態。

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a>若要設定 web 服務的外部集區 FQDN

1.  啟動拓撲產生器： 按一下 [**開始]**、 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 拓撲產生器]**。

2.  在拓撲產生器，在主控台樹狀目錄中，在**Standard Edition 前端**]、 [ **Enterprise Edition 前端**] 及 [ **Director**，以滑鼠右鍵按一下您要編輯的集區名稱，然後按一下 [**編輯內容]**。

3.  在 [ **Web 服務**] 區段中，新增或編輯**外部 web 服務 FQDN**。

4.  檢閱並調整**聆聽連接埠**的 HTTP 和 HTTPS。 預設值會是：
    
      - **聆聽連接埠：** HTTP 8080、 HTTPS 4443
    
      - **發行的連接埠：** HTTP 80、 HTTPS 443
    
    **聆聽連接埠**所在的外部 web 服務將會設定為接收來自反向 proxy 要求和**發行的連接埠**是連接埠的連接埠都已由反向 proxy 對外發行且頻內佈建期間傳達給用戶端。

5.  當您完成新增和更新時，請按一下 **[確定]** 繼續。

6.  **Lync Server 2013**中，以滑鼠右鍵按一下，然後按一下 [**發佈**]。
    
    <div>
    

    > [!IMPORTANT]  
    > 發佈成功完成之後，連結可能會出現，通知您有其他需要採取的步驟。 [] 連結，如果按下，會開啟在拓撲產生器中，會要求您重新執行更新適用於新增、 移除或變更元件設定每個列出的伺服器上的 [Lync Server 部署精靈中所做的變更所影響的伺服器清單。

    
    </div>

7.  針對每個 Standard Edition 伺服器，前端集區，重複這些步驟 Director 集區在組織中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

