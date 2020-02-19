---
title: Lync Server 2013： 確認透過您的反向 proxy 進行存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify access through your reverse proxy
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429697(v=OCS.15)
ms:contentKeyID: 48183753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b26afb358a78e18476efbebf7de4c8088e131f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>確認透過您在 Lync Server 2013 中的反向 proxy 進行存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-29_

請使用下列程序，確認您的使用者可以存取反向 Proxy 的資訊。您可能必須先完成防火牆設定與網域名稱系統 (DNS) 設定，存取才能正常運作。

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>若要確認您可以透過網際網路存取網站

  - 開啟網頁瀏覽器，依照下列方式在 **[網址]** 列輸入用戶端用來存取通訊錄檔案與網站以進行會議的 URL：
    
      - Address Book server，輸入與下列類似的 URL: **https://externalwebfarmFQDN/abs** externalwebfarmFQDN 所在主控通訊錄服務的外部 web 服務的外部 FQDN。 使用者應該會收到 HTTP 挑戰，因為 Address Book Server 資料夾的目錄安全性預設是設定為 Windows 驗證。
    
      - 電話撥入會議，輸入與下列類似的 URL: **https://externalwebfarmFQDN/meet** externalwebfarmFQDN 所在裝載會議內容 web 伺服陣列的外部 FQDN。 此 URL 應該會顯示會議的疑難排解網頁。 或者請確認您會議的簡單 URL 是否可正確運作。 可能的會議加入範例簡單 URLhttps://meet.contoso.com
    
      - 通訊群組擴充，輸入與下列類似的 URL: **https://externalwebfarmFQDN/GroupExpansion/service.svc**。 使用者應該會收到 HTTP 挑戰，因為通訊群組擴充服務上的目錄安全性預設是設定為 Windows 驗證。
    
      - 撥號對應表中，輸入與下列類似的簡單 URL **https://externalwebfarmFQDN/dialin** externalwebfarmFQDN 所在的 web 伺服器陣列裝載電話撥入式會議的電話撥入式] 頁面上的外部 FQDN。 使用者應該會被導向至撥入頁面。 或者請確認您會議的簡單 URL 是否可正確運作。 可能的撥號對應表中的範例簡單 URLhttps://dialin.contoso.com
    
      - 若要確認是否運作的自動探索 URL，請輸入https://lyncdiscover。 externaldomainFQDN。 在瀏覽器應提示您開啟檔案。 選取 [記事本] 來開啟它。 典型的回應會類似：
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

