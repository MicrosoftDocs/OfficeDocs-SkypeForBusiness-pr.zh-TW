---
title: Lync Server 2013：與 Exchange Server 2013 整合的必要條件
description: Lync Server 2013：與 Exchange Server 2013 整合的必要條件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5872fe3ec546997cd0633383fdda7e0549bec83f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579849"
---
# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="a51f3-103">整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的必要條件</span><span class="sxs-lookup"><span data-stu-id="a51f3-103">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a51f3-104">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="a51f3-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="a51f3-105">您必須先確定已完成所有必要步驟，才能整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a51f3-105">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="a51f3-106">如您所料，在 Exchange 2013 和 Lync Server 2013 完整安裝及執行之前，不會發生整合。</span><span class="sxs-lookup"><span data-stu-id="a51f3-106">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="a51f3-107">如需安裝 Exchange 的詳細資訊，請參閱 Exchange 2013 規劃和部署檔，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539) 。</span><span class="sxs-lookup"><span data-stu-id="a51f3-107">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="a51f3-108">如需安裝 Lync Server 2013 的詳細資訊，請參閱規劃和部署檔，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806) 。</span><span class="sxs-lookup"><span data-stu-id="a51f3-108">For details about installing Lync Server 2013, see the planning and deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="a51f3-109">在執行伺服器並執行後，您必須將伺服器對伺服器驗證憑證指派給 Lync Server 2013 和 Exchange 2013;這些憑證可讓 Lync Server 和 Exchange 交換資訊，並彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="a51f3-109">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="a51f3-110">當您安裝 Exchange 2013 時，會為您建立具有名稱為 Microsoft Exchange Server 驗證憑證的自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="a51f3-110">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="a51f3-111">此憑證可以在本機電腦憑證存放區中找到，以供 Exchange 2013 上的伺服器對伺服器驗證使用。</span><span class="sxs-lookup"><span data-stu-id="a51f3-111">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="a51f3-112">如需在 Exchange 2013 中指派憑證的詳細資訊，請參閱的「設定郵件流程和用戶端存取」 [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540) 。</span><span class="sxs-lookup"><span data-stu-id="a51f3-112">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="a51f3-113">對於 Lync Server 2013，您可以使用現有的 Lync Server 憑證作為伺服器對伺服器驗證憑證;例如，您的預設憑證也可以當做 OAuthTokenIssuer 憑證使用。</span><span class="sxs-lookup"><span data-stu-id="a51f3-113">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="a51f3-114">Lync Server 2013 可讓您使用任何網頁伺服器憑證作為伺服器對伺服器驗證的憑證，但前提是：</span><span class="sxs-lookup"><span data-stu-id="a51f3-114">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="a51f3-115">憑證包含 [主旨] 欄位中的 SIP 網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="a51f3-115">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="a51f3-116">在所有前端伺服器上，相同的憑證會設定為 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="a51f3-116">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="a51f3-117">憑證的長度至少為2048位。</span><span class="sxs-lookup"><span data-stu-id="a51f3-117">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="a51f3-118">如需 Microsoft Lync Server 2013 之伺服器對伺服器驗證憑證的詳細資訊，請參閱 [將伺服器對伺服器驗證憑證指派給 Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="a51f3-118">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="a51f3-119">在指派憑證之後，您必須在 Exchange 2013 上設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="a51f3-119">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="a51f3-120">在 Exchange 2013 中，自動探索服務會設定使用者設定檔，並在使用者登入系統時，提供 Exchange 服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="a51f3-120">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="a51f3-121">使用者會以他們的電子郵件地址和密碼呈現自動探索服務。反過來，服務也會為使用者提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="a51f3-121">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="a51f3-122">Exchange 2013 的內部及外部連線的連線資訊。</span><span class="sxs-lookup"><span data-stu-id="a51f3-122">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="a51f3-123">使用者的信箱伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="a51f3-123">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="a51f3-124">URLs Outlook 功能（例如空閒/忙碌資訊、整合通訊與離線通訊錄）。</span><span class="sxs-lookup"><span data-stu-id="a51f3-124">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="a51f3-125">Outlook Anywhere 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="a51f3-125">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="a51f3-126">您必須先設定自動探索服務，才能整合 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="a51f3-126">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="a51f3-127">您可以從 Exchange 管理命令介面執行下列命令，並檢查 AutoDiscoverServiceInternalUri 屬性的值，以確認是否已設定自動探索服務：</span><span class="sxs-lookup"><span data-stu-id="a51f3-127">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="a51f3-128">如果此值為空白，您必須將 URI 指派給自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="a51f3-128">If this value is blank, you must assign a URI to the autodiscover service.</span></span> <span data-ttu-id="a51f3-129">通常此 URI 如下所示：</span><span class="sxs-lookup"><span data-stu-id="a51f3-129">Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="a51f3-130">您可以執行類似如下的命令來指派自動探索 URI：</span><span class="sxs-lookup"><span data-stu-id="a51f3-130">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="a51f3-131">如需自動探索服務的詳細資訊，請參閱中的「瞭解自動探索服務」 [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542) 。</span><span class="sxs-lookup"><span data-stu-id="a51f3-131">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="a51f3-132">設定自動探索服務之後，您必須修改 Lync Server OAuth 的設定）;這可確保 Lync Server 知道哪裡可以找到自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="a51f3-132">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="a51f3-133">若要在 Lync Server 2013 中修改 OAuth 設定設定，請在 Lync Server 管理命令介面內執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="a51f3-133">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="a51f3-134">當您執行此命令時，請確定您指定的是在 Exchange 伺服器上執行之自動探索服務的 URI，而且您使用 **自動探索。 svc** 指向服務位置，而不是 **autodiscover.xml** (指向服務位置) 所使用的 XML 檔案：</span><span class="sxs-lookup"><span data-stu-id="a51f3-134">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="a51f3-135">以上命令中的 Identity 參數是選用的;這是因為 Lync Server 只允許您擁有單一、全域的 OAuth 配置設定集合。</span><span class="sxs-lookup"><span data-stu-id="a51f3-135">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="a51f3-136">除此之外，也表示您可以使用這個稍微簡單的命令來設定自動探索 URL：</span><span class="sxs-lookup"><span data-stu-id="a51f3-136">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="a51f3-137">Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl " https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc "</span><span class="sxs-lookup"><span data-stu-id="a51f3-137">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="a51f3-138">如果您不熟悉此技術，OAuth 是許多主要網站所使用的標準授權通訊協定。</span><span class="sxs-lookup"><span data-stu-id="a51f3-138">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites.</span></span> <span data-ttu-id="a51f3-139">使用 OAuth 時，使用者認證和密碼不會從一部電腦傳遞到另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="a51f3-139">With OAuth, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="a51f3-140">驗證及授權是基於安全性權杖的交換，這些權杖會授與一段特定時間內一組特定資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="a51f3-140">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="a51f3-141">除了設定自動探索服務之外，您還必須為指向 Exchange 伺服器的服務建立 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="a51f3-141">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="a51f3-142">例如，如果您的自動探索服務位於 autodiscover.litwareinc.com，您將需要為 autodiscover.litwareinc.com 建立 DNS 記錄，以便解析為 Exchange server (的完整功能變數名稱，例如，atl-exchange-001.litwareinc.com) 。</span><span class="sxs-lookup"><span data-stu-id="a51f3-142">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

