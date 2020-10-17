---
title: Lync Server 2013：遠端呼叫控制的部署工作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2ac45e0f589ac155d2e0f51b0115036a97809e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499050"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="ca14f-102">Lync Server 2013 中遠端呼叫控制的部署工作</span><span class="sxs-lookup"><span data-stu-id="ca14f-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca14f-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="ca14f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="ca14f-104">本主題說明為您的 Lync Server 環境中的使用者啟用遠端呼叫控制時必須執行的部署工作。</span><span class="sxs-lookup"><span data-stu-id="ca14f-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ca14f-105">如果您要在 Microsoft Office Communicator 2007 R2 中遷移先前為遠端呼叫控制啟用的使用者，您必須先執行額外的部署工作，再開始執行本主題中所述的遠端呼叫控制部署工作。</span><span class="sxs-lookup"><span data-stu-id="ca14f-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="ca14f-106">在將遷移程式移至 Lync Server 時，已 (先前稱為 <EM>授權主項目目</EM> 的受信任應用程式專案) ，必須視需要使用 Office 通訊伺服器 2007 R2 系統管理工具加以移除。</span><span class="sxs-lookup"><span data-stu-id="ca14f-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="ca14f-107">如需移除授權主機的詳細資訊，請參閱 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a 舊版授權主機 In Lync Server 2013 (選用) </A>。</span><span class="sxs-lookup"><span data-stu-id="ca14f-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="ca14f-108">步驟1：安裝並設定 SIP/CSTA 閘道與 PBX 通訊</span><span class="sxs-lookup"><span data-stu-id="ca14f-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="ca14f-109">您必須在您的環境中至少安裝一個可同時連接至 Lync Server 與現有私人分支 exchange (PBX) 的 SIP/CSTA 閘道，以便為您的使用者提供遠端呼叫控制功能。</span><span class="sxs-lookup"><span data-stu-id="ca14f-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="ca14f-110">SIP/CSTA 閘道是 SIP 和電腦支援之電信應用程式 (CSTA) 之間的閘道。</span><span class="sxs-lookup"><span data-stu-id="ca14f-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="ca14f-111">不論您是安裝多個閘道，還是只安裝一個閘道，每一位使用者都可以設定一個閘道或 PBX。</span><span class="sxs-lookup"><span data-stu-id="ca14f-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="ca14f-112">如果現有的 PBX 沒有 SIP/CSTA 介面，請確定您部署可支援 PBX 的 SIP/CSTA 閘道，包括對專屬 PBX 廠商特有的信號通訊協定的支援。</span><span class="sxs-lookup"><span data-stu-id="ca14f-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="ca14f-113">如需功能的詳細資訊，請直接向每個廠商諮詢。</span><span class="sxs-lookup"><span data-stu-id="ca14f-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="ca14f-114">當您準備好部署可以與 Lync Server 整合以進行遠端呼叫控制的 SIP/CSTA 閘道時，請與您的閘道廠商或供應商的閘道檔，瞭解下列資訊的閘道所需之語法：</span><span class="sxs-lookup"><span data-stu-id="ca14f-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="ca14f-115">閘道的行伺服器 URI</span><span class="sxs-lookup"><span data-stu-id="ca14f-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="ca14f-116">將指派給閘道之使用者的行 URI</span><span class="sxs-lookup"><span data-stu-id="ca14f-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="ca14f-117">上述設定是在使用者設定期間需要的，且必須依閘道所期望的方式，以路由傳送並正確連接至 PBX。</span><span class="sxs-lookup"><span data-stu-id="ca14f-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="ca14f-118">您可以在 Microsoft 整合通訊開啟互通性計畫網站上，參閱廠商 [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) 。</span><span class="sxs-lookup"><span data-stu-id="ca14f-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="ca14f-119">步驟2：設定 Lync Server 將 CSTA 要求路由傳送至 SIP/CSTA 閘道</span><span class="sxs-lookup"><span data-stu-id="ca14f-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="ca14f-120">您必須在 Lync 伺服器集區上建立靜態路由，使其為您要路由傳送遠端呼叫控制要求之所有 SIP/CSTA 閘道的目的地位址 (Server URI) 。</span><span class="sxs-lookup"><span data-stu-id="ca14f-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="ca14f-121">您也必須建立對應于每個目的地位址的受信任應用程式專案。</span><span class="sxs-lookup"><span data-stu-id="ca14f-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="ca14f-122">當您將閘道指定為信任的應用程式時，它會被提供信任的狀態，以作為 Lync Server 環境的一部分來執行，即使它是由第三 (方開發，也會執行稱為 *外部服務* 的服務，因為它並非產品) 內建的元件。</span><span class="sxs-lookup"><span data-stu-id="ca14f-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="ca14f-123">最後，如果 Lync Server 會使用傳輸控制通訊協定 (TCP) 連線來連線至 SIP/CSTA 閘道，而不是傳輸層安全性 (TLS) 連線，您也必須使用拓撲產生器來定義閘道 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ca14f-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="ca14f-124">如需設定靜態路由的詳細資訊，請參閱 [在 Lync Server 2013 中設定遠端呼叫控制的靜態路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ca14f-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="ca14f-125">如需設定信任的應用程式專案的詳細資訊，請參閱 [在 Lync Server 2013 中為遠端呼叫控制設定信任的應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ca14f-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="ca14f-126">如需在拓撲產生器中定義 SIP/CSTA 閘道 IP 位址的詳細資訊，請參閱 [在 Lync Server 2013 中定義 SIP/CSTA 閘道 ip 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。</span><span class="sxs-lookup"><span data-stu-id="ca14f-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="ca14f-127">步驟3：設定 Lync 使用者進行遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="ca14f-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="ca14f-128">啟用 Lync Server 的使用者之後，您可以使用 Lync Server 控制台或 Lync Server 管理命令介面來啟用遠端呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="ca14f-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="ca14f-129">在此部署步驟中，您會為每位使用者指派行伺服器 URI 和行 URI。</span><span class="sxs-lookup"><span data-stu-id="ca14f-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="ca14f-130">Line server URI 是您計畫指派給使用者的 SIP/CSTA 閘道的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="ca14f-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="ca14f-131">行 URI 是指派給使用者的唯一電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ca14f-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="ca14f-132">如需有關為遠端呼叫控制設定使用者的詳細資訊，請參閱 [在 Lync Server 2013 中啟用遠端呼叫控制的 Lync 使用者](lync-server-2013-enable-lync-users-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ca14f-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="ca14f-133">步驟4：定義 Lync Server 電話號碼正規化規則</span><span class="sxs-lookup"><span data-stu-id="ca14f-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="ca14f-134">在遠端呼叫控制案例中，Lync Server 會使用電話號碼正規化規則，將從 SIP/CSTA 閘道收到的電話號碼轉換成 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="ca14f-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="ca14f-135">電話號碼必須採用此標準化格式，特定的遠端呼叫控制功能才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="ca14f-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="ca14f-136">遠端呼叫控制使用與您為通訊錄服務電話號碼正規化所設定的相同電話號碼正規化規則，這與用於 Enterprise Voice 的電話號碼正常化規則不同。</span><span class="sxs-lookup"><span data-stu-id="ca14f-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="ca14f-137">如需遠端呼叫控制如何使用電話號碼正規化規則的詳細資訊，請參閱 [Lync Server 2013 中的遠端呼叫控制和電話號碼](lync-server-2013-remote-call-control-and-phone-number-normalization.md)正規化。</span><span class="sxs-lookup"><span data-stu-id="ca14f-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="ca14f-138">如需通訊錄服務之電話號碼正規化規則的詳細資訊，請參閱 Operations 檔中的 [管理 Lync Server 2013 主題中的通訊錄服務](lync-server-2013-administering-the-address-book-service.md) 主題。</span><span class="sxs-lookup"><span data-stu-id="ca14f-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

