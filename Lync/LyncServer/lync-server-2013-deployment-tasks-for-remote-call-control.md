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
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="f36a3-102">Lync Server 2013 中遠端呼叫控制的部署工作</span><span class="sxs-lookup"><span data-stu-id="f36a3-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f36a3-103">_**主題上次修改日期：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="f36a3-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="f36a3-104">本主題描述您必須執行才能針對 Lync Server 環境中的使用者啟用遠端通話控制的部署工作。</span><span class="sxs-lookup"><span data-stu-id="f36a3-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f36a3-105">如果您在 Microsoft Office Communicator 2007 R2 中將先前已啟用遠端通話控制的使用者遷移，您必須先執行額外的部署工作，才能開始執行本主題中所述的遠端呼叫控制部署工作。</span><span class="sxs-lookup"><span data-stu-id="f36a3-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="f36a3-106">在將程式遷移至 Lync Server 時，必須視需要使用 Office 通訊伺服器 2007 R2 管理工具移除受信任的應用程式專案（先前稱為<EM>授權主項目目</EM>）。</span><span class="sxs-lookup"><span data-stu-id="f36a3-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="f36a3-107">如需有關移除授權主機的詳細資訊，請參閱<A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中移除舊版授權主機（選用）</A>。</span><span class="sxs-lookup"><span data-stu-id="f36a3-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="f36a3-108">步驟1：安裝及設定 SIP/CSTA 閘道以與您的 PBX 進行通訊</span><span class="sxs-lookup"><span data-stu-id="f36a3-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="f36a3-109">您必須在您的環境中安裝至少一個能連線到 Lync Server 和現有私人分支 exchange （PBX）的 SIP/CSTA 閘道，以便為您的使用者提供遠端通話控制功能。</span><span class="sxs-lookup"><span data-stu-id="f36a3-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="f36a3-110">SIP/CSTA 閘道是 SIP 與電腦支援的電訊應用程式（CSTA）之間的閘道。</span><span class="sxs-lookup"><span data-stu-id="f36a3-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="f36a3-111">不論您是否安裝多個閘道或只有一個，每個使用者都可以使用一個閘道或 PBX 進行設定。</span><span class="sxs-lookup"><span data-stu-id="f36a3-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="f36a3-112">如果您的現有 PBX 沒有 SIP/CSTA 介面，請確保您部署可支援 PBX 的 SIP/CSTA 閘道，包括對專用 PBX 供應商特定的信號通訊協定的支援。</span><span class="sxs-lookup"><span data-stu-id="f36a3-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="f36a3-113">如需功能的詳細資訊，請直接向每個供應商諮詢。</span><span class="sxs-lookup"><span data-stu-id="f36a3-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="f36a3-114">當您準備好要部署可與 Lync Server 進行遠端通話控制的 SIP/CSTA 閘道時，請諮詢您的閘道廠商或供應商的閘道檔，瞭解閘道所需的語法，以及下列資訊：</span><span class="sxs-lookup"><span data-stu-id="f36a3-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="f36a3-115">閘道的行伺服器 URI</span><span class="sxs-lookup"><span data-stu-id="f36a3-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="f36a3-116">將指派給閘道之使用者的行 URI</span><span class="sxs-lookup"><span data-stu-id="f36a3-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="f36a3-117">上述設定是在使用者設定期間需要的，而且必須按照閘道的預期來指定，才能正確地路由及連線到 PBX。</span><span class="sxs-lookup"><span data-stu-id="f36a3-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="f36a3-118">您可以在 Microsoft 整合通訊開啟互通性計畫網站上，參閱[http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)提供給合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="f36a3-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="f36a3-119">步驟2：將 Lync Server 設定為將 CSTA 要求傳送到 SIP/CSTA 閘道</span><span class="sxs-lookup"><span data-stu-id="f36a3-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="f36a3-120">您必須在您想要路由遠端通話控制要求之部署中的所有 SIP/CSTA 閘道的目的地位址（伺服器 URI），在 Lync 伺服器池中建立靜態路由。</span><span class="sxs-lookup"><span data-stu-id="f36a3-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="f36a3-121">您也必須建立對應至每個目的地位址的信任應用程式專案。</span><span class="sxs-lookup"><span data-stu-id="f36a3-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="f36a3-122">當您將閘道指派為受信任的應用程式時，它會被指定為在 Lync Server 環境中執行的信任狀態，即使是由協力廠商開發（並執行稱為*外部服務*的服務，因為它是產品的內建元件）。</span><span class="sxs-lookup"><span data-stu-id="f36a3-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="f36a3-123">最後，如果 Lync Server 會使用傳輸控制通訊協定（TCP）連線（而不是傳輸層安全性（TLS）連線）連線到 SIP/CSTA 閘道，您也必須使用拓撲結構建立程式來定義閘道 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="f36a3-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="f36a3-124">如需設定靜態路由的詳細資料，請參閱[在 Lync Server 2013 中設定遠端通話控制的靜態路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f36a3-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="f36a3-125">如需設定受信任的應用程式專案的詳細資料，請參閱[在 Lync Server 2013 中設定遠端通話控制的信任應用程式專案](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f36a3-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="f36a3-126">如需在拓撲結構建立器中定義 SIP/CSTA 閘道 IP 位址的詳細資料，請參閱[在 Lync Server 2013 中定義 sip/CSTA 閘道 ip 位址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。</span><span class="sxs-lookup"><span data-stu-id="f36a3-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="f36a3-127">步驟3：設定遠端通話控制的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="f36a3-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="f36a3-128">在使用者啟用 Lync Server 之後，您可以使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面] 來啟用遠端通話控制。</span><span class="sxs-lookup"><span data-stu-id="f36a3-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="f36a3-129">在此部署步驟中，您可以為每位使用者指派線條伺服器 URI 和行 URI。</span><span class="sxs-lookup"><span data-stu-id="f36a3-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="f36a3-130">Line server URI 是您計畫指派給使用者的 SIP/CSTA 閘道的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="f36a3-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="f36a3-131">[行 URI] 是指派給使用者的唯一電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f36a3-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="f36a3-132">如需針對遠端通話控制設定使用者的詳細資料，請參閱[在 Lync Server 2013 中啟用遠端通話控制的 Lync 使用者](lync-server-2013-enable-lync-users-for-remote-call-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f36a3-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="f36a3-133">步驟4：定義 Lync Server Phone 編號正常化規則</span><span class="sxs-lookup"><span data-stu-id="f36a3-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="f36a3-134">在遠端通話控制案例中，Lync Server 會使用電話號碼正規化規則，將它從 SIP/CSTA 閘道收到的電話號碼轉換為. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="f36a3-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="f36a3-135">電話號碼必須是這個標準格式，才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="f36a3-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="f36a3-136">[遠端通話控制] 會使用您針對通訊錄服務電話號碼正規化所設定的相同電話號碼正規化規則，這與企業語音所用的電話號碼正規化規則不同。</span><span class="sxs-lookup"><span data-stu-id="f36a3-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="f36a3-137">如需遠端通話控制如何使用電話號碼正規化規則的詳細資料，請參閱[Lync Server 2013 中的遠端通話控制和電話號碼標準化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)。</span><span class="sxs-lookup"><span data-stu-id="f36a3-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="f36a3-138">如需通訊錄服務的電話號碼正規化規則的詳細資料，請參閱在作業檔中[管理 Lync Server 2013 主題中的通訊錄服務](lync-server-2013-administering-the-address-book-service.md)主題。</span><span class="sxs-lookup"><span data-stu-id="f36a3-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

