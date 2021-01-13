---
title: 在商務用 Skype Server 中部署 Edge Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 摘要：瞭解如何將 Edge Server 部署至您的商務用 Skype Server 環境。
ms.openlocfilehash: 8e23e157d4eb86f5b3d2bd5fa3ab3a54fd8aadc8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804373"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="c4028-103">在商務用 Skype Server 中部署 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c4028-103">Deploy Edge Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="c4028-104">**摘要：** 瞭解如何在商務用 Skype 伺服器環境中部署 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="c4028-104">**Summary:** Learn how to deploy Edge Servers into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="c4028-105">下列各節包含在商務 [用 Skype server 檔中檢查 Edge server 部署](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) 的商務用 Skype server 計畫後，應遵循的步驟。</span><span class="sxs-lookup"><span data-stu-id="c4028-105">The following sections contain steps that are meant to be followed after the Skype for Business Server [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) documentation has been reviewed.</span></span> <span data-ttu-id="c4028-106">部署步驟如下：</span><span class="sxs-lookup"><span data-stu-id="c4028-106">The deployment steps are as follows:</span></span>
  
- <span data-ttu-id="c4028-107">網路介面</span><span class="sxs-lookup"><span data-stu-id="c4028-107">Network interfaces</span></span>
    
- <span data-ttu-id="c4028-108">安裝</span><span class="sxs-lookup"><span data-stu-id="c4028-108">Installation</span></span>
    
- <span data-ttu-id="c4028-109">憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-109">Certificates</span></span>
    
- <span data-ttu-id="c4028-110">啟動 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c4028-110">Starting the Edge Servers</span></span>
    
## <a name="network-interfaces"></a><span data-ttu-id="c4028-111">網路介面</span><span class="sxs-lookup"><span data-stu-id="c4028-111">Network interfaces</span></span>

<span data-ttu-id="c4028-112">如規劃所述，您可以使用主控 Edge Server 的周邊網路中的 DNS，或在周邊網路中未設定 DNS，來設定網路介面。</span><span class="sxs-lookup"><span data-stu-id="c4028-112">As noted in Planning, you will either be configuring your network interface with DNS in the perimeter network hosting your Edge Servers, or without DNS in the perimeter network.</span></span>
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="c4028-113">在周邊網路中搭配 DNS 伺服器的介面設定</span><span class="sxs-lookup"><span data-stu-id="c4028-113">Interface configuration with DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="c4028-114">針對每一部 Edge Server 安裝兩個網路介面卡，一個用於內部對介面，另一個用於外部介面。</span><span class="sxs-lookup"><span data-stu-id="c4028-114">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4028-115">內部和外部子網不得彼此路由傳送。</span><span class="sxs-lookup"><span data-stu-id="c4028-115">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="c4028-116">您可以在外部介面上，設定下列 **其中一項** ：</span><span class="sxs-lookup"><span data-stu-id="c4028-116">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="c4028-117">a.</span><span class="sxs-lookup"><span data-stu-id="c4028-117">a.</span></span> <span data-ttu-id="c4028-118">外部周邊網路子網上的三個靜態 IP 位址，並將預設閘道指向外部防火牆的內部介面。</span><span class="sxs-lookup"><span data-stu-id="c4028-118">Three static IP addresses on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="c4028-119">設定配接器的 DNS 設定，使其指向一對周邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c4028-119">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
   <span data-ttu-id="c4028-120">b.</span><span class="sxs-lookup"><span data-stu-id="c4028-120">b.</span></span> <span data-ttu-id="c4028-121">外部周邊網路子網上的一個靜態 IP 位址，將預設閘道指向外部防火牆的內部介面。</span><span class="sxs-lookup"><span data-stu-id="c4028-121">One static IP address on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="c4028-122">設定配接器的 DNS 設定，使其指向一對周邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c4028-122">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span> <span data-ttu-id="c4028-123">只有在您先前已設定拓撲在埠指派中具有非標準值時，才可接受此設定，這會在 [ [建立商務用 Skype Server 的 Edge 拓撲](create-your-edge-topology.md) ] 文章仲介紹。</span><span class="sxs-lookup"><span data-stu-id="c4028-123">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="c4028-124">在您的內部周邊網路子網上，設定一個靜態 IP，但不要設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="c4028-124">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="c4028-125">設定配接器 DNS 設定，使其指向至少一部 DNS 伺服器，但最好是一對周邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c4028-125">Configure the adaptor DNS settings to point to at least one DNS server, but preferably a pair of perimeter DNS servers.</span></span>
    
4. <span data-ttu-id="c4028-126">在內部介面上建立持續性靜態路由，以傳送用戶端、商務用 Skype 伺服器和 Exchange 整合通訊 (UM) 伺服器所在的所有內部網路。</span><span class="sxs-lookup"><span data-stu-id="c4028-126">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="c4028-127">周邊網路中沒有 DNS 伺服器的介面設定</span><span class="sxs-lookup"><span data-stu-id="c4028-127">Interface configuration without DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="c4028-128">針對每一部 Edge Server 安裝兩個網路介面卡，一個用於內部對介面，另一個用於外部介面。</span><span class="sxs-lookup"><span data-stu-id="c4028-128">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c4028-129">內部和外部子網不得彼此路由傳送。</span><span class="sxs-lookup"><span data-stu-id="c4028-129">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="c4028-130">您可以在外部介面上，設定下列 **其中一項** ：</span><span class="sxs-lookup"><span data-stu-id="c4028-130">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="c4028-131">a.</span><span class="sxs-lookup"><span data-stu-id="c4028-131">a.</span></span> <span data-ttu-id="c4028-132">外部周邊網路子網上的三個靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4028-132">Three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="c4028-133">您也需要設定外部介面上的預設閘道，例如，將網際網路對向路由器或外部防火牆定義為預設閘道。</span><span class="sxs-lookup"><span data-stu-id="c4028-133">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="c4028-134">設定配接器 DNS 設定以指向外部 DNS 伺服器，理想的是一對外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c4028-134">Configure the adapter DNS settings to point to an external DNS server, ideally a pair of external DNS servers.</span></span>
    
   <span data-ttu-id="c4028-135">b.</span><span class="sxs-lookup"><span data-stu-id="c4028-135">b.</span></span> <span data-ttu-id="c4028-136">外部周邊網路子網上的一個靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c4028-136">One static IP address on the external perimeter network subnet.</span></span> <span data-ttu-id="c4028-137">您也需要設定外部介面上的預設閘道，例如，將網際網路對向路由器或外部防火牆定義為預設閘道。</span><span class="sxs-lookup"><span data-stu-id="c4028-137">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="c4028-138">設定配接器 DNS 設定以指向外部 DNS 伺服器，或理想一對外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c4028-138">Configure the adapter DNS settings to point to an external DNS server, or ideally a pair of external DNS servers.</span></span> <span data-ttu-id="c4028-139">只有在您先前已設定拓撲在埠指派中具有非標準值時，才可接受此設定，這會在 [ [建立商務用 Skype Server 的 Edge 拓撲](create-your-edge-topology.md) ] 文章仲介紹。</span><span class="sxs-lookup"><span data-stu-id="c4028-139">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="c4028-140">在您的內部周邊網路子網上，設定一個靜態 IP，但不要設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="c4028-140">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="c4028-141">同時將配接器 DNS 設定保留空白。</span><span class="sxs-lookup"><span data-stu-id="c4028-141">Also leave the adapter DNS settings empty.</span></span>
    
4. <span data-ttu-id="c4028-142">在內部介面上建立持續性靜態路由，以傳送用戶端、商務用 Skype 伺服器和 Exchange 整合通訊 (UM) 伺服器所在的所有內部網路。</span><span class="sxs-lookup"><span data-stu-id="c4028-142">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
5. <span data-ttu-id="c4028-143">編輯每一部 Edge Server 上的主機檔案，以包含下一個躍點伺服器或虛擬 IP (VIP) 的記錄。</span><span class="sxs-lookup"><span data-stu-id="c4028-143">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP).</span></span> <span data-ttu-id="c4028-144">這項記錄會是您在拓撲產生器中設定為 Edge Server 下一個躍點位址的 Director、Standard Edition 伺服器或前端集區。</span><span class="sxs-lookup"><span data-stu-id="c4028-144">This record will be the Director, Standard Edition server or Front End pool you configured as the Edge Server next hop address in Topology Builder.</span></span> <span data-ttu-id="c4028-145">如果您是使用 DNS 負載平衡，請在下一個躍點集區的每個成員中包含一行。</span><span class="sxs-lookup"><span data-stu-id="c4028-145">If you're using DNS load balancing, include a line for each member of the next hop pool.</span></span>
    
