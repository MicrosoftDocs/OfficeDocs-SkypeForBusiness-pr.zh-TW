---
title: Lync Server 2013：確認透過您的反向 proxy 進行存取
description: Lync Server 2013：確認透過您的反向 proxy 進行存取。
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
ms.openlocfilehash: 593aac5574f0dcf683351f12a6392f6116480ac5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547119"
---
# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="c3e23-103">在 Lync Server 2013 中驗證是否透過您的反向 proxy 進行存取</span><span class="sxs-lookup"><span data-stu-id="c3e23-103">Verify access through your reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3e23-104">_**主題上次修改日期：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="c3e23-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="c3e23-p101">請使用下列程序，確認您的使用者可以存取反向 Proxy 的資訊。您可能必須先完成防火牆設定與網域名稱系統 (DNS) 設定，存取才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="c3e23-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="c3e23-107">若要確認您可以透過網際網路存取網站</span><span class="sxs-lookup"><span data-stu-id="c3e23-107">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="c3e23-108">開啟網頁瀏覽器，依照下列方式在 **[網址]** 列輸入用戶端用來存取通訊錄檔案與網站以進行會議的 URL：</span><span class="sxs-lookup"><span data-stu-id="c3e23-108">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="c3e23-109">在 [通訊錄服務器] 中，輸入類似下列的 URL： **https://externalwebfarmFQDN/abs** 其中 externalwebfarmFQDN 是主控通訊錄服務之外部 web 服務的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c3e23-109">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="c3e23-110">使用者應該會收到 HTTP 挑戰，因為 Address Book Server 資料夾的目錄安全性預設是設定為 Windows 驗證。</span><span class="sxs-lookup"><span data-stu-id="c3e23-110">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="c3e23-111">若為會議，請輸入類似下列的 URL： **https://externalwebfarmFQDN/meet** 其中 externalwebfarmFQDN 是主控會議內容之網頁伺服器陣列的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c3e23-111">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="c3e23-112">此 URL 應該會顯示會議的疑難排解網頁。</span><span class="sxs-lookup"><span data-stu-id="c3e23-112">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="c3e23-113">或者請確認您會議的簡單 URL 是否可正確運作。</span><span class="sxs-lookup"><span data-stu-id="c3e23-113">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="c3e23-114">會議加入的簡單 URL 範例可能是 https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3e23-114">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="c3e23-115">若為通訊群組擴充，請輸入類似下列的 URL： **https://externalwebfarmFQDN/GroupExpansion/service.svc** 。</span><span class="sxs-lookup"><span data-stu-id="c3e23-115">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="c3e23-116">使用者應該會收到 HTTP 挑戰，因為通訊群組擴充服務上的目錄安全性預設是設定為 Windows 驗證。</span><span class="sxs-lookup"><span data-stu-id="c3e23-116">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="c3e23-117">若為撥入，請輸入類似下列的簡單 URL， **https://externalwebfarmFQDN/dialin** externalwebfarmFQDN 是主控電話撥入式會議撥入頁面之網頁伺服器陣列的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c3e23-117">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="c3e23-118">使用者應該會被導向至撥入頁面。</span><span class="sxs-lookup"><span data-stu-id="c3e23-118">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="c3e23-119">或者請確認您會議的簡單 URL 是否可正確運作。</span><span class="sxs-lookup"><span data-stu-id="c3e23-119">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="c3e23-120">例如，撥號的簡易 URL 可能是 https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c3e23-120">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="c3e23-121">若要確認自動探索 URL 是否正常運作，請輸入 https://lyncdiscover 。</span><span class="sxs-lookup"><span data-stu-id="c3e23-121">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="c3e23-122">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="c3e23-122">externaldomainFQDN.</span></span> <span data-ttu-id="c3e23-123">瀏覽器應該提示您開啟檔。</span><span class="sxs-lookup"><span data-stu-id="c3e23-123">The browser should prompt you to open a file.</span></span> <span data-ttu-id="c3e23-124">選取 [記事本] 以開啟它。</span><span class="sxs-lookup"><span data-stu-id="c3e23-124">Select Notepad to open it.</span></span> <span data-ttu-id="c3e23-125">一般回應如下：</span><span class="sxs-lookup"><span data-stu-id="c3e23-125">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

