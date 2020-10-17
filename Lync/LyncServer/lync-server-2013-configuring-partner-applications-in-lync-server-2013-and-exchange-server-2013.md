---
title: 在 Lync Server 2013 和 Exchange Server 2013 中設定合作夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8743b012042738ea25653cf49a804e08d59a423
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532510"
---
# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="3386d-102">在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="3386d-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3386d-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="3386d-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="3386d-104">伺服器對伺服器驗證一般會包含三個實體：兩個伺服器必須彼此通訊，另一個是協力廠商的安全性權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="3386d-104">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server.</span></span> <span data-ttu-id="3386d-105">例如，如果兩部伺服器 (，則伺服器 A 和伺服器 B) 需要通訊，則這兩部伺服器通常是透過聯繫權杖伺服器並取得相互信任的安全性權杖來開始。</span><span class="sxs-lookup"><span data-stu-id="3386d-105">If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token.</span></span> <span data-ttu-id="3386d-106">伺服器 A 接著會向伺服器 B 呈現該安全性權杖 (，反之亦然) 做為保證其真偽及其可信性的方式。</span><span class="sxs-lookup"><span data-stu-id="3386d-106">Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="3386d-107">不過，這是一般規則。</span><span class="sxs-lookup"><span data-stu-id="3386d-107">However, that's a general rule.</span></span> <span data-ttu-id="3386d-108">Lync Server 2013、Microsoft Exchange Server 2013 和 Microsoft SharePoint Server 2013 不需要使用協力廠商的 token 伺服器進行通訊，而是使用另一個憑證伺服器進行通訊;這是因為這些伺服器產品可以建立可以彼此接受的安全性權杖，而不需要個別的權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="3386d-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="3386d-109"> (只有在 Lync Server 2013、Exchange 2013 及 SharePoint Server 2013 中才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="3386d-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="3386d-110">如果您需要使用其他伺服器（包括其他 Microsoft server 產品）設定伺服器對伺服器的驗證，則需要使用協力廠商的 token 伺服器來執行。 ) </span><span class="sxs-lookup"><span data-stu-id="3386d-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="3386d-111">若要在 Lync Server 與 Exchange 之間設定伺服器對伺服器驗證，您必須執行下列兩項動作： 1) 您必須將適當的憑證指派給每個伺服器;而且，2) 您必須將每一部伺服器設定為另一部伺服器的夥伴應用程式：也就是說，您必須將 Lync Server 2013 設定為 Exchange 2013 的夥伴應用程式，而且您必須將 Exchange 2013 設定為 Lync Server 2013 的夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="3386d-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="3386d-112">設定 Lync Server 2013 成為 Exchange 2013 的夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="3386d-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="3386d-113">將 Lync Server 2013 設定為具有 Exchange 2013 之夥伴應用程式的最簡單方法，就是執行 Configure-EnterprisePartnerApplication.ps1 腳本，該腳本是隨 Exchange 2013 一起提供的 Windows PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="3386d-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="3386d-114">若要執行這個腳本，您必須提供 Lync Server 驗證元資料檔案的 URL;這通常是 Lync Server 2013 集區的完整功能變數名稱，後面加上尾碼/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="3386d-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="3386d-115">例如：</span><span class="sxs-lookup"><span data-stu-id="3386d-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="3386d-116">若要設定 Lync Server 成為夥伴應用程式，請開啟 Exchange 管理命令介面，並執行類似此 (的命令，假設 Exchange 已安裝在磁碟機 C：上，且其使用預設資料夾路徑) ：</span><span class="sxs-lookup"><span data-stu-id="3386d-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="3386d-117">設定夥伴應用程式之後，建議您在 Exchange 信箱和用戶端存取伺服器上停止並重新啟動網際網路資訊服務 (IIS) 。</span><span class="sxs-lookup"><span data-stu-id="3386d-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="3386d-118">您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：</span><span class="sxs-lookup"><span data-stu-id="3386d-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="3386d-119">您可以從 Exchange 管理命令介面或任何其他命令視窗中執行此命令，在系統管理員許可權下執行。</span><span class="sxs-lookup"><span data-stu-id="3386d-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="3386d-120">將 Exchange 2013 設定為 Lync Server 2013 的夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="3386d-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="3386d-121">將 Lync Server 2013 設定為 Exchange 2013 的夥伴應用程式之後，您必須將 Exchange 設定為 Lync Server 的夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="3386d-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="3386d-122">使用 Lync Server 管理命令介面，並指定 Exchange 的驗證元資料檔案，即可完成此動作。這通常是 Exchange 自動探索服務的 URI 後接尾碼/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="3386d-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="3386d-123">例如：</span><span class="sxs-lookup"><span data-stu-id="3386d-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="3386d-124">在 Lync Server 中，會使用 [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) Cmdlet 來設定夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="3386d-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="3386d-125">除了指定中繼資料 URI 之外，您還應該將應用程式信任層級設定為 [完整]。這可讓 Exchange 同時代表該領域中的自身和任何經授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="3386d-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="3386d-126">例如：</span><span class="sxs-lookup"><span data-stu-id="3386d-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="3386d-127">或者，您可以複製及修改 Lync Server 2013 伺服器對伺服器驗證檔中找到的腳本程式碼，以建立合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="3386d-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="3386d-128">如需詳細資訊，請參閱 [管理伺服器對伺服器驗證 (OAuth) 和夥伴應用程式在 Lync server 2013 中](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 的文章。</span><span class="sxs-lookup"><span data-stu-id="3386d-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="3386d-129">如果您已成功為 Lync Server 和 Exchange 設定夥伴應用程式，則表示您已成功設定兩種產品之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="3386d-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="3386d-130">Lync Server 2013 包括 Windows PowerShell Cmdlet [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))，可讓您驗證服務器對伺服器驗證是否已正確設定，以及 Lync Server Storage Service 是否可以連線至 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="3386d-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="3386d-131">此 Cmdlet 是透過連線至 Exchange 2013 使用者的信箱，將專案寫入該使用者的 [交談記錄] 資料夾中，然後選擇性地刪除該專案來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="3386d-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="3386d-132">若要測試 Lync Server 2013 和 Exchange 2013 的整合，請在 Lync Server 管理命令介面中執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="3386d-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="3386d-133">在上述命令中，SipUri 代表在 Exchange 2013 上具有帳戶之使用者的 SIP 位址;您的命令將會失敗。這不是有效的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="3386d-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="3386d-134">如果測試成功且已建立連線，您就可以繼續設定選用的功能，例如封存整合和整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="3386d-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