## <a name="installation"></a><span data-ttu-id="c4028-146">安裝</span><span class="sxs-lookup"><span data-stu-id="c4028-146">Installation</span></span>

<span data-ttu-id="c4028-147">若要順利完成這些步驟，您必須遵循為 [商務用 Skype Server 文章建立 Edge 拓撲](create-your-edge-topology.md) 中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c4028-147">To complete these steps successfully, you will need to have followed the steps in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
  
1. <span data-ttu-id="c4028-148">使用本機系統管理員群組中的帳戶，登入已設定 Edge Server role 的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c4028-148">Log onto the server you've been configuring for the Edge Server role with an account that's in the local Administrator's group.</span></span>
    
2. <span data-ttu-id="c4028-149">您需要在此機器上的 Edge Server 拓撲檔結束時複製您複製的拓撲設定檔。</span><span class="sxs-lookup"><span data-stu-id="c4028-149">You'll need the topology configuration file you copied out at the end of the Edge Server Topology documentation on this machine.</span></span> <span data-ttu-id="c4028-150">存取您在 (上放置該設定檔的外部媒體，如 USB 磁片磁碟機或共用) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-150">Access the external media you placed that configuration file on (like a USB drive or share).</span></span>
    
3. <span data-ttu-id="c4028-151">啟動 **部署嚮導**。</span><span class="sxs-lookup"><span data-stu-id="c4028-151">Start the **Deployment Wizard**.</span></span>
    
