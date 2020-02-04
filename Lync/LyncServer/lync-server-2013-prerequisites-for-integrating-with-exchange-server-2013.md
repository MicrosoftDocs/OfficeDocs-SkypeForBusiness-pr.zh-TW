---
title: Lync Server 2013：與 Exchange Server 2013 整合的先決條件
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
ms.openlocfilehash: 1a381f765c9c91e9c5e218d66320d542a11bf878
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="5d9be-102">整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013 的先決條件</span><span class="sxs-lookup"><span data-stu-id="5d9be-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d9be-103">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="5d9be-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="5d9be-104">在您整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 之前，您必須先確定已完成所有必備步驟。</span><span class="sxs-lookup"><span data-stu-id="5d9be-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="5d9be-105">正如您預期的，在 Exchange 2013 和 Lync Server 2013 完整安裝並執行之後，才無法進行整合。</span><span class="sxs-lookup"><span data-stu-id="5d9be-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="5d9be-106">如需安裝 Exchange 的詳細資訊，請參閱 Exchange 2013 規劃與部署[http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)檔（位於）。</span><span class="sxs-lookup"><span data-stu-id="5d9be-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="5d9be-107">如需安裝 Lync Server 2013 的詳細資訊，請參閱中的規劃[http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)與部署檔。</span><span class="sxs-lookup"><span data-stu-id="5d9be-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="5d9be-108">在伺服器啟動並執行之後，您必須將伺服器對伺服器驗證憑證指派給 Lync Server 2013 和 Exchange 2013;這些憑證可讓 Lync Server 與 Exchange 交換資訊，並與其他人通訊。</span><span class="sxs-lookup"><span data-stu-id="5d9be-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="5d9be-109">當您安裝 Exchange 2013 時，會為您建立一個名稱為 Microsoft Exchange Server Auth 憑證的自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="5d9be-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="5d9be-110">這個可在本機電腦憑證存放區中找到的憑證應該用於 Exchange 2013 上的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="5d9be-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="5d9be-111">如需在 Exchange 2013 中指派憑證的詳細資料，請參閱「設定郵件流程與[http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)用戶端存取」。</span><span class="sxs-lookup"><span data-stu-id="5d9be-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="5d9be-112">對於 Lync Server 2013，您可以使用現有的 Lync 伺服器憑證作為伺服器對伺服器驗證憑證;例如，您的預設憑證也可以用來做為 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="5d9be-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="5d9be-113">Lync Server 2013 可讓您使用任何 Web 服務器憑證作為伺服器對伺服器驗證的憑證，前提是：</span><span class="sxs-lookup"><span data-stu-id="5d9be-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="5d9be-114">憑證在 [Subject] 欄位中包含您 SIP 網域的名稱。</span><span class="sxs-lookup"><span data-stu-id="5d9be-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="5d9be-115">在所有前端伺服器上，相同的憑證都設定為 OAuthTokenIssuer 憑證。</span><span class="sxs-lookup"><span data-stu-id="5d9be-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="5d9be-116">憑證的長度至少為2048位。</span><span class="sxs-lookup"><span data-stu-id="5d9be-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="5d9be-117">如需 Microsoft Lync Server 2013 的伺服器到伺服器驗證憑證的詳細資料，請參閱[將伺服器對伺服器驗證憑證指派給 Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9be-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="5d9be-118">在已指派憑證之後，您必須在 Exchange 2013 上設定自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="5d9be-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="5d9be-119">在 Exchange 2013 中，自動探索服務會設定使用者設定檔，並在使用者登入系統時提供 Exchange 服務的存取權。</span><span class="sxs-lookup"><span data-stu-id="5d9be-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="5d9be-120">使用者以其電子郵件地址和密碼出示自動探索服務;接著，服務會為使用者提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5d9be-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="5d9be-121">Exchange 2013 內部與外部連線的連線資訊。</span><span class="sxs-lookup"><span data-stu-id="5d9be-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="5d9be-122">使用者信箱伺服器的位置。</span><span class="sxs-lookup"><span data-stu-id="5d9be-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="5d9be-123">Outlook 功能的 Url，例如 [空閒/忙碌] 資訊、[整合訊息] 和 [離線通訊錄]。</span><span class="sxs-lookup"><span data-stu-id="5d9be-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="5d9be-124">Outlook Anywhere 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="5d9be-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="5d9be-125">您必須先設定自動探索服務，才能整合 Lync Server 2013 與 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="5d9be-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="5d9be-126">您可以從 Exchange 管理命令介面執行下列命令，並檢查 AutoDiscoverServiceInternalUri 屬性的值，以驗證自動探索服務是否已設定：</span><span class="sxs-lookup"><span data-stu-id="5d9be-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="5d9be-127">如果此值為空白，您必須為自動探索服務指派 URI。</span><span class="sxs-lookup"><span data-stu-id="5d9be-127">If this value is blank, you must assign a URI to the autodiscover service.</span></span> <span data-ttu-id="5d9be-128">通常，此 URI 看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="5d9be-128">Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="5d9be-129">您可以執行如下的命令來指派自動探索 URI：</span><span class="sxs-lookup"><span data-stu-id="5d9be-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="5d9be-130">如需自動探索服務的詳細資訊，請參閱「瞭解自動探索[http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)服務」。</span><span class="sxs-lookup"><span data-stu-id="5d9be-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="5d9be-131">在已設定自動探索服務之後，您必須修改 Lync Server OAuth 設定設定;這可確保 Lync Server 知道發現自動探索服務的位置。</span><span class="sxs-lookup"><span data-stu-id="5d9be-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="5d9be-132">若要在 Lync Server 2013 中修改 OAuth 設定設定，請在 Lync Server 管理命令介面中執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="5d9be-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="5d9be-133">執行此命令時，請確定您已將 URI 指定到您的 Exchange 伺服器上執行的自動探索服務，然後使用 [**自動**探索] 來指向服務位置，而不是 [自動探索] **。 .xml** （指向服務所使用的 xml 檔案）：</span><span class="sxs-lookup"><span data-stu-id="5d9be-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="5d9be-134">上述命令中的身分識別參數是選擇性的，這是因為 Lync Server 只允許您使用單一、全域的 OAuth 設定集合。</span><span class="sxs-lookup"><span data-stu-id="5d9be-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="5d9be-135">在其他專案中，這表示您可以使用這個稍微簡單的命令來設定自動探索 URL：</span><span class="sxs-lookup"><span data-stu-id="5d9be-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="5d9be-136">Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="5d9be-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="5d9be-137">如果您不熟悉該技術，OAuth 是由許多主要網站使用的標準授權通訊協定。</span><span class="sxs-lookup"><span data-stu-id="5d9be-137">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites.</span></span> <span data-ttu-id="5d9be-138">在 OAuth 中，使用者認證和密碼不會從一部電腦傳送至另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="5d9be-138">With OAuth, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="5d9be-139">相反地，驗證與授權是以安全權杖的交換為基礎;這些標記會針對特定的一組資源，授予存取權。</span><span class="sxs-lookup"><span data-stu-id="5d9be-139">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="5d9be-140">除了設定自動探索服務之外，您也必須為指向您的 Exchange 伺服器的服務建立 DNS 記錄。</span><span class="sxs-lookup"><span data-stu-id="5d9be-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="5d9be-141">例如，如果您的自動探索服務位於 autodiscover.litwareinc.com，您將需要建立 autodiscover.litwareinc.com 的 DNS 記錄，以解析為 Exchange 伺服器的完整功能變數名稱（例如，atl-exchange-001.litwareinc.com）。</span><span class="sxs-lookup"><span data-stu-id="5d9be-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

