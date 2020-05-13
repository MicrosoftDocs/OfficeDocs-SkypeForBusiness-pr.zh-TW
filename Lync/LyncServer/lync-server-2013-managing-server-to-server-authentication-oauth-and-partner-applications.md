---
title: 管理伺服器對伺服器驗證（OAuth）和夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f3f32b4e0c13ea68df183d19b020118e32205b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="69412-102">在 Lync Server 2013 中管理伺服器對伺服器驗證（OAuth）和夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="69412-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69412-103">_**主題上次修改日期：** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="69412-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="69412-104">Microsoft Lync Server 2013 必須能夠與其他應用程式和伺服器產品進行安全、順利的通訊。</span><span class="sxs-lookup"><span data-stu-id="69412-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="69412-105">例如，您可以設定 Lync Server 2013，讓連絡人資料和（或）封存資料儲存在 Microsoft Exchange Server 2013 中;不過，只有當 Lync Server 和 Exchange 能夠安全地與彼此進行通訊時，才可執行此動作。</span><span class="sxs-lookup"><span data-stu-id="69412-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="69412-106">同樣地，您可以在 Microsoft SharePoint Server 中排程 Lync Server 會議；但是，也只有在這兩部伺服器 ((SharePoint 及 Lync Server) 互相信任的情況下，這才有辦法達成。</span><span class="sxs-lookup"><span data-stu-id="69412-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="69412-107">雖然可以針對 Lync 對 Exchange 通訊使用一種驗證機制，而針對 Lync 對 SharePoint 通訊使用另外一種機制，更好又更有效的方式為針對所有伺服器對伺服器的驗證及授權使用標準化方法。</span><span class="sxs-lookup"><span data-stu-id="69412-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="69412-108">使用單一標準化方法進行伺服器對伺服器的驗證是 Lync Server 2013 所採用的方法。</span><span class="sxs-lookup"><span data-stu-id="69412-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="69412-109">針對2013版本，Lync Server 2013 （包括 Exchange 2013 和 Microsoft SharePoint Server）的其他 Microsoft Server 產品都支援伺服器對伺服器驗證和授權的 OAuth （開放授權）通訊協定。</span><span class="sxs-lookup"><span data-stu-id="69412-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="69412-110">藉由 OAuth (一些主要網站皆使用的標準授權通訊協定)，使用者認證及密碼並不會在電腦間傳遞。</span><span class="sxs-lookup"><span data-stu-id="69412-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="69412-111">驗證及授權是基於安全性權杖的交換，這些權杖會授與一段特定時間內一組特定資源的存取權。</span><span class="sxs-lookup"><span data-stu-id="69412-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="69412-112">OAuth 驗證通常涉及三方：單一授權伺服器及兩個需要互相通訊的領域。</span><span class="sxs-lookup"><span data-stu-id="69412-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="69412-113">（您也可以不使用授權伺服器進行伺服器對伺服器的驗證，這會在本檔稍後將討論的程式。）安全性權杖是由授權伺服器（也稱為安全性權杖伺服器）所發行，以進行通訊的兩個領域;這些權杖會驗證來自某個領域的通訊是否應該由其他領域所信任。</span><span class="sxs-lookup"><span data-stu-id="69412-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="69412-114">例如，授權伺服器可能會發出權杖，以確認特定 Lync Server 2013 領域的使用者能夠存取指定的 Exchange 2013 領域，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="69412-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="69412-115">領域只是安全性容器。</span><span class="sxs-lookup"><span data-stu-id="69412-115">A realm is simply a security container.</span></span> <span data-ttu-id="69412-116">Lync Server 2013 預設會使用您的預設 SIP 網域作為其 OAuth 領域。</span><span class="sxs-lookup"><span data-stu-id="69412-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="69412-117">其他 SIP 命名空間會新增至 OAuth 憑證中的主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="69412-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="69412-118">Lync Server 2013 支援三種伺服器對伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="69412-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="69412-119">使用 Lync Server 2013，您可以：</span><span class="sxs-lookup"><span data-stu-id="69412-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="69412-120">設定 Lync Server 2013 的內部部署安裝與 Exchange 2013 和/或 Microsoft SharePoint Server 的內部部署安裝之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="69412-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="69412-121">設定一對 Microsoft 365 元件之間的伺服器對伺服器驗證（例如，在 Microsoft Exchange 和 Microsoft Lync Server 之間，或在 Microsoft Lync Server 和 Microsoft SharePoint 之間）。</span><span class="sxs-lookup"><span data-stu-id="69412-121">Configure server-to-server authentication between a pair of Microsoft 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="69412-122">在跨部署環境中設定伺服器對伺服器的驗證（也就是在內部部署伺服器與 Microsoft 365 元件之間的伺服器對伺服器驗證）。</span><span class="sxs-lookup"><span data-stu-id="69412-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Microsoft 365 component).</span></span>

