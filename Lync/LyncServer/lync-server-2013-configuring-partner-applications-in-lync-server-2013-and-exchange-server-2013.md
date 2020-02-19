---
title: Lync Server 2013 和 Exchange Server 2013 中設定夥伴應用程式
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
ms.openlocfilehash: fca5fe648ecfb00c7ef7bcb84948a68e4386bbf3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="e353b-102">Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="e353b-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e353b-103">_**主題上次修改日期：** 2012年-11-12_</span><span class="sxs-lookup"><span data-stu-id="e353b-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e353b-104">伺服器對伺服器驗證通常涉及三個實體： 兩部伺服器需要彼此通訊，以及協力廠商安全性權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="e353b-104">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server.</span></span> <span data-ttu-id="e353b-105">如果兩部伺服器 （例如，伺服器 A 和伺服器 B） 需要進行通訊，然後這兩個這些伺服器通常啟動連絡 token 的伺服器，並取得彼此信任安全性 token。</span><span class="sxs-lookup"><span data-stu-id="e353b-105">If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token.</span></span> <span data-ttu-id="e353b-106">伺服器的然後顯示該安全性權杖伺服器 B （反之亦然） 的方式，確保其授權和其可信度。</span><span class="sxs-lookup"><span data-stu-id="e353b-106">Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="e353b-107">不過，這是一般規則。</span><span class="sxs-lookup"><span data-stu-id="e353b-107">However, that's a general rule.</span></span> <span data-ttu-id="e353b-108">Lync Server 2013、 Microsoft Exchange Server 2013 和 Microsoft SharePoint Server 2013 不需要使用協力廠商權杖伺服器，與另一個; 通訊時這是因為這些伺服器產品可以建立安全性權杖可以接受的另一個，而不需要個別的權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="e353b-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="e353b-109">（此功能只有在 Lync Server 2013、 Exchange 2013 和 SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="e353b-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="e353b-110">如果您需要設定與其他伺服器的伺服器對伺服器驗證，包括其他 Microsoft server 產品，則您將需要這麼做使用協力廠商權杖伺服器。）</span><span class="sxs-lookup"><span data-stu-id="e353b-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="e353b-111">若要設定 Lync Server 和 Exchange 之間的伺服器對伺服器驗證，您必須執行下列兩件事： 1) 您必須將適當的憑證指派給每個伺服器;和，2） 您必須設定為夥伴應用程式的另一部伺服器的每一部伺服器： 這表示您必須設定 Lync Server 2013 到 Exchange 2013 中，為合作夥伴應用程式，您必須設定為 Lync Server 2013 的協力廠商應用程式的 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="e353b-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="e353b-112">設定 Lync Server 2013 到 Exchange 2013 為合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="e353b-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="e353b-113">設定 Lync Server 2013 與 Exchange 2013 為合作夥伴應用程式的最簡單方法是執行 Configure-enterprisepartnerapplication.ps1 指令碼，隨附於 Exchange 2013 的 Windows PowerShell 指令碼。</span><span class="sxs-lookup"><span data-stu-id="e353b-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="e353b-114">若要執行此指令碼，您必須提供 URL Lync Server 驗證中繼資料文件;這通常會接著尾碼 /metadata/json/1 Lync Server 2013 集區完整的網域名稱。</span><span class="sxs-lookup"><span data-stu-id="e353b-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="e353b-115">例如：</span><span class="sxs-lookup"><span data-stu-id="e353b-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="e353b-116">若要設定 Lync Server 作為夥伴應用程式，請開啟 Exchange 管理命令介面並執行如下的命令 （假設已在 c： 磁碟機上安裝 Exchange，且其使用預設資料夾路徑）：</span><span class="sxs-lookup"><span data-stu-id="e353b-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="e353b-117">設定夥伴應用程式之後建議您停止並重新啟動您的 Exchange 信箱和用戶端存取伺服器上的網際網路資訊服務 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="e353b-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="e353b-118">您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：</span><span class="sxs-lookup"><span data-stu-id="e353b-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="e353b-119">在 Exchange 管理命令介面中，或是從任何其他命令視窗中執行系統管理員權限，可以從執行此命令。</span><span class="sxs-lookup"><span data-stu-id="e353b-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="e353b-120">設定 Lync Server 2013 的協力廠商應用程式的 Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="e353b-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="e353b-121">您已設定 Lync Server 2013 到 Exchange 2013 為合作夥伴應用程式之後，您必須接著設定 Lync Server 的協力廠商應用程式的 Exchange。</span><span class="sxs-lookup"><span data-stu-id="e353b-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="e353b-122">這可以經由使用 Lync Server 管理命令介面和 exchange; 指定驗證中繼資料文件這通常會接著尾碼 /metadata/json/1 Exchange 自動探索服務的 URI。</span><span class="sxs-lookup"><span data-stu-id="e353b-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="e353b-123">例如：</span><span class="sxs-lookup"><span data-stu-id="e353b-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="e353b-124">在 Lync Server 中，使用[New-cspartnerapplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet 設定夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="e353b-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="e353b-125">除了指定 URI 的中繼資料也應設定應用程式信任層級為 Full;這樣可讓 Exchange 來表示本身和領域中的任何授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="e353b-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="e353b-126">例如：</span><span class="sxs-lookup"><span data-stu-id="e353b-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="e353b-127">或者，您可以藉由複製和修改 Lync Server 2013 伺服器對伺服器驗證文件中找到的指令碼程式碼建立夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="e353b-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="e353b-128">請參閱[Managing 伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e353b-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="e353b-129">如果您已成功設定協力應用程式的 Lync Server 和 Exchange，表示您已也成功設定這兩項產品之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="e353b-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="e353b-130">Lync Server 2013 包含 Windows PowerShell cmdlet， [Test-csexstorageconnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))，可讓您確認已正確設定伺服器對伺服器驗證和 Lync Server 儲存體服務可以連線至 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="e353b-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="e353b-131">指令程式的運作方式連線至 Exchange 2013 使用者信箱，寫入交談記錄資料夾中的項目，該使用者的然後選擇性地刪除該項目。</span><span class="sxs-lookup"><span data-stu-id="e353b-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="e353b-132">若要測試的 Lync Server 2013 和 Exchange 2013 的整合，請執行命令類似從 Lync Server 管理命令介面中：</span><span class="sxs-lookup"><span data-stu-id="e353b-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="e353b-133">在上述命令中，SipUri 代表具有 Exchange 2013 /; 帳戶的使用者的 SIP 位址您的命令會失敗這不是有效的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e353b-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="e353b-134">如果測試成功且建立連線，您可以再繼續設定選用功能，例如封存整合和整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="e353b-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