4. <span data-ttu-id="c4028-152">在嚮導開啟之後，按一下 [ **安裝或更新商務用 Skype Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-152">Once the wizard opens, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="c4028-153">嚮導會執行檢查，以查看是否有任何已安裝的專案。</span><span class="sxs-lookup"><span data-stu-id="c4028-153">The wizard will run checks to see if anything's already installed.</span></span> <span data-ttu-id="c4028-154">當您第一次執行該嚮導時，您會想要從 **步驟1開始。安裝本機設定存放區。**</span><span class="sxs-lookup"><span data-stu-id="c4028-154">As this is the first time running the wizard, you'll want to start at **Step 1. Install Local Configuration Store.**</span></span>
    
6. <span data-ttu-id="c4028-155">隨即會出現 [ **設定中央管理存放區的本機複本** ] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c4028-155">The **Configure Local Replica of Central Management store** dialog will appear.</span></span> <span data-ttu-id="c4028-156">您必須按一下 [ **從檔案匯入] (為 Edge server) 所建議的** 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4028-156">You need to click **Import from a file (Recommended for Edge Servers)**.</span></span>
    
7. <span data-ttu-id="c4028-157">在這裡，流覽至您先前匯出的拓撲位置，選取 .zip 檔案，按一下 [ **開啟**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-157">From here, browse to the location of the topology you exported previously, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="c4028-158">部署嚮導會讀取設定檔，並將 XML 設定檔寫入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c4028-158">The Deployment Wizard will read the configuration file and write the XML configuration file to the local computer.</span></span>
    
9. <span data-ttu-id="c4028-159">**[執行命令]** 程序完成後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-159">After the **Executing Commands** process is finished, click **Finish**.</span></span>
    
10. <span data-ttu-id="c4028-160">在 [部署嚮導] 中，按一下 [ **步驟 2]。安裝或移除商務用 Skype Server 元件**。</span><span class="sxs-lookup"><span data-stu-id="c4028-160">In the Deployment Wizard, click **Step 2. Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="c4028-161">然後，該嚮導將安裝已儲存在本機電腦上的 XML 設定檔中所指定的商務用 Skype 伺服器 Edge 元件。</span><span class="sxs-lookup"><span data-stu-id="c4028-161">The wizard will then install the Skype for Business Server Edge components specified in the XML configuration file that's been stored on the local computer.</span></span>
    
11. <span data-ttu-id="c4028-162">安裝完成後，您可以移至下方的 **憑證** 區段中的步驟。</span><span class="sxs-lookup"><span data-stu-id="c4028-162">Once the installation's complete, you can move onto the steps in the **Certificates** section below.</span></span>
    
## <a name="certificates"></a><span data-ttu-id="c4028-163">憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-163">Certificates</span></span>

<span data-ttu-id="c4028-164">Edge Server 的憑證需求可在 Edge 憑證規劃檔中找到。</span><span class="sxs-lookup"><span data-stu-id="c4028-164">The certificate requirements for the Edge Server can be found in the Edge Certificate Planning documentation.</span></span> <span data-ttu-id="c4028-165">以下是設定憑證的步驟。</span><span class="sxs-lookup"><span data-stu-id="c4028-165">The steps for setting up certificates are below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c4028-166">執行憑證嚮導時，您必須以具有您要使用之憑證範本類型之正確許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c4028-166">When running the Certificate Wizard, you need to be logged in as an account with the correct permissions for the type of certificate template you're going to use.</span></span> <span data-ttu-id="c4028-167">根據預設，商務用 Skype 伺服器憑證要求即將使用網頁伺服器憑證範本。</span><span class="sxs-lookup"><span data-stu-id="c4028-167">By default, a Skype for Business Server certificate request is going to use the Web Server certificate template.</span></span> <span data-ttu-id="c4028-168">如果您是以 RTCUniversalServerAdmins 群組成員的帳戶登入，以透過此範本要求憑證，請加倍檢查，確定已將「註冊」許可權指派給群組，以使用該範本。</span><span class="sxs-lookup"><span data-stu-id="c4028-168">If you're logged in with an account that's a member of the RTCUniversalServerAdmins group to request a certificate via this template, double-check to make sure the group's been assigned the Enroll permissions to use that template.</span></span> 
  
### <a name="internal-edge-interface-certificates"></a><span data-ttu-id="c4028-169">內部 Edge 介面憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-169">Internal Edge interface certificates</span></span>

 
### <a name="1-download-or-export-the-ca-certification-chain"></a><span data-ttu-id="c4028-170">1. 下載或匯出 CA 憑證鏈</span><span class="sxs-lookup"><span data-stu-id="c4028-170">1. Download or export the CA certification chain</span></span>

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a><span data-ttu-id="c4028-171">&nbsp;&nbsp;&nbsp; 單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-171">&nbsp;&nbsp;&nbsp; a.</span></span> <span data-ttu-id="c4028-172">使用 certsrv 網站下載</span><span class="sxs-lookup"><span data-stu-id="c4028-172">Download using certsrv web site</span></span>

<span data-ttu-id="c4028-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="c4028-174">以本機 Administrators 群組成員的身分，登入內部網路中的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c4028-174">Log into a Skype for Business Server in your internal network as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="c4028-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第二。</span><span class="sxs-lookup"><span data-stu-id="c4028-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="c4028-176">開啟 [ **開始**] 及 [ **執行** (] 或 [ **搜尋** 並 **執行** ) ]，然後輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="c4028-176">Open up **Start**, and **Run** (or **Search** and **Run** ), and then type the following:</span></span>
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

<span data-ttu-id="c4028-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如：</span><span class="sxs-lookup"><span data-stu-id="c4028-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For example:</span></span>
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

<span data-ttu-id="c4028-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第三。</span><span class="sxs-lookup"><span data-stu-id="c4028-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="c4028-179">在發證 CA 的 certsrv 網頁上，按一下 [ **選取任務**] 底下的 [ **下載 CA 憑證、憑證鏈或 CRL**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-179">On the issuing CA's certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
    
<span data-ttu-id="c4028-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;四。</span><span class="sxs-lookup"><span data-stu-id="c4028-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="c4028-181">在 [ **下載 ca 憑證、憑證鏈或 CRL**] 底下，按一下 [ **下載 ca 憑證鏈**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-181">Under **Download a CA certificate, certificate chain, or CRL**, click **Download CA certificate chain**.</span></span>
    
<span data-ttu-id="c4028-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;V。</span><span class="sxs-lookup"><span data-stu-id="c4028-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="c4028-183">在 [檔案 **下載** ] 方塊中，按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-183">In the **File Download** box, click **Save**.</span></span>
    
<span data-ttu-id="c4028-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;六。</span><span class="sxs-lookup"><span data-stu-id="c4028-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="c4028-185">將. p7b 檔案儲存至伺服器的硬碟磁碟機上，然後將它複製到每一部 Edge Server 上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4028-185">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each of your Edge Servers.</span></span>
    
### <a name="nbspnbspnbspb-export-using-mmc"></a><span data-ttu-id="c4028-186">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-186">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-187">使用 MMC 匯出</span><span class="sxs-lookup"><span data-stu-id="c4028-187">Export using MMC</span></span>

<span data-ttu-id="c4028-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="c4028-189">您可以使用 MMC 從任何已加入網域的機器匯出 CA 的根憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-189">You can export the CA root certificate from any domain joined machine using the MMC.</span></span> <span data-ttu-id="c4028-190">移至 [ **開始** ] 和 [ **執行**]，或開啟 [ **搜尋**]，然後輸入 **MMC** 加以開啟。</span><span class="sxs-lookup"><span data-stu-id="c4028-190">Either go to **Start** and **Run**, or open **Search**, and type **MMC** to open.</span></span>
    
<span data-ttu-id="c4028-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第二。</span><span class="sxs-lookup"><span data-stu-id="c4028-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="c4028-192">在 MMC 主控台中，按一下 [檔案]，**然後按一下 [\*\*\*\*新增/移除嵌入式管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-192">In the MMC console, click **File**, and then click **Add/Remove Snap-In**.</span></span>
    
<span data-ttu-id="c4028-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第三。</span><span class="sxs-lookup"><span data-stu-id="c4028-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="c4028-194">從 [ **新增或移除嵌入式管理單元** ] 對話方塊清單中，選擇 [ **憑證**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-194">From the **Add or Remove Snap-ins** dialog list, choose **Certificates**, and then click **Add**.</span></span> <span data-ttu-id="c4028-195">出現提示時，請選取 [ **電腦帳戶**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-195">When prompted, select **Computer Account**, and then **Next**.</span></span> <span data-ttu-id="c4028-196">在 [ **選取電腦** ] 對話方塊中，選取 [ **本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-196">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="c4028-197">按一下 **[完成]**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-197">Click **Finish**, and then **OK**.</span></span>
    
<span data-ttu-id="c4028-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;四。</span><span class="sxs-lookup"><span data-stu-id="c4028-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="c4028-199">展開 [ **憑證 (本機電腦])**。</span><span class="sxs-lookup"><span data-stu-id="c4028-199">Expand **Certificates (Local computer)**.</span></span> <span data-ttu-id="c4028-200">展開 **[受信任的根憑證授權單位]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-200">Expand **Trusted Root Certification Authorities**.</span></span> <span data-ttu-id="c4028-201">選取 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-201">Select **Certificates**.</span></span>
    
<span data-ttu-id="c4028-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;V。</span><span class="sxs-lookup"><span data-stu-id="c4028-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="c4028-203">按一下您的 CA 所簽發的根憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-203">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="c4028-204">以滑鼠右鍵按一下憑證，選擇功能表上的 [ **所有** 工作]，然後選取 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-204">Right-click the certificate, choose **All Tasks** on the menu, and then select **Export**.</span></span>
    
<span data-ttu-id="c4028-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;六。</span><span class="sxs-lookup"><span data-stu-id="c4028-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="c4028-206">[ **憑證匯出] 嚮導** 隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="c4028-206">The **Certificate Export Wizard** opens.</span></span> <span data-ttu-id="c4028-207">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-207">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;七。</span><span class="sxs-lookup"><span data-stu-id="c4028-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii.</span></span> <span data-ttu-id="c4028-209">在 [ **匯出檔案格式** ] 對話方塊中，選擇您想要匯出的格式。</span><span class="sxs-lookup"><span data-stu-id="c4028-209">On the **Export File Format** dialog, choose the format you want to export to.</span></span> <span data-ttu-id="c4028-210">建議是 **加密郵件語法 Standard-PKCS #7 憑證 (P7b)**。</span><span class="sxs-lookup"><span data-stu-id="c4028-210">Our recommendation is **Cryptographic Message Syntax Standard - PKCS #7 Certificates (P7b)**.</span></span> <span data-ttu-id="c4028-211">如果您也選擇這種方式，請務必同時選取 [ **如果可能的話，包含憑證路徑中的所有憑證** ] 核取方塊，因為這樣也會匯出憑證鏈，包括根 CA 憑證和任何中級憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-211">If that's your choice as well, remember to also select the **Include all certificates in the certification path if possible** checkbox, as this will also export the certificate chain, including the root CA certificate and any Intermediate certificates.</span></span> <span data-ttu-id="c4028-212">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-212">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;八。</span><span class="sxs-lookup"><span data-stu-id="c4028-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii.</span></span> <span data-ttu-id="c4028-214">在 [ **要匯出的** 檔案] 對話方塊的 [檔案名] 專案中，輸入路徑和檔案名 (預設副檔名為已匯出憑證的 p7b) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-214">On the **File to Export** dialog, in the file name entry, type a path and file name (the default extension would be .p7b) for the exported certificate.</span></span> <span data-ttu-id="c4028-215">如果您很容易，請選擇 [ **流覽]** 按鈕，移至您要儲存匯出憑證的位置，然後在這裡命名匯出的憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-215">If it's easier on you, choose the **Browse** button to go to the location you want to save the exported certificate to, and name the exported certificate here.</span></span> <span data-ttu-id="c4028-216">按一下 [ **儲存**]，然後在 **[下一步]** 準備就緒。</span><span class="sxs-lookup"><span data-stu-id="c4028-216">Click **Save**, and then **Next** when you're ready.</span></span>
    
<span data-ttu-id="c4028-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;九。</span><span class="sxs-lookup"><span data-stu-id="c4028-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix.</span></span> <span data-ttu-id="c4028-218">請複查您的動作摘要，然後按一下 **[完成]** 完成憑證的匯出。</span><span class="sxs-lookup"><span data-stu-id="c4028-218">Review the summary of your actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="c4028-219">按一下 **[確定]** 確認成功的匯出。</span><span class="sxs-lookup"><span data-stu-id="c4028-219">Click **OK** to confirm the successful export.</span></span>
    
<span data-ttu-id="c4028-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;X。</span><span class="sxs-lookup"><span data-stu-id="c4028-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x.</span></span> <span data-ttu-id="c4028-221">將. p7b 檔複製到每一部 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="c4028-221">Copy the .p7b file to each of your Edge Servers.</span></span>
    
### <a name="2-import-the-ca-certification-chain"></a><span data-ttu-id="c4028-222">2. 匯入 CA 憑證鏈</span><span class="sxs-lookup"><span data-stu-id="c4028-222">2. Import the CA certification chain</span></span>

<span data-ttu-id="c4028-223">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-223">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-224">在每一部 Edge Server 上，開啟 MMC (選擇 [ **開始** ] 與 [ **執行**] 或 [ **搜尋**]，然後輸入 **mmc** ，以開啟) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-224">On each Edge Server, open the MMC (choose **Start** and **Run**, or **Search**, and type **MMC** to open).</span></span>
    
<span data-ttu-id="c4028-225">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-225">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-226">**在 [檔案**] 功能表上，按一下 [**新增/移除嵌入式管理單元**]，然後選擇 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-226">On the **File** menu, click **Add/Remove Snap-in**, and then choose **Add**.</span></span>
    
<span data-ttu-id="c4028-227">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-227">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-228">在 [ **新增或移除嵌入式管理單元** ] 方塊中，按一下 [ **憑證**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-228">In the **Add or Remove Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
    
<span data-ttu-id="c4028-229">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-229">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-230">在 **[憑證嵌入式管理單元]** 對話方塊中，按一下 **[電腦帳戶]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-230">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
    
<span data-ttu-id="c4028-231">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-231">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-232">在 [ **選取電腦** ] 對話方塊中，確定已選取 [本機電腦] 的 [ **(此主控台執行的電腦)** ] 核取方塊，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-232">In the **Select Computer** dialog box, ensure that the **Local Computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
    
<span data-ttu-id="c4028-233">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-233">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-234">按一下 [ **關閉**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-234">Click **Close**, and then **OK**.</span></span>
    
<span data-ttu-id="c4028-235">&nbsp;&nbsp;&nbsp;G。</span><span class="sxs-lookup"><span data-stu-id="c4028-235">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="c4028-236">在主控台樹中，依序展開 [**憑證 (本機電腦])** 中，以滑鼠右鍵按一下 **[信任的根憑證授權** 單位]，移至 [**所有** 工作]，然後按一下 [匯 **入**</span><span class="sxs-lookup"><span data-stu-id="c4028-236">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, go to **All Tasks**, and then click **Import**.</span></span>
    
<span data-ttu-id="c4028-237">&nbsp;&nbsp;&nbsp;H。</span><span class="sxs-lookup"><span data-stu-id="c4028-237">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="c4028-238">在出現的嚮導中，在 [ **要匯入** 的檔案] textbox 中指定憑證的檔案名 (您在上一節) 中您所擁有的 p7b 檔案名稱。</span><span class="sxs-lookup"><span data-stu-id="c4028-238">In the wizard that appears, in the **File to Import** textbox, specify the file name of the certificate (the name you gave the .p7b file in the previous section).</span></span> <span data-ttu-id="c4028-239">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-239">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-240">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-240">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="c4028-241">將 [選項按鈕] 保留在 **[將所有憑證放入] 下的存放區中，因為應該選取受信任的根憑證授權單位單位** 。</span><span class="sxs-lookup"><span data-stu-id="c4028-241">Leave the radio button on **Place all certificates in the following store, as Trusted Root Certification Authorities** should be selected.</span></span> <span data-ttu-id="c4028-242">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-242">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-243">&nbsp;&nbsp;&nbsp;J。</span><span class="sxs-lookup"><span data-stu-id="c4028-243">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="c4028-244">查看摘要，然後按一下 **[完成]** 完成匯入。</span><span class="sxs-lookup"><span data-stu-id="c4028-244">Review the summary, and click **Finish** to complete the import.</span></span>
    
<span data-ttu-id="c4028-245">&nbsp;&nbsp;&nbsp;K。</span><span class="sxs-lookup"><span data-stu-id="c4028-245">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="c4028-246">這將需要針對您要部署的每一部 Edge Server 執行。</span><span class="sxs-lookup"><span data-stu-id="c4028-246">This will need to be done for every Edge Server you're deploying.</span></span>
    
### <a name="3-create-the-certificate-request"></a><span data-ttu-id="c4028-247">3. 建立憑證要求</span><span class="sxs-lookup"><span data-stu-id="c4028-247">3. Create the certificate request</span></span>

<span data-ttu-id="c4028-248">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-248">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-249">登入其中一部 Edge Server，啟動部署嚮導，然後在 [ **步驟3：要求、安裝或指派憑證**] 中，按一下 [ **執行** (**] 或 [** 指派憑證]，如果您已執行此嚮導) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-249">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates**, click **Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="c4028-250">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-250">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-251">在 [ **憑證要求** ] 頁面上，確定已選取 [ **內部 Edge 憑證** ]，然後按一下 [ **要求**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-251">On the **Certificate Request** page, ensure **Internal Edge Certificate** is selected, and click **Request**.</span></span>
    
<span data-ttu-id="c4028-252">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-252">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-253">在 [ **延遲或立即要求** ] 頁面上，只要您可以從 Edge 環境存取其中一個，請選擇 [ **立即將要求傳送到線上憑證授權單位** ]，或是 **立即準備此要求，否則請稍後再傳送** 。</span><span class="sxs-lookup"><span data-stu-id="c4028-253">On the **Delayed or Immediate Requests** page, choose **Send the request immediately to an online certification authority** if you have access to one from your Edge environment, or **Prepare the request now, but send it later** otherwise.</span></span>
    
<span data-ttu-id="c4028-254">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-254">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-255">在 [ **憑證要求** 檔案] 頁面上，輸入檔案儲存位置的完整部分和檔案名 (例如 c:\SkypeInternalEdgeCert.cer) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-255">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="c4028-256">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-256">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-257">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-257">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-258">在 [ **指定替代的憑證範本** ] 頁面上，若要使用預設 WebServer 範本以外的範本，請選取 [對 **選取的憑證授權單位單位使用其他憑證範本** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c4028-258">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span> <span data-ttu-id="c4028-259">否則，不執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="c4028-259">Otherwise, do nothing.</span></span>
    
<span data-ttu-id="c4028-260">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-260">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-261">在 [名稱和安全性設定] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c4028-261">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="c4028-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   我。</span><span class="sxs-lookup"><span data-stu-id="c4028-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="c4028-263">在 [ **易記名稱**] 中，輸入憑證 (的顯示名稱，例如 [內部 Edge) ]。</span><span class="sxs-lookup"><span data-stu-id="c4028-263">In **Friendly name**, enter a display name for the certificate (such as Internal Edge).</span></span>
    
 <span data-ttu-id="c4028-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  第二。</span><span class="sxs-lookup"><span data-stu-id="c4028-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="c4028-265">在 [ **位長度**] 中，選擇您的位長度 (預設值為2048，您可以提高安全性，但會使效能降低) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-265">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="c4028-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  第三。</span><span class="sxs-lookup"><span data-stu-id="c4028-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="c4028-267">如果您需要可匯出的憑證，您必須勾選 [將 **憑證私密金鑰標示為可匯出** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c4028-267">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
 <span data-ttu-id="c4028-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  四。</span><span class="sxs-lookup"><span data-stu-id="c4028-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv.</span></span> <span data-ttu-id="c4028-269">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-269">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-270">&nbsp;&nbsp;&nbsp;G。</span><span class="sxs-lookup"><span data-stu-id="c4028-270">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="c4028-271">在 [ **組織資訊** ] 頁面上，輸入組織的名稱和組織單位 (OU) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-271">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="c4028-272">您可以輸入您的部門或部門 (它，例如) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-272">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="c4028-273">&nbsp;&nbsp;&nbsp;H。</span><span class="sxs-lookup"><span data-stu-id="c4028-273">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="c4028-274">在 [ **地理資訊** ] 頁面上，輸入您的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="c4028-274">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="c4028-275">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-275">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="c4028-276">在 [ **主體名稱/主體替代名稱** ] 頁面上，嚮導應該會自動填入此頁面。</span><span class="sxs-lookup"><span data-stu-id="c4028-276">On the **Subject Name/Subject Alternate Names** page, this should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="c4028-277">&nbsp;&nbsp;&nbsp;J。</span><span class="sxs-lookup"><span data-stu-id="c4028-277">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="c4028-278">在 [ **設定其他主體替代名稱** ] 頁面上，您需要新增任何所需的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="c4028-278">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="c4028-279">&nbsp;&nbsp;&nbsp;K。</span><span class="sxs-lookup"><span data-stu-id="c4028-279">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="c4028-280">在 [ **要求摘要** ] 頁面上，查看要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="c4028-280">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="c4028-281">如果您需要進行變更，請移回並立即執行。</span><span class="sxs-lookup"><span data-stu-id="c4028-281">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="c4028-282">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-282">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="c4028-283">然後按 **[下一步]** ，以產生您需要提供給 CA 的 CSR 檔案 (您也可以按一下 [ **查看記錄** 檔] 以查看憑證要求) 的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c4028-283">Then click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="c4028-284">&nbsp;&nbsp;&nbsp;平方米.</span><span class="sxs-lookup"><span data-stu-id="c4028-284">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="c4028-285">在產生要求之後，您可以按一下 [View] （ **查看** ）以查看憑證，然後按一下 **[完成** ] 以關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="c4028-285">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="c4028-286">您必須將 CSR 檔案的內容提供給您的 CA，這樣他們才可以在下一節中為您產生憑證，以匯入此電腦。</span><span class="sxs-lookup"><span data-stu-id="c4028-286">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    

### <a name="4-import-the-certificate"></a><span data-ttu-id="c4028-287">4. 匯入憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-287">4. Import the certificate</span></span>

<span data-ttu-id="c4028-288">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-288">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-289">以本機 Administrators 群組成員的身分登入至 Edge Server，而您在上一個程式中提出憑證要求。</span><span class="sxs-lookup"><span data-stu-id="c4028-289">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="c4028-290">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-290">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-291">在 [部署嚮導] 中的 [ **步驟 3] 旁邊。要求、安裝或指派憑證**，請按一下 [ **再執行一次**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-291">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="c4028-292">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-292">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-293">在 [ **可用憑證** 工作] 頁面上，按一下 [匯 **入憑證自 a]。P7b、.pfx 或 .cer** 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4028-293">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="c4028-294">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-294">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-295">在 [匯 **入憑證** ] 頁面上，輸入您在前一節中取得之憑證的完整路徑及檔案名 (，也可以按一下 **[流覽]** ，尋找並選擇) 的檔案。</span><span class="sxs-lookup"><span data-stu-id="c4028-295">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span>
    
<span data-ttu-id="c4028-296">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-296">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-297">若要匯入 Edge 集區其他成員的憑證，且憑證包含私密金鑰，請務必選取 [ **包含憑證私密金鑰的憑證** 檔案] 核取方塊，然後指定密碼。</span><span class="sxs-lookup"><span data-stu-id="c4028-297">If you're importing certificates for other members of your Edge pool, and your certificate contains a private key, be sure to select the **Certificate file that contains certificate's private key** check box, and specify the password.</span></span> <span data-ttu-id="c4028-298">按 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="c4028-298">Click **Next** to continue.</span></span>
    
<span data-ttu-id="c4028-299">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-299">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-300">在 [**摘要** ] 頁面上，按 **[下一步]** 您已確認資訊，並在成功匯入憑證後 **完成** 。</span><span class="sxs-lookup"><span data-stu-id="c4028-300">On the **Summary** page, click **Next** once you've confirmed the information, and **Finish** once the certificate is successfully imported.</span></span>
    
 
### <a name="5-export-the-certificate"></a><span data-ttu-id="c4028-301">5. 匯出憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-301">5. Export the certificate</span></span>

<span data-ttu-id="c4028-302">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-302">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-303">請確認您已登入已匯入憑證的 Edge Server，成為本機 Administrators 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c4028-303">Make sure you've logged onto the Edge Server you imported the certificate to previously, as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="c4028-304">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-304">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-305">按一下 [ **開始**]、[ **執行** (] 或 [開啟 **搜尋** ) ]，然後輸入 **MMC**。</span><span class="sxs-lookup"><span data-stu-id="c4028-305">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="c4028-306">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-306">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-307">在 MMC 主控台中，按一下 [檔案]，**然後按一下 [\*\*\*\*新增/移除嵌入式管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-307">From the MMC console, click **File**, and click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="c4028-308">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-308">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-309">在 [ **新增或移除嵌入式管理單元** ] 方塊中，按一下 [ **憑證**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-309">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="c4028-310">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-310">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-311">在 [ **憑證** 嵌入式管理單元] 對話方塊中，選擇 [ **電腦帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-311">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="c4028-312">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-312">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-313">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-313">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-314">在 [ **選取電腦** ] 對話方塊中，選取 [ **本機電腦： (此主控台執行的電腦])**。</span><span class="sxs-lookup"><span data-stu-id="c4028-314">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="c4028-315">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-315">Click **Finish**.</span></span> <span data-ttu-id="c4028-316">按一下 **[確定]**，然後完成 MMC 主控台的設定。</span><span class="sxs-lookup"><span data-stu-id="c4028-316">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="c4028-317">&nbsp;&nbsp;&nbsp;G。</span><span class="sxs-lookup"><span data-stu-id="c4028-317">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="c4028-318">按兩下 [ **憑證 (本機電腦])** 以展開憑證儲存區。</span><span class="sxs-lookup"><span data-stu-id="c4028-318">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="c4028-319">連按兩下 [ **個人**]，然後按一下 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-319">Double-click **Personal**, and then click **Certificates**.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="c4028-320">您可能在這裡，而且在本機電腦的憑證個人存放區中看不到任何憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-320">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="c4028-321">您不需要進行搜尋，如果該機碼不存在，則匯入的憑證沒有相關聯的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="c4028-321">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="c4028-322">請嘗試一次以上的要求和匯入步驟，如果您確定完全正確，請諮詢 CA 管理員或提供者。</span><span class="sxs-lookup"><span data-stu-id="c4028-322">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="c4028-323">&nbsp;&nbsp;&nbsp;H。</span><span class="sxs-lookup"><span data-stu-id="c4028-323">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="c4028-324">在本機電腦的 [ **憑證個人] 存放區** 中，以滑鼠右鍵按一下您要匯出的憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-324">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="c4028-325">從產生的功能表中選取 [ **所有** 工作]，然後按一下 [ **匯出**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-325">Select **All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="c4028-326">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-326">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="c4028-327">在 [憑證匯出精靈] 中，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="c4028-327">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="c4028-328">選取 **[是，匯出私密金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-328">Select **Yes, export the private key**.</span></span> <span data-ttu-id="c4028-329">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-329">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-330">&nbsp;&nbsp;&nbsp;J。</span><span class="sxs-lookup"><span data-stu-id="c4028-330">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="c4028-331">在 [ **匯出檔案格式** ] 對話方塊中，選取 [ **個人資訊交換-PKCS#12 (]。PFX)**，然後選取下列各項：</span><span class="sxs-lookup"><span data-stu-id="c4028-331">On the **Export File Formats** dialog, select **Personal Information Exchange - PKCS#12 (.PFX)**, and then select the following:</span></span>
    
<span data-ttu-id="c4028-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   我。</span><span class="sxs-lookup"><span data-stu-id="c4028-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="c4028-333">如有可能，請將所有憑證包含在憑證路徑中。</span><span class="sxs-lookup"><span data-stu-id="c4028-333">Include all certificates in the certification path, if possible.</span></span>
    
<span data-ttu-id="c4028-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   第二。</span><span class="sxs-lookup"><span data-stu-id="c4028-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii.</span></span> <span data-ttu-id="c4028-335">匯出所有延伸屬性。</span><span class="sxs-lookup"><span data-stu-id="c4028-335">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="c4028-336">如果匯出成功，**切勿** 選取 **[刪除私密金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-336">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="c4028-337">這表示您必須將憑證和私密金鑰重新導入至此 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="c4028-337">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="c4028-338">&nbsp;&nbsp;&nbsp;K。</span><span class="sxs-lookup"><span data-stu-id="c4028-338">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="c4028-339">如果您想要指派密碼來保護私密金鑰，您可以輸入私密金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="c4028-339">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="c4028-340">重新輸入密碼以加以確認，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-340">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="c4028-341">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-341">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="c4028-342">輸入匯出憑證的路徑和檔案名，並使用 **.pfx** 的副檔名。</span><span class="sxs-lookup"><span data-stu-id="c4028-342">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="c4028-343">您必須可以透過集區中的其他 Edge Server 存取該路徑，否則您必須使用外部媒體 (例如 u 盤) ）移動檔案。</span><span class="sxs-lookup"><span data-stu-id="c4028-343">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="c4028-344">作出選擇後，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="c4028-344">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="c4028-345">&nbsp;&nbsp;&nbsp;平方米.</span><span class="sxs-lookup"><span data-stu-id="c4028-345">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="c4028-346">在 [ **完成憑證匯出嚮導** ] 對話方塊中查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-346">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="c4028-347">&nbsp;&nbsp;&nbsp;\r\n.</span><span class="sxs-lookup"><span data-stu-id="c4028-347">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="c4028-348">在 [成功匯出] 對話方塊中，按一下 **[確定** ]。</span><span class="sxs-lookup"><span data-stu-id="c4028-348">Click **OK** in the successful export dialog.</span></span>
    
 
### <a name="6-assign-the-certificate"></a><span data-ttu-id="c4028-349">6. 指派憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-349">6. Assign the certificate</span></span>

<span data-ttu-id="c4028-350">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-350">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-351">在每一部 Edge Server 上，于 [部署嚮導] 中的 [ **步驟 3] 旁邊。要求、安裝或指派憑證**，請按一下 [ **再執行一次**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-351">On EACH Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="c4028-352">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-352">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-353">在 [ **可用憑證** 工作] 頁面上，按一下 [ **指派現有的憑證**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-353">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="c4028-354">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-354">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-355">在 [ **憑證指派** ] 頁面上，選取清單中的 [ **Edge Internal** ]。</span><span class="sxs-lookup"><span data-stu-id="c4028-355">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>
    
<span data-ttu-id="c4028-356">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-356">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-357">在 [ **憑證存放區** ] 頁面上，選取您為內部 Edge 匯入的憑證，以供先前區段中 () 。</span><span class="sxs-lookup"><span data-stu-id="c4028-357">On the **Certificate Store** page, select the certificate you've imported for the internal Edge (from the previous section).</span></span>
    
<span data-ttu-id="c4028-358">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-358">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-359">在 [ **憑證指派摘要** ] 頁面上，查看設定，然後按一下 **[下一步]** 指派憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-359">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="c4028-360">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-360">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-361">在精靈完成頁面中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-361">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="c4028-362">&nbsp;&nbsp;&nbsp;G。</span><span class="sxs-lookup"><span data-stu-id="c4028-362">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="c4028-363">當您完成此程式後，就可以在每一部 Edge Server 上開啟憑證 MMC 嵌入式管理單元，展開 [ **憑證 (本機電腦])**，展開 [ **個人**]，按一下 [ **憑證**]，然後確認 [詳細資料] 窗格中列出的是內部 Edge 憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-363">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each Edge Server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
### <a name="external-edge-interface-certificates"></a><span data-ttu-id="c4028-364">外部 Edge 介面憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-364">External Edge interface certificates</span></span>

 
### <a name="1-create-the-certificate-request"></a><span data-ttu-id="c4028-365">1. 建立憑證要求</span><span class="sxs-lookup"><span data-stu-id="c4028-365">1. Create the certificate request</span></span>

<span data-ttu-id="c4028-366">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-366">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-367">登入其中一部 Edge Server，啟動部署嚮導，然後在 [ **步驟3：要求、安裝或指派憑證** ] 中，按一下 [執行 (**] 或 [** 指派憑證]，如果您已執行此嚮導) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-367">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates, click Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="c4028-368">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-368">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-369">在 **[可用憑證工作]** 頁面上，按一下 **[建立新憑證要求]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-369">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>
    
<span data-ttu-id="c4028-370">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-370">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-371">在 [ **憑證要求** ] 頁面上，確定已選取 [ **外部邊緣憑證** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-371">On the **Certificate Request** page, ensure **External Edge Certificate** is selected, and click **Next**.</span></span>
    
<span data-ttu-id="c4028-372">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-372">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-373">在 [ **延遲或立即要求** ] 頁面上，按一下 **[立即準備此要求，但稍後再傳送**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-373">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>
    
<span data-ttu-id="c4028-374">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-374">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-375">在 [ **憑證要求** 檔案] 頁面上，輸入檔案儲存位置的完整部分和檔案名 (例如 c:\SkypeInternalEdgeCert.cer) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-375">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="c4028-376">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-376">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-377">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-377">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-378">在 [ **指定替代的憑證範本** ] 頁面上，若要使用預設 WebServer 範本以外的範本，請選取 [對 **選取的憑證授權單位單位使用其他憑證範本** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c4028-378">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>
    
<span data-ttu-id="c4028-379">&nbsp;&nbsp;&nbsp;G。</span><span class="sxs-lookup"><span data-stu-id="c4028-379">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="c4028-380">在 [名稱和安全性設定] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c4028-380">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="c4028-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   我。</span><span class="sxs-lookup"><span data-stu-id="c4028-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="c4028-382">在 [ **易記名稱**] 中，輸入憑證 (的顯示名稱，例如 [外部 Edge]) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-382">In **Friendly name**, enter a display name for the certificate (such as External Edge).</span></span>
    
 <span data-ttu-id="c4028-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  第二。</span><span class="sxs-lookup"><span data-stu-id="c4028-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="c4028-384">在 [ **位長度**] 中，選擇您的位長度 (預設值為2048，您可以提高安全性，但會使效能降低) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-384">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="c4028-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  第三。</span><span class="sxs-lookup"><span data-stu-id="c4028-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="c4028-386">如果您需要可匯出的憑證，您必須勾選 [將 **憑證私密金鑰標示為可匯出** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="c4028-386">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
  <span data-ttu-id="c4028-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 四。</span><span class="sxs-lookup"><span data-stu-id="c4028-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv.</span></span> <span data-ttu-id="c4028-388">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-388">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-389">&nbsp;&nbsp;&nbsp;H。</span><span class="sxs-lookup"><span data-stu-id="c4028-389">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="c4028-390">在 [ **組織資訊** ] 頁面上，輸入組織的名稱和組織單位 (OU) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-390">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="c4028-391">您可以輸入您的部門或部門 (它，例如) 。</span><span class="sxs-lookup"><span data-stu-id="c4028-391">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="c4028-392">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-392">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="c4028-393">在 [ **地理資訊** ] 頁面上，輸入您的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="c4028-393">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="c4028-394">&nbsp;&nbsp;&nbsp;J。</span><span class="sxs-lookup"><span data-stu-id="c4028-394">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="c4028-395">在 [ **主體名稱/主體替代名稱** ] 頁面上，嚮導應該會自動填入必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="c4028-395">On the **Subject Name/Subject Alternate Names** page, the needed information should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="c4028-396">&nbsp;&nbsp;&nbsp;K。</span><span class="sxs-lookup"><span data-stu-id="c4028-396">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="c4028-397">在 [ **主體別名] 上的 [SIP 網域設定] (SANs)** ] 頁面上，選取 [網域] 核取方塊，以新增 SIP。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="c4028-397">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, check the domain checkbox to add a sip.<sipdomain></span></span> <span data-ttu-id="c4028-398">專案的主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="c4028-398">entry to the subject alternative names list.</span></span>
    
<span data-ttu-id="c4028-399">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-399">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="c4028-400">在 [ **設定其他主體替代名稱** ] 頁面上，您需要新增任何所需的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="c4028-400">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="c4028-401">&nbsp;&nbsp;&nbsp;平方米.</span><span class="sxs-lookup"><span data-stu-id="c4028-401">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="c4028-402">在 [ **要求摘要** ] 頁面上，查看要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="c4028-402">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="c4028-403">如果您需要進行變更，請移回並立即執行。</span><span class="sxs-lookup"><span data-stu-id="c4028-403">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="c4028-404">&nbsp;&nbsp;&nbsp;\r\n.</span><span class="sxs-lookup"><span data-stu-id="c4028-404">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="c4028-405">當您準備好時，按 **[下一步]** 以產生您需要提供給 CA 的 CSR 檔案 (您也可以按一下 [ **查看記錄** 檔] 以查看憑證要求) 的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c4028-405">When you're ready, click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="c4028-406">&nbsp;&nbsp;&nbsp;複雜度.</span><span class="sxs-lookup"><span data-stu-id="c4028-406">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="c4028-407">在產生要求之後，您可以按一下 [View] （ **查看** ）以查看憑證，然後按一下 **[完成** ] 以關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="c4028-407">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="c4028-408">您必須將 CSR 檔案的內容提供給您的 CA，這樣他們才可以在下一節中為您產生憑證，以匯入此電腦。</span><span class="sxs-lookup"><span data-stu-id="c4028-408">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    
<span data-ttu-id="c4028-409">&nbsp;&nbsp;&nbsp;P。</span><span class="sxs-lookup"><span data-stu-id="c4028-409">&nbsp;&nbsp;&nbsp;p.</span></span> <span data-ttu-id="c4028-410"> (選用) 當您提交 CSR 的內容時，系統會要求您提供特定資訊，如下所示 (CAs 會有很大的不同，因此可能不需要這樣做) ：</span><span class="sxs-lookup"><span data-stu-id="c4028-410">(OPTIONAL) You may, when submitting the contents of the CSR, be asked for certain information, as follows (CAs vary greatly, so this may not be required):</span></span>
    
  - <span data-ttu-id="c4028-411">**Microsoft** 作為伺服器平臺</span><span class="sxs-lookup"><span data-stu-id="c4028-411">**Microsoft** as the server platform</span></span>
    
  - <span data-ttu-id="c4028-412">以 **IIS** 作為版本</span><span class="sxs-lookup"><span data-stu-id="c4028-412">**IIS** as the version</span></span>
    
  - <span data-ttu-id="c4028-413">使用類型的 **網頁伺服器**</span><span class="sxs-lookup"><span data-stu-id="c4028-413">**Web Server** as the usage type</span></span>
    
  - <span data-ttu-id="c4028-414">以回應格式 **PKCS7**</span><span class="sxs-lookup"><span data-stu-id="c4028-414">**PKCS7** as the response format</span></span>
    
 
### <a name="2-import-the-certificate"></a><span data-ttu-id="c4028-415">2. 匯入憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-415">2. Import the certificate</span></span>

<span data-ttu-id="c4028-416">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-416">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-417">以本機 Administrators 群組成員的身分登入至 Edge Server，而您在上一個程式中提出憑證要求。</span><span class="sxs-lookup"><span data-stu-id="c4028-417">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="c4028-418">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-418">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-419">在 [部署嚮導] 中的 [ **步驟 3] 旁邊。要求、安裝或指派憑證**，請按一下 [ **再執行一次**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-419">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="c4028-420">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-420">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-421">在 [ **可用憑證** 工作] 頁面上，按一下 [匯 **入憑證自 a]。P7b、.pfx 或 .cer** 檔案。</span><span class="sxs-lookup"><span data-stu-id="c4028-421">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="c4028-422">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-422">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-423">在 [匯 **入憑證** ] 頁面上，輸入您在前一節中取得之憑證的完整路徑及檔案名 (，也可以按一下 **[流覽]** ，尋找並選擇) 的檔案。</span><span class="sxs-lookup"><span data-stu-id="c4028-423">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span> <span data-ttu-id="c4028-424">如果您的憑證包含私密金鑰，請務必選取 [ **憑證檔案包含憑證的私密金鑰**]，然後輸入私密金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="c4028-424">If your certificate contains a private key, make sure to select **Certificate file contains certificate's private key**, and enter the password for the private key.</span></span> <span data-ttu-id="c4028-425">準備好時，按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="c4028-425">Click **Next** when ready.</span></span>
    
<span data-ttu-id="c4028-426">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-426">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-427">在 [匯 **入憑證摘要** ] 頁面上，複查摘要資訊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-427">On the **Import Certificate Summary** page, review the summary information, and click **Next**.</span></span>
    
<span data-ttu-id="c4028-428">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-428">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-429">在 [ **執行命令** ] 頁面上，您可以按一下 [ **查看記錄** 檔]，以複查完成時的匯入結果。</span><span class="sxs-lookup"><span data-stu-id="c4028-429">On the **Executing Commands** page, you can review the result of the import when it's complete by clicking **View Log**.</span></span> <span data-ttu-id="c4028-430">按一下 **[完成]** 以完成憑證匯入。</span><span class="sxs-lookup"><span data-stu-id="c4028-430">Click **Finish** to complete the certificate import.</span></span>
    
<span data-ttu-id="c4028-431">&nbsp;&nbsp;&nbsp;G。</span><span class="sxs-lookup"><span data-stu-id="c4028-431">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="c4028-432">如果您的集區中有其他 Edge Server，您也必須遵循下兩個程式。</span><span class="sxs-lookup"><span data-stu-id="c4028-432">If you have other Edge Servers in a pool, you'll need to follow the next two procedures as well.</span></span> <span data-ttu-id="c4028-433">如果這是獨立的 Edge Server，就會使用外部憑證完成。</span><span class="sxs-lookup"><span data-stu-id="c4028-433">If this is a standalone Edge Server, you're done with external certificates.</span></span>
    
 
### <a name="3-export-the-certificate"></a><span data-ttu-id="c4028-434">3. 匯出憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-434">3. Export the certificate</span></span>

<span data-ttu-id="c4028-435">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-435">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-436">請確認您已登入以本機系統管理員身分匯入憑證的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="c4028-436">Make sure you've logged onto the Edge Server you imported the certificate to as a local Administrator.</span></span>
    
<span data-ttu-id="c4028-437">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-437">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-438">按一下 [ **開始**]、[ **執行** (] 或 [開啟 **搜尋** ) ]，然後輸入 **MMC**。</span><span class="sxs-lookup"><span data-stu-id="c4028-438">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="c4028-439">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-439">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-440">在 MMC 主控台中，按一下 [檔案]，**然後按一下 [\*\*\*\*新增/移除嵌入式管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-440">From the MMC console, click **File**, and then click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="c4028-441">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-441">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-442">在 [ **新增或移除嵌入式管理單元** ] 方塊中，按一下 [ **憑證**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-442">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="c4028-443">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-443">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-444">在 [ **憑證** 嵌入式管理單元] 對話方塊中，選擇 [ **電腦帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-444">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="c4028-445">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-445">Click **Next**.</span></span>
    
<span data-ttu-id="c4028-446">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-446">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-447">在 [ **選取電腦** ] 對話方塊中，選取 [ **本機電腦： (此主控台執行的電腦])**。</span><span class="sxs-lookup"><span data-stu-id="c4028-447">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="c4028-448">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-448">Click **Finish**.</span></span> <span data-ttu-id="c4028-449">按一下 **[確定]**，然後完成 MMC 主控台的設定。</span><span class="sxs-lookup"><span data-stu-id="c4028-449">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="c4028-450">&nbsp;&nbsp;&nbsp;G。</span><span class="sxs-lookup"><span data-stu-id="c4028-450">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="c4028-451">按兩下 [ **憑證 (本機電腦])** 以展開憑證儲存區。</span><span class="sxs-lookup"><span data-stu-id="c4028-451">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="c4028-452">連 **按兩下 [個人**]，然後按一下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-452">**Double-click Personal**, and then click **Certificates**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="c4028-453">您可能在這裡，而且在本機電腦的憑證個人存放區中看不到任何憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-453">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="c4028-454">您不需要進行搜尋，如果該機碼不存在，則匯入的憑證沒有相關聯的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="c4028-454">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="c4028-455">請嘗試一次以上的要求和匯入步驟，如果您確定完全正確，請諮詢 CA 管理員或提供者。</span><span class="sxs-lookup"><span data-stu-id="c4028-455">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="c4028-456">&nbsp;&nbsp;&nbsp;H。</span><span class="sxs-lookup"><span data-stu-id="c4028-456">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="c4028-457">在本機電腦的 [ **憑證個人] 存放區** 中，以滑鼠右鍵按一下您要匯出的憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-457">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="c4028-458">從產生的功能表中 **選取 [所有** 工作]，然後按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-458">**Select All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="c4028-459">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-459">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="c4028-460">在 [憑證匯出精靈] 中，按 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="c4028-460">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="c4028-461">選取 **[是，匯出私密金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-461">Select **Yes, export the private key**.</span></span> <span data-ttu-id="c4028-462">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-462">Click **Next**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="c4028-463">如果 **是，請匯出私密金鑰** 不可用，則此憑證的私密金鑰在您取得之前並未標示為匯出。</span><span class="sxs-lookup"><span data-stu-id="c4028-463">If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it.</span></span> <span data-ttu-id="c4028-464">您必須再次向提供者要求憑證，並在私密金鑰設定為匯出後，才可成功執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="c4028-464">You need to request the certificate from the provider again, with the private key set to export, before doing this successfully.</span></span>
  
<span data-ttu-id="c4028-465">&nbsp;&nbsp;&nbsp;J。</span><span class="sxs-lookup"><span data-stu-id="c4028-465">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="c4028-466">在 [匯出檔案格式] 對話方塊中，選取 [個人資訊交換-PKCS#12 (]。PFX) 然後選取下列各項：</span><span class="sxs-lookup"><span data-stu-id="c4028-466">On the Export File Formats dialog, select Personal Information Exchange - PKCS#12 (.PFX) and then select the following:</span></span>
    
 <span data-ttu-id="c4028-467">&nbsp;&nbsp;&nbsp;  我。</span><span class="sxs-lookup"><span data-stu-id="c4028-467">&nbsp;&nbsp;&nbsp;  i.</span></span> <span data-ttu-id="c4028-468">如有可能，請將所有憑證包含在憑證路徑中。</span><span class="sxs-lookup"><span data-stu-id="c4028-468">Include all certificates in the certification path, if possible.</span></span>
    
 <span data-ttu-id="c4028-469">&nbsp;&nbsp;&nbsp;  第二。</span><span class="sxs-lookup"><span data-stu-id="c4028-469">&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="c4028-470">匯出所有延伸屬性。</span><span class="sxs-lookup"><span data-stu-id="c4028-470">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="c4028-471">如果匯出成功，**切勿** 選取 **[刪除私密金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-471">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="c4028-472">這表示您必須將憑證和私密金鑰重新導入至此 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="c4028-472">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="c4028-473">&nbsp;&nbsp;&nbsp;K。</span><span class="sxs-lookup"><span data-stu-id="c4028-473">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="c4028-474">如果您想要指派密碼來保護私密金鑰，您可以輸入私密金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="c4028-474">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="c4028-475">重新輸入密碼以加以確認，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-475">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="c4028-476">&nbsp;&nbsp;&nbsp;我。</span><span class="sxs-lookup"><span data-stu-id="c4028-476">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="c4028-477">輸入匯出憑證的路徑和檔案名，並使用 **.pfx** 的副檔名。</span><span class="sxs-lookup"><span data-stu-id="c4028-477">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="c4028-478">您必須可以透過集區中的其他 Edge Server 存取該路徑，否則您必須使用外部媒體 (例如 u 盤) ）移動檔案。</span><span class="sxs-lookup"><span data-stu-id="c4028-478">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="c4028-479">作出選擇後，請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="c4028-479">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="c4028-480">&nbsp;&nbsp;&nbsp;平方米.</span><span class="sxs-lookup"><span data-stu-id="c4028-480">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="c4028-481">在 [ **完成憑證匯出嚮導** ] 對話方塊中查看摘要，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-481">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="c4028-482">&nbsp;&nbsp;&nbsp;\r\n.</span><span class="sxs-lookup"><span data-stu-id="c4028-482">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="c4028-483">在 [成功匯出] 對話方塊中，按一下 **[確定** ]。</span><span class="sxs-lookup"><span data-stu-id="c4028-483">Click **OK** in the successful export dialog.</span></span>
    
<span data-ttu-id="c4028-484">&nbsp;&nbsp;&nbsp;複雜度.</span><span class="sxs-lookup"><span data-stu-id="c4028-484">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="c4028-485">您現在必須回到此位置之前的 [匯入憑證] 區段，並將憑證匯入至其餘所有 Edge Server，然後繼續進行指派。</span><span class="sxs-lookup"><span data-stu-id="c4028-485">You'll now need to go back to the Import the certificate section prior to this and import the certificate to all your remaining Edge Servers, then proceed with assigning, below.</span></span>
    
 
### <a name="4-assign-the-certificate"></a><span data-ttu-id="c4028-486">4. 指派憑證</span><span class="sxs-lookup"><span data-stu-id="c4028-486">4. Assign the certificate</span></span>

<span data-ttu-id="c4028-487">&nbsp;&nbsp;&nbsp;單個.</span><span class="sxs-lookup"><span data-stu-id="c4028-487">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="c4028-488">在 **每一** 部 Edge Server 上，于 [部署嚮導] 中的 [ **步驟 3] 旁邊。要求、安裝或指派憑證**，請按一下 [ **再執行一次**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-488">On **EACH** Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="c4028-489">&nbsp;&nbsp;&nbsp;B。</span><span class="sxs-lookup"><span data-stu-id="c4028-489">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="c4028-490">在 [ **可用憑證** 工作] 頁面上，按一下 [ **指派現有的憑證**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-490">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="c4028-491">&nbsp;&nbsp;&nbsp;C。</span><span class="sxs-lookup"><span data-stu-id="c4028-491">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="c4028-492">在 [ **憑證指派** ] 頁面上，選取清單中的 [ **Edge External** ]。</span><span class="sxs-lookup"><span data-stu-id="c4028-492">On the **Certificate Assignment** page, select **Edge External** in the list.</span></span>
    
<span data-ttu-id="c4028-493">&nbsp;&nbsp;&nbsp;D。</span><span class="sxs-lookup"><span data-stu-id="c4028-493">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="c4028-494">在 [ **憑證存放區** ] 頁面上，選取您為外部 Edge 匯入的憑證) 上一節所 (。</span><span class="sxs-lookup"><span data-stu-id="c4028-494">On the **Certificate Store** page, select the certificate you've imported for the external Edge (from the previous section).</span></span>
    
<span data-ttu-id="c4028-495">&nbsp;&nbsp;&nbsp;發送.</span><span class="sxs-lookup"><span data-stu-id="c4028-495">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="c4028-496">在 [ **憑證指派摘要** ] 頁面上，查看設定，然後按一下 **[下一步]** 指派憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-496">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="c4028-497">&nbsp;&nbsp;&nbsp;F。</span><span class="sxs-lookup"><span data-stu-id="c4028-497">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="c4028-498">在精靈完成頁面中，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c4028-498">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="c4028-499">&nbsp;&nbsp;&nbsp;G。</span><span class="sxs-lookup"><span data-stu-id="c4028-499">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="c4028-500">當您完成此程式後，就可以在每個伺服器上開啟憑證 MMC 嵌入式管理單元，展開 [ **憑證 (本機電腦])**，展開 [ **個人**]，按一下 [ **憑證**]，然後確認 [詳細資料] 窗格中列出的是內部 Edge 憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-500">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="c4028-501">您也會需要設定反向 proxy 伺服器的憑證。</span><span class="sxs-lookup"><span data-stu-id="c4028-501">You will also have needed to set up the certificates for your reverse proxy server.</span></span> 
  
## <a name="starting-the-edge-servers"></a><span data-ttu-id="c4028-502">啟動 Edge Server</span><span class="sxs-lookup"><span data-stu-id="c4028-502">Starting the Edge Servers</span></span>

<span data-ttu-id="c4028-503">完成安裝後，您需要在部署中的每一部 Edge server 上啟動服務：</span><span class="sxs-lookup"><span data-stu-id="c4028-503">Once the setup is complete, you'll need to start the services on each Edge server in your deployment:</span></span>
  
1. <span data-ttu-id="c4028-504">在每一部 Edge Server 上，于 [ **部署嚮導**] 中的 [ **步驟4：啟動服務**] 旁邊，按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-504">On each Edge Server, in the **Deployment Wizard**, next to **Step 4: Start Services**, click **Run**.</span></span>
    
2. <span data-ttu-id="c4028-505">在 [ **開始商務用 Skype 伺服器服務** ] 頁面上，複查服務清單，然後按 **[下一步]** 以啟動服務。</span><span class="sxs-lookup"><span data-stu-id="c4028-505">On the **Start Skype for Business Server Services** page, review the list of services, and then click **Next** to start the services.</span></span>
    
3. <span data-ttu-id="c4028-506">啟動服務後，您可以按一下 **[完成** ] 來關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="c4028-506">After the services are started, you can click **Finish** to close the wizard.</span></span>
    
4. <span data-ttu-id="c4028-507"> (選用) 仍在 [ **步驟4：啟動服務**] 下，按一下 [ **服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="c4028-507">(Optional) Still under **Step 4: Start Services**, click **Services Status**.</span></span>
    
5.  <span data-ttu-id="c4028-508">在每一部伺服器上的 [ **服務 MMC** ] 中，確認所有商務用 Skype server 服務都在執行中。</span><span class="sxs-lookup"><span data-stu-id="c4028-508">In the **Services MMC** on each server, verify that all the Skype for Business Server services are running.</span></span>
    

