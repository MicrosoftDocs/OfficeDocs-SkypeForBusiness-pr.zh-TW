---
title: Lync Server 2013：設定反向 proxy 伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up reverse proxy servers
ms:assetid: 00bc138a-243f-4389-bfa5-9c62fcc95132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398069(v=OCS.15)
ms:contentKeyID: 48183225
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f4ff853e3f31804e4bca55bd6a4576e25702b6c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-reverse-proxy-servers-for-lync-server-2013"></a><span data-ttu-id="49f1f-102">設定 Lync Server 2013 的反向 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="49f1f-102">Setting up reverse proxy servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49f1f-103">_**主題上次修改日期：** 2014-05-08_</span><span class="sxs-lookup"><span data-stu-id="49f1f-103">_**Topic Last Modified:** 2014-05-08_</span></span>

<span data-ttu-id="49f1f-104">針對 Microsoft Lync Server 2013 Edge Server 部署，外部用戶端必須使用周邊網路反向 proxy，才能存取「Director」和使用者主集區的 [Office 通訊伺服器) 中稱為*Web 元件* (的 Lync Server 2013 web 服務]。</span><span class="sxs-lookup"><span data-stu-id="49f1f-104">For Microsoft Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for external clients to access the Lync Server 2013 Web Services (called *Web Components* in Office Communications Server) on the Director and the user’s home pool.</span></span> <span data-ttu-id="49f1f-105">有些需要透過反向 Proxy 進行外部存取的功能包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="49f1f-105">Some of the features that require external access through a reverse proxy include the following:</span></span>

  - <span data-ttu-id="49f1f-106">讓外部使用者能夠下載會議的內容。</span><span class="sxs-lookup"><span data-stu-id="49f1f-106">Enabling external users to download meeting content for your meetings.</span></span>

  - <span data-ttu-id="49f1f-107">讓外部使用者能夠擴充通訊群組。</span><span class="sxs-lookup"><span data-stu-id="49f1f-107">Enabling external users to expand distribution groups.</span></span>

  - <span data-ttu-id="49f1f-108">讓遠端使用者能夠從通訊錄服務下載檔案。</span><span class="sxs-lookup"><span data-stu-id="49f1f-108">Enabling remote users to download files from the Address Book service.</span></span>

  - <span data-ttu-id="49f1f-109">存取 Lync Web App 用戶端。</span><span class="sxs-lookup"><span data-stu-id="49f1f-109">Accessing the Lync Web App client.</span></span>

  - <span data-ttu-id="49f1f-110">存取 [電話撥入式會議設定] 網頁。</span><span class="sxs-lookup"><span data-stu-id="49f1f-110">Accessing the Dial-in Conferencing Settings webpage.</span></span>

  - <span data-ttu-id="49f1f-111">讓外部裝置能夠連線至裝置更新 Web 服務並取得更新。</span><span class="sxs-lookup"><span data-stu-id="49f1f-111">Enabling external devices to connect to Device Update web service and obtain updates.</span></span>

  - <span data-ttu-id="49f1f-112">讓行動應用程式能夠自動探索和使用行動性 (Mcx) URLs 從網際網路。</span><span class="sxs-lookup"><span data-stu-id="49f1f-112">Enabling mobile applications to automatically discover and use the mobility (Mcx) URLs from the Internet.</span></span>

  - <span data-ttu-id="49f1f-113">啟用 Lync 2013 用戶端、Lync Windows Store 應用程式和 Lync 2013 行動用戶端，以找出 Lync 探索 (自動探索) URLs 和使用整合通訊 Web API (UCWA) 。</span><span class="sxs-lookup"><span data-stu-id="49f1f-113">Enabling the Lync 2013 client, Lync Windows Store app and Lync 2013 Mobile client to locate the Lync Discover (autodiscover) URLs and use Unified Communications Web API (UCWA).</span></span>

<span data-ttu-id="49f1f-114">我們建議將您的 HTTP 反向 Proxy 設定成發行所有集區中的所有 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="49f1f-114">We recommend that you configure your HTTP reverse proxy to publish all Web Services in all pools.</span></span> <span data-ttu-id="49f1f-115">發佈 HTTPs://ExternalFQDN/ \* 發佈所有集區的 IIS 虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="49f1f-115">Publishing https:// ExternalFQDN/\* publishes all IIS virtual directories for a pool.</span></span> <span data-ttu-id="49f1f-116">您組織中的每一個 Standard Edition Server、前端集區或 Director 或 Director 集區都需要有一個發行規則。</span><span class="sxs-lookup"><span data-stu-id="49f1f-116">You need one publishing rule for each Standard Edition server, Front End pool, or Director or Director pool in your organization.</span></span>