<span data-ttu-id="69412-123">請注意，目前只有 Exchange 2013、SharePoint Server 和 Lync Server 2013 支援伺服器對伺服器驗證;如果您未執行這些伺服器之一，您將無法完全執行 OAuth 驗證。</span><span class="sxs-lookup"><span data-stu-id="69412-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="69412-124">您也應該指出，您不需要使用伺服器對伺服器驗證：不需要伺服器對伺服器驗證即可部署 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="69412-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="69412-125">如果 Lync Server 2013 不需要與其他伺服器（例如 Exchange 2013）進行通訊，則不需要伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="69412-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="69412-126">然而，如果要使用 Lync Server 某些新功能 (例如，整合連絡人存放區)，則需要伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="69412-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="69412-127">使用整合連絡人存放區時，Lync Server 2013 連絡人資訊會儲存在 Exchange 2013 中，而不是儲存在 Lync Server 中;這可讓使用者有一組可在 Lync、Microsoft Outlook 或 Microsoft Outlook Web Access 中輕鬆存取的連絡人。</span><span class="sxs-lookup"><span data-stu-id="69412-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="69412-128">由於整合的連絡人存放區需要 Lync Server 2013，以與 Exchange 2013 共用資訊，因此您必須使用伺服器對伺服器驗證，才能部署該功能。</span><span class="sxs-lookup"><span data-stu-id="69412-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="69412-129">如果您選擇使用 Exchange 封存（其中立即訊息會話的記錄會儲存為 Exchange 2013 電子郵件，而不是個別的資料庫記錄），則也需要伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="69412-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="69412-130">若要讓 Microsoft 365 版本的 Lync Server 與其 Exchange 對應，Lync Server 2013 必須先取得授權伺服器的安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="69412-130">For the Microsoft 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="69412-131">然後，Lync Server 會使用該安全性權杖，將自己識別為 Exchange。</span><span class="sxs-lookup"><span data-stu-id="69412-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="69412-132">Microsoft 365 版本的 Exchange 必須經過相同的程式，才能與 Lync Server 2013 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="69412-132">The Microsoft 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="69412-133">不過，對於兩部 Microsoft 伺服器之間的內部部署伺服器對伺服器驗證，則不需要使用協力廠商權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="69412-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="69412-134">伺服器產品（如 Lync Server 2013 和 Exchange 2013）具有內建的權杖伺服器，可供與支援伺服器對伺服器驗證之其他 Microsoft 伺服器（例如 SharePoint Server）進行驗證。</span><span class="sxs-lookup"><span data-stu-id="69412-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="69412-135">例如，Lync Server 2013 可以自行發行並簽署安全性權杖，然後使用該權杖來與 Exchange 2013 通訊。</span><span class="sxs-lookup"><span data-stu-id="69412-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="69412-136">在這種情況下，便不需要協力廠商權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="69412-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="69412-137">若要為 Lync Server 2013 的內部部署執行設定伺服器對伺服器驗證，您必須執行下列兩項作業：</span><span class="sxs-lookup"><span data-stu-id="69412-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="69412-138">指派憑證給 Lync Server 內建的權杖發行者。</span><span class="sxs-lookup"><span data-stu-id="69412-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="69412-139">將 Lync Server 2013 通訊的伺服器設定為 "partner application"。</span><span class="sxs-lookup"><span data-stu-id="69412-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="69412-140">例如，如果 Lync Server 2013 需要與 Exchange 2013 通訊，則您必須將 Exchange 設定為合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="69412-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="69412-141">「協力廠商應用程式」是 Lync Server 2013 可以直接交換安全性權杖的任何應用程式，而不需要經過協力廠商安全性權杖伺服器。</span><span class="sxs-lookup"><span data-stu-id="69412-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="69412-142">請注意，OAuth 是產品的核心部分，無法停用或移除。</span><span class="sxs-lookup"><span data-stu-id="69412-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="69412-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="69412-143">See Also</span></span>


[<span data-ttu-id="69412-144">將伺服器對伺服器驗證憑證指派給 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69412-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="69412-145">在跨部署環境中設定 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69412-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

