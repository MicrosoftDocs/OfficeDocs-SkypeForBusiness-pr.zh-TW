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

# <a name="verify-access-through-your-reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="39b79-102">在 Lync Server 2013 中確認透過您的反向 Proxy 進行存取</span><span class="sxs-lookup"><span data-stu-id="39b79-102">Verify access through your reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39b79-103">_**主題上次修改日期：** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="39b79-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="39b79-104">使用下列程式來確認您的使用者可以存取反向 proxy 上的資訊。</span><span class="sxs-lookup"><span data-stu-id="39b79-104">Use the following procedure to verify that your users can access information on the reverse proxy.</span></span> <span data-ttu-id="39b79-105">您可能需要完成防火牆設定和網域名稱系統（DNS）設定，才能使 access 正常運作。</span><span class="sxs-lookup"><span data-stu-id="39b79-105">You might need to complete the firewall configuration and Domain Name System (DNS) configuration before access will work correctly.</span></span>

<div>

## <a name="to-verify-that-you-can-access-the-website-through-the-internet"></a><span data-ttu-id="39b79-106">驗證您是否可以透過網際網路存取網站</span><span class="sxs-lookup"><span data-stu-id="39b79-106">To verify that you can access the website through the Internet</span></span>

  - <span data-ttu-id="39b79-107">開啟網頁瀏覽器，在**網址**列中輸入 url，讓用戶端用來存取通訊錄檔案及會議的網站，如下所示：</span><span class="sxs-lookup"><span data-stu-id="39b79-107">Open a web browser, type the URLs in the **Address** bar that clients use to access the Address Book files and the website for conferencing as follows:</span></span>
    
      - <span data-ttu-id="39b79-108">針對 [通訊錄服務器]，輸入類似以下的 URL： **https://externalwebfarmFQDN/abs** externalwebfarmFQDN 是託管通訊錄服務之外部 web 服務的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="39b79-108">For Address Book Server, type a URL similar to the following: **https://externalwebfarmFQDN/abs** where externalwebfarmFQDN is the external FQDN of the external web services that hosts Address Book services.</span></span> <span data-ttu-id="39b79-109">使用者應該會收到 HTTP 質詢，因為通訊錄服務器資料夾上的目錄安全性預設會設定為 Windows 驗證。</span><span class="sxs-lookup"><span data-stu-id="39b79-109">The user should receive an HTTP challenge, because directory security on the Address Book Server folder is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="39b79-110">如果是會議，請輸入類似以下的 URL： **https://externalwebfarmFQDN/meet** externalwebfarmFQDN 是主持會議內容之網頁伺服器陣列的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="39b79-110">For conferencing, type a URL similar to the following: **https://externalwebfarmFQDN/meet** where externalwebfarmFQDN is the external FQDN of the web farm that hosts meeting content.</span></span> <span data-ttu-id="39b79-111">此 URL 應該會顯示會議的疑難排解頁面。</span><span class="sxs-lookup"><span data-stu-id="39b79-111">This URL should display the troubleshooting page for conferencing.</span></span> <span data-ttu-id="39b79-112">或者，確認您的會議簡單 URL 能正常運作。</span><span class="sxs-lookup"><span data-stu-id="39b79-112">Alternatively, confirm that your Simple URL for conferencing functions correctly.</span></span> <span data-ttu-id="39b79-113">加入會議的簡單 URL 範例可能是https://meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b79-113">An example Simple URL for the conference join might be https://meet.contoso.com</span></span>
    
      - <span data-ttu-id="39b79-114">針對通訊群組展開，請輸入類似以下的 URL： **https://externalwebfarmFQDN/GroupExpansion/service.svc**。</span><span class="sxs-lookup"><span data-stu-id="39b79-114">For distribution group expansion, type a URL similar to the following: **https://externalwebfarmFQDN/GroupExpansion/service.svc**.</span></span> <span data-ttu-id="39b79-115">使用者應該會收到 HTTP 質詢，因為通訊群組延伸服務的目錄安全性預設會設定為 Windows 驗證。</span><span class="sxs-lookup"><span data-stu-id="39b79-115">The user should receive an HTTP challenge, because directory security on the distribution group expansion service is configured to Windows authentication by default.</span></span>
    
      - <span data-ttu-id="39b79-116">在 [撥入] 中，輸入類似以下**https://externalwebfarmFQDN/dialin**的簡單 URL，其中 externalwebfarmFQDN 是主持撥入式會議的撥入頁面之網路集群的外部 FQDN。</span><span class="sxs-lookup"><span data-stu-id="39b79-116">For dial-in, type the simple URL similar to the following **https://externalwebfarmFQDN/dialin** where externalwebfarmFQDN is the external FQDN of the web farm that hosts the dial-in page for dial-in conferencing.</span></span> <span data-ttu-id="39b79-117">使用者應該會被導向至撥入頁面。</span><span class="sxs-lookup"><span data-stu-id="39b79-117">The user should be directed to the dial-in page.</span></span> <span data-ttu-id="39b79-118">或者，確認您的簡單 URL 撥入功能正常運作。</span><span class="sxs-lookup"><span data-stu-id="39b79-118">Alternatively, confirm that your Simple URL dial-in functions correctly.</span></span> <span data-ttu-id="39b79-119">撥號的簡單 URL 範例可能是https://dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="39b79-119">An example Simple URL for dial-in might be https://dialin.contoso.com</span></span>
    
      - <span data-ttu-id="39b79-120">若要確認自動探索 URL 是否正常運作， https://lyncdiscover請輸入。</span><span class="sxs-lookup"><span data-stu-id="39b79-120">To confirm that the autodiscover URL is working, type https://lyncdiscover.</span></span> <span data-ttu-id="39b79-121">externaldomainFQDN.</span><span class="sxs-lookup"><span data-stu-id="39b79-121">externaldomainFQDN.</span></span> <span data-ttu-id="39b79-122">瀏覽器應該提示您開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="39b79-122">The browser should prompt you to open a file.</span></span> <span data-ttu-id="39b79-123">選取 [記事本] 將它開啟。</span><span class="sxs-lookup"><span data-stu-id="39b79-123">Select Notepad to open it.</span></span> <span data-ttu-id="39b79-124">典型的回應會類似以下所示：</span><span class="sxs-lookup"><span data-stu-id="39b79-124">A typical response would be similar to:</span></span>
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

</div>

</div>

<span> </span>

</div>

</div>

</div>