<span data-ttu-id="49f1f-117">此外，您必須發佈簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="49f1f-117">In addition, you need to publish the simple URLs.</span></span> <span data-ttu-id="49f1f-118">如果組織有 Director 或 Director 集區，HTTP 反向 proxy 會偵聽 HTTP/HTTPS 對簡單 URLs 的要求，並將其代理到 Director 或 Director 集區上的外部 Web 服務虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="49f1f-118">If the organization has a Director or Director pool, the HTTP reverse proxy listens for HTTP/HTTPS requests to the simple URLs and proxies them to the external Web Services virtual directory on the Director or Director pool.</span></span> <span data-ttu-id="49f1f-119">若尚未部署 Director，您必須指定一個集區，以處理簡單 URLs 的要求。</span><span class="sxs-lookup"><span data-stu-id="49f1f-119">If you have not deployed a Director, you need to designate one pool to handle requests to the simple URLs.</span></span> <span data-ttu-id="49f1f-120"> (如果這不是使用者的主集區，則會將它們重新導向至使用者主集區上的 Web 服務) 。</span><span class="sxs-lookup"><span data-stu-id="49f1f-120">(If this is not the user’s home pool, it will redirect them onward to the Web Services on the user’s home pool).</span></span> <span data-ttu-id="49f1f-121">簡單的 URLs 可以透過專用的 web 發行規則來處理，也可以將其新增到 Director 之網頁發行規則的公用名稱。</span><span class="sxs-lookup"><span data-stu-id="49f1f-121">The simple URLs can be handled by a dedicated web publishing rule, or you can add it to the public names of the web publishing rule for the Director.</span></span> <span data-ttu-id="49f1f-122">您也需要發佈外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="49f1f-122">You also need to publish the external Autodiscover Service URL.</span></span>

<span data-ttu-id="49f1f-123">您可以使用 Microsoft Forefront 威脅管理閘道2010、Microsoft Internet 安全性和加速度 (ISA) Server 2006 SP1 或 Internet Information Server 7.0、7.5 或8.0，且應用程式要求路由 (IIS ARR) 做為反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="49f1f-123">You can use Microsoft Forefront Threat Management Gateway 2010, Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, or Internet Information Server 7.0, 7.5 or 8.0 with Application Request Routing (IIS ARR) as a reverse proxy.</span></span> <span data-ttu-id="49f1f-124">這一節中的詳細步驟說明如何設定 Forefront Threat Management Gateway 2010，而且用於設定 ISA Server 2006 的步驟幾乎相同。</span><span class="sxs-lookup"><span data-stu-id="49f1f-124">The detailed steps in this section describe how to configure Forefront Threat Management Gateway 2010, and the steps for configuring ISA Server 2006 are almost identical.</span></span> <span data-ttu-id="49f1f-125">也會為 IIS ARR 提供指導方針。</span><span class="sxs-lookup"><span data-stu-id="49f1f-125">Guidance is also provided for IIS ARR.</span></span> <span data-ttu-id="49f1f-126">如果您使用其他的反向 Proxy，請參閱該產品的文件，並將此處定義的需求對應至其他反向 Proxy 中的關聯功能。</span><span class="sxs-lookup"><span data-stu-id="49f1f-126">If you are using a different reverse proxy, consult the documentation for that product and map the requirements defined here to the associated features in other reverse proxies.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="49f1f-127">Internet Information Server 應用程式要求路由 (IIS ARR) 是針對 Lync Server 2010 和 Lync Server 2013 實施反向 proxy 的經過完整測試及支援的選項。</span><span class="sxs-lookup"><span data-stu-id="49f1f-127">Internet Information Server Application Request Routing (IIS ARR) is a fully tested and supported option for implementing a reverse proxy for Lync Server 2010 and Lync Server 2013.</span></span> <span data-ttu-id="49f1f-128">在2012年11月，Microsoft 未 ForeFront 威脅管理閘道2010或 TMG 的授權銷售。</span><span class="sxs-lookup"><span data-stu-id="49f1f-128">In November, 2012, Microsoft ceased license sales of ForeFront Threat Management Gateway 2010, or TMG.</span></span> <span data-ttu-id="49f1f-129">TMG 仍是完全支援的產品，仍然可在協力廠商銷售的裝置上銷售。</span><span class="sxs-lookup"><span data-stu-id="49f1f-129">TMG is still a fully supported product, and is still available for sale on appliances sold by third parties.</span></span> <span data-ttu-id="49f1f-130">此外，許多協力廠商硬體負載平衡器和防火牆都提供反向 proxy 支援。</span><span class="sxs-lookup"><span data-stu-id="49f1f-130">Also, many third party hardware load balancers and firewalls provide reverse proxy support.</span></span> <span data-ttu-id="49f1f-131">如需提供反向 proxy 功能的硬體負載平衡器和防火牆，請諮詢您的廠商，以取得如何設定其產品以提供 Lync Server 的反向 proxy 支援的特定指示。</span><span class="sxs-lookup"><span data-stu-id="49f1f-131">For hardware load balancers and firewalls that provide reverse proxy features, check with your vendor for specific instructions on how to configure their product to provide reverse proxy support for Lync Server.</span></span> <span data-ttu-id="49f1f-132">您也可以查看已將產品的檔提交至 Microsoft 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="49f1f-132">You can also view third parties that have submitted documentation for their product to Microsoft.</span></span> <span data-ttu-id="49f1f-133">支援由協力廠商提供，以供其解決方案使用。</span><span class="sxs-lookup"><span data-stu-id="49f1f-133">Support is provided by the third party for their solution.</span></span> <span data-ttu-id="49f1f-134">若要查看提供解決方案時使用中的協力廠商，請參閱<A href="https://go.microsoft.com/fwlink/?linkid=268730">Microsoft Lync 的基礎結構限定</A>。</span><span class="sxs-lookup"><span data-stu-id="49f1f-134">To see third parties that are active in providing solutions, see <A href="https://go.microsoft.com/fwlink/?linkid=268730">Infrastructure qualified for Microsoft Lync</A>.</span></span>



