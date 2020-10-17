---
title: Lync Server 2013：確認透過您的反向 proxy 進行存取
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
ms.openlocfilehash: 8b8c8e4c92f0cdb9eb1b7070735882b43a308080
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518710"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a>在 Lync Server 2013 中驗證是否透過您的反向 proxy 進行存取

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-29_

請使用下列程序，確認您的使用者可以存取反向 Proxy 的資訊。您可能必須先完成防火牆設定與網域名稱系統 (DNS) 設定，存取才能正常運作。

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a>若要確認您可以透過網際網路存取網站

  - 開啟網頁瀏覽器，依照下列方式在 **[網址]** 列輸入用戶端用來存取通訊錄檔案與網站以進行會議的 URL：
    
      - 在 [通訊錄服務器] 中，輸入類似下列的 URL： **https://externalwebfarmFQDN/abs** 其中 externalwebfarmFQDN 是主控通訊錄服務之外部 web 服務的外部 FQDN。 使用者應該會收到 HTTP 挑戰，因為 Address Book Server 資料夾的目錄安全性預設是設定為 Windows 驗證。
    
      - 若為會議，請輸入類似下列的 URL： **https://externalwebfarmFQDN/meet** 其中 externalwebfarmFQDN 是主控會議內容之網頁伺服器陣列的外部 FQDN。 此 URL 應該會顯示會議的疑難排解網頁。 或者請確認您會議的簡單 URL 是否可正確運作。 會議加入的簡單 URL 範例可能是 https://meet.contoso.com
    
      - 若為通訊群組擴充，請輸入類似下列的 URL： **https://externalwebfarmFQDN/GroupExpansion/service.svc** 。 使用者應該會收到 HTTP 挑戰，因為通訊群組擴充服務上的目錄安全性預設是設定為 Windows 驗證。
    
      - 若為撥入，請輸入類似下列的簡單 URL， **https://externalwebfarmFQDN/dialin** externalwebfarmFQDN 是主控電話撥入式會議撥入頁面之網頁伺服器陣列的外部 FQDN。 使用者應該會被導向至撥入頁面。 或者請確認您會議的簡單 URL 是否可正確運作。 例如，撥號的簡易 URL 可能是 https://dialin.contoso.com
    
      - 若要確認自動探索 URL 是否正常運作，請輸入 https://lyncdiscover 。 externaldomainFQDN. 瀏覽器應該提示您開啟檔。 選取 [記事本] 以開啟它。 一般回應如下：
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

