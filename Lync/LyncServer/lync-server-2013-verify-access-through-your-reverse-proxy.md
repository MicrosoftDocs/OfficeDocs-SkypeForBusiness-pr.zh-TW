---
title: Lync Server 2013：確認透過您的反向 Proxy 進行存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e35e3908f66952b0e631484efa590bcd76fc0456
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976802"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中確認透過您的反向 Proxy 進行存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-29_

使用下列程式來確認您的使用者可以存取反向 proxy 上的資訊。 您可能需要完成防火牆設定和網域名稱系統（DNS）設定，才能使 access 正常運作。

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>驗證您是否可以透過網際網路存取網站

  - 開啟網頁瀏覽器，在**網址**列中輸入 url，讓用戶端用來存取通訊錄檔案及會議的網站，如下所示：
    
      - 針對 [通訊錄服務器]，輸入類似以下的 URL： **https://externalwebfarmFQDN/abs** externalwebfarmFQDN 是託管通訊錄服務之外部 web 服務的外部 FQDN。 使用者應該會收到 HTTP 質詢，因為通訊錄服務器資料夾上的目錄安全性預設會設定為 Windows 驗證。
    
      - 如果是會議，請輸入類似以下的 URL： **https://externalwebfarmFQDN/meet** externalwebfarmFQDN 是主持會議內容之網頁伺服器陣列的外部 FQDN。 此 URL 應該會顯示會議的疑難排解頁面。 或者，確認您的會議簡單 URL 能正常運作。 加入會議的簡單 URL 範例可能是https://meet.contoso.com
    
      - 針對通訊群組展開，請輸入類似以下的 URL： **https://externalwebfarmFQDN/GroupExpansion/service.svc**。 使用者應該會收到 HTTP 質詢，因為通訊群組延伸服務的目錄安全性預設會設定為 Windows 驗證。
    
      - 在 [撥入] 中，輸入類似以下**https://externalwebfarmFQDN/dialin**的簡單 URL，其中 externalwebfarmFQDN 是主持撥入式會議的撥入頁面之網路集群的外部 FQDN。 使用者應該會被導向至撥入頁面。 或者，確認您的簡單 URL 撥入功能正常運作。 撥號的簡單 URL 範例可能是https://dialin.contoso.com
    
      - 若要確認自動探索 URL 是否正常運作， https://lyncdiscover請輸入。 externaldomainFQDN. 瀏覽器應該提示您開啟檔案。 選取 [記事本] 將它開啟。 典型的回應會類似以下所示：
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