</div>

<span data-ttu-id="49f1f-135">下列主題及程式使用 Forefront 威脅管理閘道2010和 IIS ARR 做為部署及設定程式的基礎。</span><span class="sxs-lookup"><span data-stu-id="49f1f-135">The following topics and procedures use Forefront Threat Management Gateway 2010 and IIS ARR as the basis for the deployment and configuration procedures.</span></span>

  - [<span data-ttu-id="49f1f-136">設定 Lync Server 2013 的 web 伺服器陣列 Fqdn</span><span class="sxs-lookup"><span data-stu-id="49f1f-136">Configure web farm FQDNs for Lync Server 2013</span></span>](lync-server-2013-configure-web-farm-fqdns.md)

  - [<span data-ttu-id="49f1f-137">在 Lync Server 2013 中設定網路介面卡</span><span class="sxs-lookup"><span data-stu-id="49f1f-137">Configure network adapters in Lync Server 2013</span></span>](lync-server-2013-configure-network-adapters.md)

  - [<span data-ttu-id="49f1f-138">在 Lync Server 2013 中要求和設定反向 HTTP proxy 的憑證</span><span class="sxs-lookup"><span data-stu-id="49f1f-138">Request and configure a certificate for your reverse HTTP proxy in Lync Server 2013</span></span>](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md)

  - [<span data-ttu-id="49f1f-139">在 Lync Server 2013 中設定單一內部集區的 web 發佈規則</span><span class="sxs-lookup"><span data-stu-id="49f1f-139">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>](lync-server-2013-configure-web-publishing-rules-for-a-single-internal-pool.md)

  - [<span data-ttu-id="49f1f-140">在 Lync Server 2013 中驗證或設定 IIS 虛擬目錄上的驗證和憑證</span><span class="sxs-lookup"><span data-stu-id="49f1f-140">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>](lync-server-2013-verify-or-configure-authentication-and-certification-on-iis-virtual-directories.md)

  - [<span data-ttu-id="49f1f-141">在 Lync Server 2013 中建立反向 proxy 伺服器的 DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="49f1f-141">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

  - [<span data-ttu-id="49f1f-142">在 Lync Server 2013 中驗證是否透過您的反向 proxy 進行存取</span><span class="sxs-lookup"><span data-stu-id="49f1f-142">Verify access through your reverse proxy in Lync Server 2013</span></span>](lync-server-2013-verify-access-through-your-reverse-proxy.md)

<div>

## <a name="before-you-begin"></a><span data-ttu-id="49f1f-143">開始之前</span><span class="sxs-lookup"><span data-stu-id="49f1f-143">Before You Begin</span></span>

<span data-ttu-id="49f1f-144">若要順利將 Forefront Threat Management Gateway 2010 部署成您的反向 Proxy，您必須安裝及設定伺服器，並使用 Forefront Threat Management Gateway 2010 文件中定義的先決條件和硬體需求。</span><span class="sxs-lookup"><span data-stu-id="49f1f-144">To successfully deploy Forefront Threat Management Gateway 2010 as your reverse proxy, you need to setup and configure a server, using the prerequisites and hardware requirements defined in the Forefront Threat Management Gateway 2010 documentation.</span></span> <span data-ttu-id="49f1f-145">請參閱下列主題設定為正確地設定硬體，並在伺服器上安裝 Forefront 威脅管理閘道2010，再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="49f1f-145">See the following topic set to properly configure the hardware and to install Forefront Threat Management Gateway 2010 on the server before proceeding.</span></span>

  - <span></span>  
    [<span data-ttu-id="49f1f-146">Forefront Threat Management Gateway (TMG) 2010</span><span class="sxs-lookup"><span data-stu-id="49f1f-146">Forefront Threat Management Gateway (TMG) 2010</span></span>](https://go.microsoft.com/fwlink/?linkid=291292)

  - <span></span>  
    [<span data-ttu-id="49f1f-147">Forefront TMG 2010 硬體建議</span><span class="sxs-lookup"><span data-stu-id="49f1f-147">Forefront TMG 2010 hardware recommendations</span></span>](https://go.microsoft.com/fwlink/?linkid=291293)

<span data-ttu-id="49f1f-148">若要將 IIS ARR 成功部署為反向 proxy，請參閱下列主題以設定硬體和必要條件軟體。</span><span class="sxs-lookup"><span data-stu-id="49f1f-148">To successfully deploy IIS ARR as your reverse proxy, review the following topics to configure the hardware and the prerequisite software.</span></span>

  - <span></span>  
    <span data-ttu-id="49f1f-149">若要在 Windows Server 2008 或 Windows Server 2008 R2 上安裝 IIS，請參閱[在 Windows server 2008 或 Windows server 2008 r2 上安裝 iis 7](https://go.microsoft.com/fwlink/?linkid=291296)</span><span class="sxs-lookup"><span data-stu-id="49f1f-149">To install IIS on Windows Server 2008 or Windows Server 2008 R2, see [Installing IIS 7 on Windows Server 2008 or Windows Server 2008 R2](https://go.microsoft.com/fwlink/?linkid=291296)</span></span>

  - <span></span>  
    <span data-ttu-id="49f1f-150">若要在 Windows Server 2012 上安裝 IIS，請參閱[在 Windows server 2012 上安裝 iis 8](https://go.microsoft.com/fwlink/?linkid=291297) 。</span><span class="sxs-lookup"><span data-stu-id="49f1f-150">To install IIS on Windows Server 2012, see [Installing IIS 8 on Windows Server 2012](https://go.microsoft.com/fwlink/?linkid=291297)</span></span>

  - <span></span>  
    <span data-ttu-id="49f1f-151">若要在 Windows Server 2012 R2 上安裝 IIS，請參閱[在 Windows server 2012 R2 上安裝 iis 8.5](https://go.microsoft.com/fwlink/?linkid=330687)</span><span class="sxs-lookup"><span data-stu-id="49f1f-151">To install IIS on Windows Server 2012 R2, see [Installing IIS 8.5 on Windows Server 2012 R2](https://go.microsoft.com/fwlink/?linkid=330687)</span></span>

  - <span></span>  
    <span data-ttu-id="49f1f-152">若要下載 IIS 的應用程式要求路由分機分機，請依照[應用程式要求路由傳送第 2.5](https://go.microsoft.com/fwlink/?linkid=291298)版的指示下載</span><span class="sxs-lookup"><span data-stu-id="49f1f-152">To download the Application Request Routing extension for IIS, follow the instructions at [Application Request Routing v2.5 Download](https://go.microsoft.com/fwlink/?linkid=291298)</span></span>

  - <span></span>  
    <span data-ttu-id="49f1f-153">若要安裝 ARR，請參閱[安裝應用程式要求路由第2版](https://go.microsoft.com/fwlink/?linkid=291299)時的指示</span><span class="sxs-lookup"><span data-stu-id="49f1f-153">To install ARR, for the instructions at [Install Application Request Routing Version 2](https://go.microsoft.com/fwlink/?linkid=291299)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="49f1f-154">目前發佈的指令是用於 ARR 2.0。</span><span class="sxs-lookup"><span data-stu-id="49f1f-154">The instructions currently posted are for ARR 2.0.</span></span> <span data-ttu-id="49f1f-155">若要安裝分機號碼，這兩種版本沒有區別。</span><span class="sxs-lookup"><span data-stu-id="49f1f-155">For installation of the extension, there is no difference between the two versions.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

