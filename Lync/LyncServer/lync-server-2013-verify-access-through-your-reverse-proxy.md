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
ms.openlocfilehash: 4dec8a6d5339af93a7e8c0f63aca5f5d3f990583
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="f5afb-102">確認透過您在 Lync Server 2013 中的反向 proxy 進行存取</span><span class="sxs-lookup"><span data-stu-id="f5afb-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5afb-103">_**上次修改主題：** 2013年-03-29_</span><span class="sxs-lookup"><span data-stu-id="f5afb-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="f5afb-p101">請使用下列程序，確認您的使用者可以存取反向 Proxy 的資訊。您可能必須先完成防火牆設定與網域名稱系統 (DNS) 設定，存取才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="f5afb-p101">Use the following procedure to verify that your users can access information on the reverse proxy. You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="f5afb-106">若要確認您可以透過網際網路存取網站</span><span class="sxs-lookup"><span data-stu-id="f5afb-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="f5afb-107">開啟網頁瀏覽器，依照下列方式在 **[網址]** 列輸入用戶端用來存取通訊錄檔案與網站以進行會議的 URL：</span><span class="sxs-lookup"><span data-stu-id="f5afb-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="f5afb-108">Address Book server，輸入與下列類似的 URL: **https://externalwebfarmFQDN/abs** externalwebfarmFQDN 所在主控通訊錄服務的外部 web 服務的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f5afb-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="f5afb-109">使用者應該會收到 HTTP 挑戰，因為 Address Book Server 資料夾的目錄安全性預設是設定為 Windows 驗證。</span><span class="sxs-lookup"><span data-stu-id="f5afb-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="f5afb-110">電話撥入會議，輸入與下列類似的 URL: **https://externalwebfarmFQDN/meet** externalwebfarmFQDN 所在裝載會議內容 web 伺服陣列的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f5afb-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="f5afb-111">此 URL 應該會顯示會議的疑難排解網頁。</span><span class="sxs-lookup"><span data-stu-id="f5afb-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="f5afb-112">或者請確認您會議的簡單 URL 是否可正確運作。</span><span class="sxs-lookup"><span data-stu-id="f5afb-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="f5afb-113">可能的會議加入範例簡單 URLhttps://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5afb-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="f5afb-114">通訊群組擴充，輸入與下列類似的 URL: **https://externalwebfarmFQDN/GroupExpansion/service.svc**。</span><span class="sxs-lookup"><span data-stu-id="f5afb-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="f5afb-115">使用者應該會收到 HTTP 挑戰，因為通訊群組擴充服務上的目錄安全性預設是設定為 Windows 驗證。</span><span class="sxs-lookup"><span data-stu-id="f5afb-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="f5afb-116">撥號對應表中，輸入與下列類似的簡單 URL **https://externalwebfarmFQDN/dialin** externalwebfarmFQDN 所在的 web 伺服器陣列裝載電話撥入式會議的電話撥入式] 頁面上的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f5afb-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="f5afb-117">使用者應該會被導向至撥入頁面。</span><span class="sxs-lookup"><span data-stu-id="f5afb-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="f5afb-118">或者請確認您會議的簡單 URL 是否可正確運作。</span><span class="sxs-lookup"><span data-stu-id="f5afb-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="f5afb-119">可能的撥號對應表中的範例簡單 URLhttps://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="f5afb-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="f5afb-120">若要確認是否運作的自動探索 URL，請輸入https://lyncdiscover。</span><span class="sxs-lookup"><span data-stu-id="f5afb-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="f5afb-121">externaldomainFQDN。</span><span class="sxs-lookup"><span data-stu-id="f5afb-121">externaldomainFQDN.</span></span> <span data-ttu-id="f5afb-122">在瀏覽器應提示您開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="f5afb-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="f5afb-123">選取 [記事本] 來開啟它。</span><span class="sxs-lookup"><span data-stu-id="f5afb-123">Select Notepad to open it.</span></span> <span data-ttu-id="f5afb-124">典型的回應會類似：</span><span class="sxs-lookup"><span data-stu-id="f5afb-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

