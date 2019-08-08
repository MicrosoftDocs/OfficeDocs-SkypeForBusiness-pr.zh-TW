---
title: 在商務用 Skype Server 中部署邊緣伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: '摘要: 瞭解如何將 Edge 伺服器部署到商務用 Skype Server 環境。'
ms.openlocfilehash: 70355f6f00e8f38a13d74afd2d13c62a345fa063
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234103"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a><span data-ttu-id="3df93-103">在商務用 Skype Server 中部署邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="3df93-103">Deploy Edge Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="3df93-104">**摘要:** 瞭解如何將 Edge 伺服器部署到商務用 Skype Server 環境。</span><span class="sxs-lookup"><span data-stu-id="3df93-104">**Summary:** Learn how to deploy Edge Servers into your Skype for Business Server environment.</span></span>
  
<span data-ttu-id="3df93-105">下列各節包含[在商務用 Skype server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md)檔的商務用 Skype server 方案已經過審查之後, 應遵循的步驟。</span><span class="sxs-lookup"><span data-stu-id="3df93-105">The following sections contain steps that are meant to be followed after the Skype for Business Server [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) documentation has been reviewed.</span></span> <span data-ttu-id="3df93-106">部署步驟如下所示:</span><span class="sxs-lookup"><span data-stu-id="3df93-106">The deployment steps are as follows:</span></span>
  
- <span data-ttu-id="3df93-107">網路介面</span><span class="sxs-lookup"><span data-stu-id="3df93-107">Network interfaces</span></span>
    
- <span data-ttu-id="3df93-108">安裝</span><span class="sxs-lookup"><span data-stu-id="3df93-108">Installation</span></span>
    
- <span data-ttu-id="3df93-109">證書</span><span class="sxs-lookup"><span data-stu-id="3df93-109">Certificates</span></span>
    
- <span data-ttu-id="3df93-110">啟動邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="3df93-110">Starting the Edge Servers</span></span>
    
## <a name="network-interfaces"></a><span data-ttu-id="3df93-111">網路介面</span><span class="sxs-lookup"><span data-stu-id="3df93-111">Network interfaces</span></span>

<span data-ttu-id="3df93-112">就像在規劃中所述, 您可以在託管您邊緣伺服器的周邊網路中, 或在周邊網路中不使用 DNS, 來設定您的網路介面。</span><span class="sxs-lookup"><span data-stu-id="3df93-112">As noted in Planning, you will either be configuring your network interface with DNS in the perimeter network hosting your Edge Servers, or without DNS in the perimeter network.</span></span>
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="3df93-113">在周邊網路中使用 DNS 伺服器的介面設定</span><span class="sxs-lookup"><span data-stu-id="3df93-113">Interface configuration with DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="3df93-114">針對每個邊緣伺服器安裝兩個網路介面卡, 一個用於內部介面, 另一個用於面向外部介面。</span><span class="sxs-lookup"><span data-stu-id="3df93-114">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3df93-115">內部和外部子網必須彼此無法路由。</span><span class="sxs-lookup"><span data-stu-id="3df93-115">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="3df93-116">您可以在外部介面上設定下列**其中一項**:</span><span class="sxs-lookup"><span data-stu-id="3df93-116">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="3df93-117">是.</span><span class="sxs-lookup"><span data-stu-id="3df93-117">a.</span></span> <span data-ttu-id="3df93-118">外部周邊網路子網上的三個靜態 IP 位址, 並將預設閘道指向外部防火牆的內部介面。</span><span class="sxs-lookup"><span data-stu-id="3df93-118">Three static IP addresses on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="3df93-119">將 [配接器 DNS 設定] 設定為指向一對週邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-119">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
   <span data-ttu-id="3df93-120">乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-120">b.</span></span> <span data-ttu-id="3df93-121">外部周邊網路子網上的一個靜態 IP 位址, 並將預設閘道指向外部防火牆的內部介面。</span><span class="sxs-lookup"><span data-stu-id="3df93-121">One static IP address on the external perimeter network subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="3df93-122">將 [配接器 DNS 設定] 設定為指向一對週邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-122">Configure the adapter DNS settings to point to a pair of perimeter DNS servers.</span></span> <span data-ttu-id="3df93-123">只有在您先前已將您的拓撲設定為在埠指派中有非標準值, 這項設定才是可接受的, 這會在為[商務用 Skype Server 文章建立您的邊緣拓撲](create-your-edge-topology.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="3df93-123">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="3df93-124">在您的內部介面上, 在內部周邊網路子網上設定一個靜態 IP, 然後不要設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="3df93-124">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="3df93-125">將 [配接器 DNS 設定] 設定為指向至少一個 DNS 伺服器, 但最好是一對週邊 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-125">Configure the adaptor DNS settings to point to at least one DNS server, but preferably a pair of perimeter DNS servers.</span></span>
    
4. <span data-ttu-id="3df93-126">在內部介面上建立永久靜態路由至用戶端、商務用 Skype 伺服器以及 Exchange 整合通訊 (UM) 伺服器所駐留的所有內部網路。</span><span class="sxs-lookup"><span data-stu-id="3df93-126">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="3df93-127">周邊網路中不含 DNS 伺服器的介面配置</span><span class="sxs-lookup"><span data-stu-id="3df93-127">Interface configuration without DNS servers in the perimeter network</span></span>

1. <span data-ttu-id="3df93-128">針對每個邊緣伺服器安裝兩個網路介面卡, 一個用於內部介面, 另一個用於面向外部介面。</span><span class="sxs-lookup"><span data-stu-id="3df93-128">Install two network adapters for each Edge Server, one for the internal-facing interface, and one for the external-facing interface.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3df93-129">內部和外部子網必須彼此無法路由。</span><span class="sxs-lookup"><span data-stu-id="3df93-129">The internal and external subnets must not be routable to each other.</span></span> 
  
2. <span data-ttu-id="3df93-130">您可以在外部介面上設定下列**其中一項**:</span><span class="sxs-lookup"><span data-stu-id="3df93-130">On your external interface, you'll configure **one** of the following:</span></span>
    
   <span data-ttu-id="3df93-131">是.</span><span class="sxs-lookup"><span data-stu-id="3df93-131">a.</span></span> <span data-ttu-id="3df93-132">外部周邊網路子網上的三個靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3df93-132">Three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="3df93-133">您也需要在外部介面上設定預設閘道, 例如, 將網際網路式路由器或外部防火牆定義為預設閘道。</span><span class="sxs-lookup"><span data-stu-id="3df93-133">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="3df93-134">將 [配接器 DNS 設定] 設定為指向外部 DNS 伺服器, 最好是一對外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-134">Configure the adapter DNS settings to point to an external DNS server, ideally a pair of external DNS servers.</span></span>
    
   <span data-ttu-id="3df93-135">乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-135">b.</span></span> <span data-ttu-id="3df93-136">外部周邊網路子網上的一個靜態 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3df93-136">One static IP address on the external perimeter network subnet.</span></span> <span data-ttu-id="3df93-137">您也需要在外部介面上設定預設閘道, 例如, 將網際網路式路由器或外部防火牆定義為預設閘道。</span><span class="sxs-lookup"><span data-stu-id="3df93-137">You'll also need to configure the default gateway on the external interface, for example, defining the internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="3df93-138">將 [配接器 DNS 設定] 設定為指向外部 DNS 伺服器, 或 [理想] 是一對外部 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-138">Configure the adapter DNS settings to point to an external DNS server, or ideally a pair of external DNS servers.</span></span> <span data-ttu-id="3df93-139">只有在您先前已將您的拓撲設定為在埠指派中有非標準值, 這項設定才是可接受的, 這會在為[商務用 Skype Server 文章建立您的邊緣拓撲](create-your-edge-topology.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="3df93-139">This configuration is ONLY acceptable if you have previously configured your topology to have non-standard values in the port assignments, which is covered in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
    
3. <span data-ttu-id="3df93-140">在您的內部介面上, 在內部周邊網路子網上設定一個靜態 IP, 然後不要設定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="3df93-140">On your internal interface, configure one static IP on the internal perimeter network subnet, and don't set a default gateway.</span></span> <span data-ttu-id="3df93-141">同時將配接器 DNS 設定保留為空白。</span><span class="sxs-lookup"><span data-stu-id="3df93-141">Also leave the adapter DNS settings empty.</span></span>
    
4. <span data-ttu-id="3df93-142">在內部介面上建立永久靜態路由至用戶端、商務用 Skype 伺服器以及 Exchange 整合通訊 (UM) 伺服器所駐留的所有內部網路。</span><span class="sxs-lookup"><span data-stu-id="3df93-142">Create persistent static routes on the internal interface to all internal networks where clients, Skype for Business Server, and Exchange Unified Messaging (UM) servers reside.</span></span>
    
5. <span data-ttu-id="3df93-143">在每個邊緣伺服器上編輯主機檔案, 以包含下一個躍點伺服器或虛擬 IP (VIP) 的記錄。</span><span class="sxs-lookup"><span data-stu-id="3df93-143">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP).</span></span> <span data-ttu-id="3df93-144">此記錄將是您在拓撲建立器中設定為 Edge 伺服器下一個躍點位址的 Director、Standard Edition 伺服器或前端池。</span><span class="sxs-lookup"><span data-stu-id="3df93-144">This record will be the Director, Standard Edition server or Front End pool you configured as the Edge Server next hop address in Topology Builder.</span></span> <span data-ttu-id="3df93-145">如果您使用的是 DNS 負載平衡, 請為下一個躍點池的每個成員包含一條線。</span><span class="sxs-lookup"><span data-stu-id="3df93-145">If you're using DNS load balancing, include a line for each member of the next hop pool.</span></span>
    
## <a name="installation"></a><span data-ttu-id="3df93-146">安裝</span><span class="sxs-lookup"><span data-stu-id="3df93-146">Installation</span></span>

<span data-ttu-id="3df93-147">若要成功完成這些步驟, 您必須遵循在[商務用 Skype Server 文章中建立邊緣拓撲](create-your-edge-topology.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="3df93-147">To complete these steps successfully, you will need to have followed the steps in the [Create your Edge topology for Skype for Business Server](create-your-edge-topology.md) article.</span></span>
  
1. <span data-ttu-id="3df93-148">使用本機管理員群組中的帳戶登入您針對 Edge 伺服器角色配置的伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-148">Log onto the server you've been configuring for the Edge Server role with an account that's in the local Administrator's group.</span></span>
    
2. <span data-ttu-id="3df93-149">您需要在此電腦上的 Edge 伺服器拓撲檔結尾複製您複製的拓撲設定檔案。</span><span class="sxs-lookup"><span data-stu-id="3df93-149">You'll need the topology configuration file you copied out at the end of the Edge Server Topology documentation on this machine.</span></span> <span data-ttu-id="3df93-150">存取您放入該設定檔案的外部媒體 (例如 USB 磁片磁碟機或共用)。</span><span class="sxs-lookup"><span data-stu-id="3df93-150">Access the external media you placed that configuration file on (like a USB drive or share).</span></span>
    
3. <span data-ttu-id="3df93-151">啟動 [**部署] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="3df93-151">Start the **Deployment Wizard**.</span></span>
    
4. <span data-ttu-id="3df93-152">嚮導開啟後, 按一下 [**安裝或更新商務用 Skype Server 系統**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-152">Once the wizard opens, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="3df93-153">嚮導會執行檢查, 以查看是否有任何已安裝的專案。</span><span class="sxs-lookup"><span data-stu-id="3df93-153">The wizard will run checks to see if anything's already installed.</span></span> <span data-ttu-id="3df93-154">如第一次執行此嚮導, 您會想從**步驟1開始。安裝本機配置存放區。**</span><span class="sxs-lookup"><span data-stu-id="3df93-154">As this is the first time running the wizard, you'll want to start at **Step 1. Install Local Configuration Store.**</span></span>
    
6. <span data-ttu-id="3df93-155">隨即會出現 [**設定中央管理儲存的本機複本**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="3df93-155">The **Configure Local Replica of Central Management store** dialog will appear.</span></span> <span data-ttu-id="3df93-156">您需要按一下 **[從檔案匯入] (適用于 Edge 伺服器的建議)**。</span><span class="sxs-lookup"><span data-stu-id="3df93-156">You need to click **Import from a file (Recommended for Edge Servers)**.</span></span>
    
7. <span data-ttu-id="3df93-157">在這裡, 流覽至您先前匯出的拓撲位置, 選取該 .zip 檔案, 按一下 [**開啟**], 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-157">From here, browse to the location of the topology you exported previously, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="3df93-158">[部署嚮導] 會讀取設定檔案, 並將 XML 設定檔寫入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="3df93-158">The Deployment Wizard will read the configuration file and write the XML configuration file to the local computer.</span></span>
    
9. <span data-ttu-id="3df93-159">完成**執行命令**程式後, 請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-159">After the **Executing Commands** process is finished, click **Finish**.</span></span>
    
10. <span data-ttu-id="3df93-160">在 [部署嚮導] 中, 按一下 [**步驟 2]。設定或移除商務用 Skype Server 元件**。</span><span class="sxs-lookup"><span data-stu-id="3df93-160">In the Deployment Wizard, click **Step 2. Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="3df93-161">然後, 此嚮導會安裝在儲存在本機電腦上的 XML 設定檔中指定的商務用 Skype Server Edge 元件。</span><span class="sxs-lookup"><span data-stu-id="3df93-161">The wizard will then install the Skype for Business Server Edge components specified in the XML configuration file that's been stored on the local computer.</span></span>
    
11. <span data-ttu-id="3df93-162">安裝完成後, 您可以移至下方 [**憑證**] 區段中的步驟。</span><span class="sxs-lookup"><span data-stu-id="3df93-162">Once the installation's complete, you can move onto the steps in the **Certificates** section below.</span></span>
    
## <a name="certificates"></a><span data-ttu-id="3df93-163">證書</span><span class="sxs-lookup"><span data-stu-id="3df93-163">Certificates</span></span>

<span data-ttu-id="3df93-164">Edge 伺服器的憑證需求可以在邊緣認證規劃檔中找到。</span><span class="sxs-lookup"><span data-stu-id="3df93-164">The certificate requirements for the Edge Server can be found in the Edge Certificate Planning documentation.</span></span> <span data-ttu-id="3df93-165">設定憑證的步驟如下。</span><span class="sxs-lookup"><span data-stu-id="3df93-165">The steps for setting up certificates are below.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3df93-166">在執行 [憑證] 嚮導時, 您必須以具有您要使用之憑證範本類型之正確許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="3df93-166">When running the Certificate Wizard, you need to be logged in as an account with the correct permissions for the type of certificate template you're going to use.</span></span> <span data-ttu-id="3df93-167">根據預設, 商務用 Skype 伺服器憑證要求將會使用 Web 服務器憑證範本。</span><span class="sxs-lookup"><span data-stu-id="3df93-167">By default, a Skype for Business Server certificate request is going to use the Web Server certificate template.</span></span> <span data-ttu-id="3df93-168">如果您是使用 RTCUniversalServerAdmins 群組成員的帳戶登入, 以透過這個範本申請憑證, 請重複檢查以確認群組已獲指派 [註冊] 許可權, 才能使用該範本。</span><span class="sxs-lookup"><span data-stu-id="3df93-168">If you're logged in with an account that's a member of the RTCUniversalServerAdmins group to request a certificate via this template, double-check to make sure the group's been assigned the Enroll permissions to use that template.</span></span> 
  
### <a name="internal-edge-interface-certificates"></a><span data-ttu-id="3df93-169">內部邊緣介面憑證</span><span class="sxs-lookup"><span data-stu-id="3df93-169">Internal Edge interface certificates</span></span>

 
### <a name="1-download-or-export-the-ca-certification-chain"></a><span data-ttu-id="3df93-170">1. 下載或匯出 CA 認證鏈</span><span class="sxs-lookup"><span data-stu-id="3df93-170">1. Download or export the CA certification chain</span></span>

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a><span data-ttu-id="3df93-171">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-171">&nbsp;&nbsp;&nbsp; a.</span></span> <span data-ttu-id="3df93-172">使用 certsrv 網站下載</span><span class="sxs-lookup"><span data-stu-id="3df93-172">Download using certsrv web site</span></span>

<span data-ttu-id="3df93-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-173">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="3df93-174">以本機管理員群組成員的身分登入內部網路中的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-174">Log into a Skype for Business Server in your internal network as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="3df93-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第.</span><span class="sxs-lookup"><span data-stu-id="3df93-175">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="3df93-176">開啟 [**開始**]、[**執行**] (或 [**搜尋**及**執行**]), 然後輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="3df93-176">Open up **Start**, and **Run** (or **Search** and **Run** ), and then type the following:</span></span>
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

<span data-ttu-id="3df93-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;例如:</span><span class="sxs-lookup"><span data-stu-id="3df93-177">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;For example:</span></span>
    
  ```
  https://ca01/contoso.com/certsrv
  ```

<span data-ttu-id="3df93-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;三.</span><span class="sxs-lookup"><span data-stu-id="3df93-178">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="3df93-179">在發證 CA 的 certsrv 網頁上的 [**選取工作**] 底下, 按一下 [**下載 CA 憑證、憑證連結或 CRL**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-179">On the issuing CA's certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>
    
<span data-ttu-id="3df93-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="3df93-180">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="3df93-181">在 [**下載 ca 憑證、憑證連結或 CRL**] 底下, 按一下 [**下載 ca 憑證連結**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-181">Under **Download a CA certificate, certificate chain, or CRL**, click **Download CA certificate chain**.</span></span>
    
<span data-ttu-id="3df93-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;向量.</span><span class="sxs-lookup"><span data-stu-id="3df93-182">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="3df93-183">在 [檔案**下載**] 方塊中, 按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-183">In the **File Download** box, click **Save**.</span></span>
    
<span data-ttu-id="3df93-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;六.</span><span class="sxs-lookup"><span data-stu-id="3df93-184">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="3df93-185">將. p7b 檔案儲存到伺服器上的硬碟, 然後將它複製到每個邊緣伺服器上的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="3df93-185">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each of your Edge Servers.</span></span>
    
### <a name="nbspnbspnbspb-export-using-mmc"></a><span data-ttu-id="3df93-186">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-186">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-187">使用 MMC 匯出</span><span class="sxs-lookup"><span data-stu-id="3df93-187">Export using MMC</span></span>

<span data-ttu-id="3df93-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-188">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="3df93-189">您可以使用 MMC 從任何已加入網域的電腦匯出 CA 根憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-189">You can export the CA root certificate from any domain joined machine using the MMC.</span></span> <span data-ttu-id="3df93-190">移至 [**開始**] 和 [**執行**], 或開啟 [**搜尋**], 然後輸入 [ **MMC** ] 來開啟。</span><span class="sxs-lookup"><span data-stu-id="3df93-190">Either go to **Start** and **Run**, or open **Search**, and type **MMC** to open.</span></span>
    
<span data-ttu-id="3df93-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第.</span><span class="sxs-lookup"><span data-stu-id="3df93-191">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii.</span></span> <span data-ttu-id="3df93-192">在 MMC 主控台中, 按一下\*\*\*\*[檔案], 然後按一下 [**新增/移除管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-192">In the MMC console, click **File**, and then click **Add/Remove Snap-In**.</span></span>
    
<span data-ttu-id="3df93-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;三.</span><span class="sxs-lookup"><span data-stu-id="3df93-193">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii.</span></span> <span data-ttu-id="3df93-194">從 [**新增或移除管理單元**] 對話方塊清單中, 選擇 [**憑證**], 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-194">From the **Add or Remove Snap-ins** dialog list, choose **Certificates**, and then click **Add**.</span></span> <span data-ttu-id="3df93-195">出現提示時, 請選取 [**電腦帳戶**], 然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-195">When prompted, select **Computer Account**, and then **Next**.</span></span> <span data-ttu-id="3df93-196">在 [**選取電腦**] 對話方塊中, 選取 [**本機電腦**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-196">On the **Select Computer** dialog, select **Local Computer**.</span></span> <span data-ttu-id="3df93-197">按一下 **[完成]**, 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-197">Click **Finish**, and then **OK**.</span></span>
    
<span data-ttu-id="3df93-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="3df93-198">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span></span> <span data-ttu-id="3df93-199">展開 **[憑證 (本機電腦)**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-199">Expand **Certificates (Local computer)**.</span></span> <span data-ttu-id="3df93-200">展開**受信任的根憑證授權單位**。</span><span class="sxs-lookup"><span data-stu-id="3df93-200">Expand **Trusted Root Certification Authorities**.</span></span> <span data-ttu-id="3df93-201">選取 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-201">Select **Certificates**.</span></span>
    
<span data-ttu-id="3df93-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;向量.</span><span class="sxs-lookup"><span data-stu-id="3df93-202">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v.</span></span> <span data-ttu-id="3df93-203">按一下您的 CA 所頒發的根憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-203">Click the root certificate issued by your CA.</span></span> <span data-ttu-id="3df93-204">以滑鼠右鍵按一下憑證, 選擇功能表上的 [**所有任務**], 然後選取 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-204">Right-click the certificate, choose **All Tasks** on the menu, and then select **Export**.</span></span>
    
<span data-ttu-id="3df93-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;六.</span><span class="sxs-lookup"><span data-stu-id="3df93-205">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi.</span></span> <span data-ttu-id="3df93-206">[**證書匯出] 嚮導**隨即開啟。</span><span class="sxs-lookup"><span data-stu-id="3df93-206">The **Certificate Export Wizard** opens.</span></span> <span data-ttu-id="3df93-207">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-207">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii.</span><span class="sxs-lookup"><span data-stu-id="3df93-208">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii.</span></span> <span data-ttu-id="3df93-209">在 [**匯出檔案格式**] 對話方塊中, 選擇您要匯出的格式。</span><span class="sxs-lookup"><span data-stu-id="3df93-209">On the **Export File Format** dialog, choose the format you want to export to.</span></span> <span data-ttu-id="3df93-210">我們的建議是**加密訊息語法標準-PKCS #7 憑證 (P7b)**。</span><span class="sxs-lookup"><span data-stu-id="3df93-210">Our recommendation is **Cryptographic Message Syntax Standard - PKCS #7 Certificates (P7b)**.</span></span> <span data-ttu-id="3df93-211">如果這是您選擇的選項, 請記住同時選取 [**如果可能的話, 包括憑證路徑中的所有憑證**] 核取方塊, 因為這也會匯出憑證連結, 包括根 CA 憑證及任何中間憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-211">If that's your choice as well, remember to also select the **Include all certificates in the certification path if possible** checkbox, as this will also export the certificate chain, including the root CA certificate and any Intermediate certificates.</span></span> <span data-ttu-id="3df93-212">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-212">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii.</span><span class="sxs-lookup"><span data-stu-id="3df93-213">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii.</span></span> <span data-ttu-id="3df93-214">在 [**要匯出**的檔案] 對話方塊的 [檔案名] 專案中, 輸入匯出憑證的路徑和檔案名 (預設副檔名為. p7b)。</span><span class="sxs-lookup"><span data-stu-id="3df93-214">On the **File to Export** dialog, in the file name entry, type a path and file name (the default extension would be .p7b) for the exported certificate.</span></span> <span data-ttu-id="3df93-215">如果您更容易, 請選擇 [**流覽]** 按鈕, 移至您要儲存匯出的憑證的位置, 然後在此命名匯出的憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-215">If it's easier on you, choose the **Browse** button to go to the location you want to save the exported certificate to, and name the exported certificate here.</span></span> <span data-ttu-id="3df93-216">按一下 [**儲存**], 然後在您準備好時再選取 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="3df93-216">Click **Save**, and then **Next** when you're ready.</span></span>
    
<span data-ttu-id="3df93-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;期.</span><span class="sxs-lookup"><span data-stu-id="3df93-217">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix.</span></span> <span data-ttu-id="3df93-218">查看您動作的摘要, 然後按一下 **[完成]** 以完成憑證的匯出。</span><span class="sxs-lookup"><span data-stu-id="3df93-218">Review the summary of your actions, and click **Finish** to complete the export of the certificate.</span></span> <span data-ttu-id="3df93-219">按一下 **[確定]** 以確認匯出成功。</span><span class="sxs-lookup"><span data-stu-id="3df93-219">Click **OK** to confirm the successful export.</span></span>
    
<span data-ttu-id="3df93-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;pci-x.</span><span class="sxs-lookup"><span data-stu-id="3df93-220">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x.</span></span> <span data-ttu-id="3df93-221">將. p7b 檔案複製到您的每個邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-221">Copy the .p7b file to each of your Edge Servers.</span></span>
    
### <a name="2-import-the-ca-certification-chain"></a><span data-ttu-id="3df93-222">2. 匯入 CA 認證鏈</span><span class="sxs-lookup"><span data-stu-id="3df93-222">2. Import the CA certification chain</span></span>

<span data-ttu-id="3df93-223">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-223">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-224">在每個邊緣伺服器上, 開啟 MMC (選擇 [**開始**] 和 [**執行**], 或 [**搜尋**], 然後輸入**MMC**來開啟)。</span><span class="sxs-lookup"><span data-stu-id="3df93-224">On each Edge Server, open the MMC (choose **Start** and **Run**, or **Search**, and type **MMC** to open).</span></span>
    
<span data-ttu-id="3df93-225">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-225">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-226">在 [ \*\*\*\* 檔案] 功能表上, 按一下 [**新增/移除管理單元**], 然後選擇 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-226">On the **File** menu, click **Add/Remove Snap-in**, and then choose **Add**.</span></span>
    
<span data-ttu-id="3df93-227">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-227">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-228">在 [**新增或移除管理單元**] 方塊中, 按一下 [**憑證**], 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-228">In the **Add or Remove Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>
    
<span data-ttu-id="3df93-229">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-229">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-230">在 [**憑證管理單元**] 對話方塊中, 按一下 [**電腦帳戶**], 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-230">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>
    
<span data-ttu-id="3df93-231">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-231">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-232">在 [**選取電腦**] 對話方塊中, 確認已選取 [**本機電腦 (執行此主控台的電腦)** ] 核取方塊, 然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-232">In the **Select Computer** dialog box, ensure that the **Local Computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>
    
<span data-ttu-id="3df93-233">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-233">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-234">按一下 [**關閉**], 然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-234">Click **Close**, and then **OK**.</span></span>
    
<span data-ttu-id="3df93-235">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="3df93-235">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="3df93-236">在主控台樹中, 展開 [**憑證 (本機電腦)**], 以滑鼠右鍵按一下 [**信任的根憑證授權單位**], 移至 [**所有任務**], 然後按一下 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-236">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, go to **All Tasks**, and then click **Import**.</span></span>
    
<span data-ttu-id="3df93-237">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="3df93-237">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="3df93-238">在隨後出現的嚮導的 [**要匯入**的檔案] 文字方塊中, 指定憑證的檔案名 (在前一節中您賦予. p7b 檔案的名稱)。</span><span class="sxs-lookup"><span data-stu-id="3df93-238">In the wizard that appears, in the **File to Import** textbox, specify the file name of the certificate (the name you gave the .p7b file in the previous section).</span></span> <span data-ttu-id="3df93-239">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-239">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-240">&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-240">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="3df93-241">將 [選項按鈕]**放在 [將所有憑證放在下列書店中], 因為應該選取受信任的根憑證授權單位**。</span><span class="sxs-lookup"><span data-stu-id="3df93-241">Leave the radio button on **Place all certificates in the following store, as Trusted Root Certification Authorities** should be selected.</span></span> <span data-ttu-id="3df93-242">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-242">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-243">&nbsp;&nbsp;&nbsp;韓文.</span><span class="sxs-lookup"><span data-stu-id="3df93-243">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="3df93-244">查看摘要, 然後按一下 **[完成]** 以完成匯入。</span><span class="sxs-lookup"><span data-stu-id="3df93-244">Review the summary, and click **Finish** to complete the import.</span></span>
    
<span data-ttu-id="3df93-245">&nbsp;&nbsp;&nbsp;位元組.</span><span class="sxs-lookup"><span data-stu-id="3df93-245">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="3df93-246">這將需要針對您要部署的每個 Edge 伺服器進行。</span><span class="sxs-lookup"><span data-stu-id="3df93-246">This will need to be done for every Edge Server you're deploying.</span></span>
    
### <a name="3-create-the-certificate-request"></a><span data-ttu-id="3df93-247">3. 建立證書申請</span><span class="sxs-lookup"><span data-stu-id="3df93-247">3. Create the certificate request</span></span>

<span data-ttu-id="3df93-248">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-248">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-249">登入其中一個邊緣伺服器、啟動 [部署嚮導], 然後在**步驟 3: [要求**]、[安裝] 或 [指派憑證], 按一下 [**執行**] (如果您已執行此嚮導, 則會**再次執行**)。</span><span class="sxs-lookup"><span data-stu-id="3df93-249">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates**, click **Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="3df93-250">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-250">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-251">在 [**憑證要求**] 頁面上, 確認已選取 [**內部邊緣證書**], 然後按一下 [**要求**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-251">On the **Certificate Request** page, ensure **Internal Edge Certificate** is selected, and click **Request**.</span></span>
    
<span data-ttu-id="3df93-252">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-252">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-253">在 [**延遲] 或 [立即要求**] 頁面上, 如果您有權從 Edge 環境存取, 請選擇 [**立即將要求傳送給線上憑證授權單位**], 或按一下 [**立即傳送要求], 稍後再傳送**。</span><span class="sxs-lookup"><span data-stu-id="3df93-253">On the **Delayed or Immediate Requests** page, choose **Send the request immediately to an online certification authority** if you have access to one from your Edge environment, or **Prepare the request now, but send it later** otherwise.</span></span>
    
<span data-ttu-id="3df93-254">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-254">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-255">在 [**憑證要求**檔案] 頁面上, 輸入檔案儲存位置的完整元件及檔案名 (例如 c:\SkypeInternalEdgeCert.cer)。</span><span class="sxs-lookup"><span data-stu-id="3df93-255">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="3df93-256">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-256">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-257">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-257">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-258">若要使用預設 Web 文件範本以外的範本, 請在 [**指定備用憑證範本**] 頁面上, 核取 [**針對所選的憑證頒發機構使用替代憑證範本**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3df93-258">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span> <span data-ttu-id="3df93-259">否則, 請勿執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="3df93-259">Otherwise, do nothing.</span></span>
    
<span data-ttu-id="3df93-260">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-260">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-261">在 [名稱及安全性設定] 頁面上, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="3df93-261">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="3df93-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-262">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="3df93-263">在 [**易記名稱**] 中, 輸入憑證的顯示名稱 (例如內部邊緣)。</span><span class="sxs-lookup"><span data-stu-id="3df93-263">In **Friendly name**, enter a display name for the certificate (such as Internal Edge).</span></span>
    
 <span data-ttu-id="3df93-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第.</span><span class="sxs-lookup"><span data-stu-id="3df93-264">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="3df93-265">在 [**位長**] 中, 選擇您的位長 (預設值為 2048, 您可以提高安全性, 但會使效能變慢)。</span><span class="sxs-lookup"><span data-stu-id="3df93-265">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="3df93-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;三.</span><span class="sxs-lookup"><span data-stu-id="3df93-266">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="3df93-267">如果您需要可匯出的憑證, 您必須核取 [將**證書私密金鑰標示為可匯出**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3df93-267">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
 <span data-ttu-id="3df93-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="3df93-268">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv.</span></span> <span data-ttu-id="3df93-269">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-269">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-270">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="3df93-270">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="3df93-271">在 [**組織資訊**] 頁面上, 輸入貴組織和組織單位 (OU) 的名稱。</span><span class="sxs-lookup"><span data-stu-id="3df93-271">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="3df93-272">您可以輸入您的部門或部門 (例如)。</span><span class="sxs-lookup"><span data-stu-id="3df93-272">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="3df93-273">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="3df93-273">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="3df93-274">在 [**地理資訊**] 頁面上, 輸入您的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="3df93-274">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="3df93-275">&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-275">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="3df93-276">在 [**受領人名稱/主旨替換名稱**] 頁面上, 嚮導應該自動填入此頁面。</span><span class="sxs-lookup"><span data-stu-id="3df93-276">On the **Subject Name/Subject Alternate Names** page, this should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="3df93-277">&nbsp;&nbsp;&nbsp;韓文.</span><span class="sxs-lookup"><span data-stu-id="3df93-277">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="3df93-278">在 [**設定其他消費者替換名稱**] 頁面上, 您需要新增任何您需要的其他消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="3df93-278">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="3df93-279">&nbsp;&nbsp;&nbsp;位元組.</span><span class="sxs-lookup"><span data-stu-id="3df93-279">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="3df93-280">在 [**要求摘要**] 頁面上, 查看將要用來產生您要求之憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="3df93-280">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="3df93-281">如果您需要進行變更, 請返回並立即執行。</span><span class="sxs-lookup"><span data-stu-id="3df93-281">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="3df93-282">&nbsp;&nbsp;&nbsp;左.</span><span class="sxs-lookup"><span data-stu-id="3df93-282">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="3df93-283">然後按一下 **[下一步]** , 以產生您需要提供給 CA 的 CSR 檔案 (您也可以按一下 [**查看記錄**] 來查看憑證要求的記錄)。</span><span class="sxs-lookup"><span data-stu-id="3df93-283">Then click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="3df93-284">&nbsp;&nbsp;&nbsp;m.</span><span class="sxs-lookup"><span data-stu-id="3df93-284">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="3df93-285">在要求產生之後, 您可以按一下 [**查看**] 來查看憑證, 然後按一下 **[完成**] 來關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="3df93-285">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="3df93-286">CSR 檔案的內容需要提供給您的 CA, 因此他們可以在下一節中產生您要匯入到此電腦的憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-286">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    

### <a name="4-import-the-certificate"></a><span data-ttu-id="3df93-287">4. 匯入憑證</span><span class="sxs-lookup"><span data-stu-id="3df93-287">4. Import the certificate</span></span>

<span data-ttu-id="3df93-288">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-288">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-289">以本機管理員群組成員的身分登入, 移至最後一個程式中您提出證書要求的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-289">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="3df93-290">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-290">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-291">在 [部署嚮導] 的 [**步驟 3] 旁。要求、安裝或指派憑證**, 請**再次**按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="3df93-291">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="3df93-292">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-292">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-293">在 [**可用的憑證**工作] 頁面上, 按一下 [**從 a 匯入憑證]。P7b、.pfx 或 .cer**檔案。</span><span class="sxs-lookup"><span data-stu-id="3df93-293">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="3df93-294">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-294">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-295">在 [匯**入憑證**] 頁面上, 輸入您在前一節中取得之憑證的完整路徑和檔案名 (您也可以按一下 **[流覽]** 以尋找並選擇該檔案的方式)。</span><span class="sxs-lookup"><span data-stu-id="3df93-295">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span>
    
<span data-ttu-id="3df93-296">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-296">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-297">如果您要匯入其他邊緣池成員的憑證, 且您的憑證包含私密金鑰, 請務必選取 [**包含證書私人金鑰的憑證**檔案] 核取方塊, 並指定密碼。</span><span class="sxs-lookup"><span data-stu-id="3df93-297">If you're importing certificates for other members of your Edge pool, and your certificate contains a private key, be sure to select the **Certificate file that contains certificate's private key** check box, and specify the password.</span></span> <span data-ttu-id="3df93-298">請按 [下一步]\*\*\*\* 繼續。</span><span class="sxs-lookup"><span data-stu-id="3df93-298">Click **Next** to continue.</span></span>
    
<span data-ttu-id="3df93-299">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-299">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-300">在 [**摘要**] 頁面上, 在您確認資訊之後, 按一下 **[下一步**], 然後在成功匯入憑證後**完成**。</span><span class="sxs-lookup"><span data-stu-id="3df93-300">On the**Summary** page, click **Next** once you've confirmed the information, and **Finish** once the certificate is successfully imported.</span></span>
    
 
### <a name="5-export-the-certificate"></a><span data-ttu-id="3df93-301">5. 匯出憑證</span><span class="sxs-lookup"><span data-stu-id="3df93-301">5. Export the certificate</span></span>

<span data-ttu-id="3df93-302">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-302">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-303">請確認您已登入您先前已匯入憑證的邊緣伺服器, 成為本機管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="3df93-303">Make sure you've logged onto the Edge Server you imported the certificate to previously, as a member of the local Administrators group.</span></span>
    
<span data-ttu-id="3df93-304">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-304">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-305">按一下 [**開始**]、[**執行**] (或 [開啟**搜尋**]), 然後輸入 [ **MMC**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-305">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="3df93-306">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-306">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-307">在 MMC 主控台中, 按一下\*\*\*\*[檔案], 然後按一下 [**新增/移除管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-307">From the MMC console, click **File**, and click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="3df93-308">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-308">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-309">從 [**新增或移除管理單元**] 方塊中, 按一下 [**憑證**], 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-309">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="3df93-310">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-310">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-311">在 [**憑證**管理單元] 對話方塊中, 選擇 [**電腦帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-311">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="3df93-312">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-312">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-313">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-313">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-314">在 [**選取電腦**] 對話方塊中, 選取 [**本機電腦: 執行此主控台的電腦**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-314">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="3df93-315">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-315">Click **Finish**.</span></span> <span data-ttu-id="3df93-316">按一下 **[確定]**, MMC 主控台的設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="3df93-316">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="3df93-317">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="3df93-317">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="3df93-318">按兩下 **[憑證 (本機電腦)** ], 展開證書存放區。</span><span class="sxs-lookup"><span data-stu-id="3df93-318">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="3df93-319">按兩下 [**個人**], 然後按一下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-319">Double-click **Personal**, and then click **Certificates**.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="3df93-320">您可能在這裡, 但在本機電腦的 [憑證個人] 商店中看不到任何憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-320">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="3df93-321">您不需要搜尋, 如果該索引鍵不在該處, 則匯入的憑證沒有與其相關聯的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="3df93-321">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="3df93-322">請稍後再試一次要求和匯入步驟, 如果您確定自己已取得正確的許可權, 請與您的 CA 管理員或提供者通話。</span><span class="sxs-lookup"><span data-stu-id="3df93-322">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="3df93-323">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="3df93-323">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="3df93-324">在本機電腦的 [**認證個人] 商店**中, 以滑鼠右鍵按一下您要匯出的憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-324">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="3df93-325">從產生的功能表中選取 [**所有任務**], 然後按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-325">Select **All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="3df93-326">&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-326">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="3df93-327">在 [**證書匯出嚮導]** 中, 按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-327">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="3df93-328">選取 **[是, 匯出私人金鑰]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-328">Select **Yes, export the private key**.</span></span> <span data-ttu-id="3df93-329">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-329">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-330">&nbsp;&nbsp;&nbsp;韓文.</span><span class="sxs-lookup"><span data-stu-id="3df93-330">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="3df93-331">在 [**匯出檔案格式**] 對話方塊中, 選取 [**個人資訊交換-PKCS # 12 (。PFX)**, 然後選取下列專案:</span><span class="sxs-lookup"><span data-stu-id="3df93-331">On the **Export File Formats** dialog, select **Personal Information Exchange - PKCS#12 (.PFX)**, and then select the following:</span></span>
    
<span data-ttu-id="3df93-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-332">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="3df93-333">如果可能的話, 請將所有憑證包含在憑證路徑中。</span><span class="sxs-lookup"><span data-stu-id="3df93-333">Include all certificates in the certification path, if possible.</span></span>
    
<span data-ttu-id="3df93-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第.</span><span class="sxs-lookup"><span data-stu-id="3df93-334">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii.</span></span> <span data-ttu-id="3df93-335">匯出所有延伸屬性。</span><span class="sxs-lookup"><span data-stu-id="3df93-335">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="3df93-336">**如果匯出成功**,**千萬不要**選取 [刪除金鑰]。</span><span class="sxs-lookup"><span data-stu-id="3df93-336">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="3df93-337">這表示您必須重新將憑證和私密金鑰重新導入到此 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-337">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="3df93-338">&nbsp;&nbsp;&nbsp;位元組.</span><span class="sxs-lookup"><span data-stu-id="3df93-338">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="3df93-339">如果您想要指派密碼來保護私密金鑰, 您可以輸入私人金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="3df93-339">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="3df93-340">重新輸入密碼以進行確認, 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-340">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="3df93-341">&nbsp;&nbsp;&nbsp;左.</span><span class="sxs-lookup"><span data-stu-id="3df93-341">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="3df93-342">針對匯出的憑證輸入路徑和檔案名, 並使用 **.pfx**副檔名。</span><span class="sxs-lookup"><span data-stu-id="3df93-342">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="3df93-343">路徑中的其他邊緣伺服器必須能夠存取路徑, 否則您需要使用外部媒體 (例如 USB 磁片磁碟機) 來移動檔案。</span><span class="sxs-lookup"><span data-stu-id="3df93-343">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="3df93-344">當您進行選擇時, 請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="3df93-344">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="3df93-345">&nbsp;&nbsp;&nbsp;m.</span><span class="sxs-lookup"><span data-stu-id="3df93-345">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="3df93-346">在 [**完成證書匯出嚮導**] 對話方塊中查看摘要, 然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-346">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="3df93-347">&nbsp;&nbsp;&nbsp;n.</span><span class="sxs-lookup"><span data-stu-id="3df93-347">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="3df93-348">按一下 [成功匯出] 對話方塊中的 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-348">Click **OK** in the successful export dialog.</span></span>
    
 
### <a name="6-assign-the-certificate"></a><span data-ttu-id="3df93-349">6. 指派憑證</span><span class="sxs-lookup"><span data-stu-id="3df93-349">6. Assign the certificate</span></span>

<span data-ttu-id="3df93-350">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-350">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-351">在每個 Edge 伺服器的 [部署嚮導] 中, 在**步驟3的旁邊。要求、安裝或指派憑證**, 請**再次**按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="3df93-351">On EACH Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="3df93-352">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-352">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-353">在 [**可用的憑證**工作] 頁面上, 按一下 [**指派現有的憑證**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-353">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="3df93-354">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-354">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-355">在 [**憑證指派**] 頁面上, 選取清單中的 [**邊緣內部**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-355">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>
    
<span data-ttu-id="3df93-356">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-356">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-357">在 [**憑證存放區**] 頁面上, 選取您針對內部邊緣所匯入的憑證 (從上一節)。</span><span class="sxs-lookup"><span data-stu-id="3df93-357">On the **Certificate Store** page, select the certificate you've imported for the internal Edge (from the previous section).</span></span>
    
<span data-ttu-id="3df93-358">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-358">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-359">在 [**憑證指派摘要**] 頁面上, 查看設定, 然後按一下 **[下一步]** 以指派憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-359">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="3df93-360">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-360">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-361">在 [嚮導完成] 頁面上, 按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-361">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="3df93-362">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="3df93-362">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="3df93-363">完成這個程式後, 建議您在每個 Edge 伺服器上開啟 [憑證] MMC 管理單元、展開 **[憑證 (本機電腦)**]、[展開**個人**]、[**憑證**], 然後確認內部邊緣[詳細資料] 窗格中列出了 [憑證]。</span><span class="sxs-lookup"><span data-stu-id="3df93-363">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each Edge Server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
### <a name="external-edge-interface-certificates"></a><span data-ttu-id="3df93-364">外部邊緣介面憑證</span><span class="sxs-lookup"><span data-stu-id="3df93-364">External Edge interface certificates</span></span>

 
### <a name="1-create-the-certificate-request"></a><span data-ttu-id="3df93-365">1. 建立證書申請</span><span class="sxs-lookup"><span data-stu-id="3df93-365">1. Create the certificate request</span></span>

<span data-ttu-id="3df93-366">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-366">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-367">登入其中一個邊緣伺服器、啟動 [部署嚮導], 然後在**步驟 3: [要求]、[安裝] 或 [指派憑證], 按一下 [執行**] (如果您已執行此嚮導, 則會**再次執行**)。</span><span class="sxs-lookup"><span data-stu-id="3df93-367">Log on to one of your Edge Servers, start the Deployment Wizard, and on **Step 3: Request, Install, or Assign Certificates, click Run** (or **Run Again**, if you've already run this wizard).</span></span>
    
<span data-ttu-id="3df93-368">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-368">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-369">在 [**可用的憑證**工作] 頁面上, 按一下 [**建立新的憑證要求**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-369">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>
    
<span data-ttu-id="3df93-370">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-370">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-371">在 [**憑證要求**] 頁面上, 確認已選取 [**外部邊緣憑證**], 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-371">On the **Certificate Request** page, ensure **External Edge Certificate** is selected, and click **Next**.</span></span>
    
<span data-ttu-id="3df93-372">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-372">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-373">在 [**延遲] 或 [立即要求**] 頁面上, 按一下 **[立即準備要求], 但稍後再傳送**。</span><span class="sxs-lookup"><span data-stu-id="3df93-373">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>
    
<span data-ttu-id="3df93-374">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-374">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-375">在 [**憑證要求**檔案] 頁面上, 輸入檔案儲存位置的完整元件及檔案名 (例如 c:\SkypeInternalEdgeCert.cer)。</span><span class="sxs-lookup"><span data-stu-id="3df93-375">On the **Certificate Request File** page, enter the full part and file name for where the file will be saved (such as c:\SkypeInternalEdgeCert.cer).</span></span> <span data-ttu-id="3df93-376">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-376">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-377">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-377">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-378">若要使用預設 Web 文件範本以外的範本, 請在 [**指定備用憑證範本**] 頁面上, 核取 [**針對所選的憑證頒發機構使用替代憑證範本**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3df93-378">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, check the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>
    
<span data-ttu-id="3df93-379">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="3df93-379">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="3df93-380">在 [名稱及安全性設定] 頁面上, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="3df93-380">On the Name and Security Settings page, do the following:</span></span>
    
<span data-ttu-id="3df93-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-381">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i.</span></span> <span data-ttu-id="3df93-382">在 [**易記名稱**] 中, 輸入憑證的顯示名稱 (例如外部邊緣)。</span><span class="sxs-lookup"><span data-stu-id="3df93-382">In **Friendly name**, enter a display name for the certificate (such as External Edge).</span></span>
    
 <span data-ttu-id="3df93-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;第.</span><span class="sxs-lookup"><span data-stu-id="3df93-383">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="3df93-384">在 [**位長**] 中, 選擇您的位長 (預設值為 2048, 您可以提高安全性, 但會使效能變慢)。</span><span class="sxs-lookup"><span data-stu-id="3df93-384">In **Bit length**, choose your bit length (the default is 2048, you can go higher and be more secure, but it will make performance slow down).</span></span>
    
 <span data-ttu-id="3df93-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;三.</span><span class="sxs-lookup"><span data-stu-id="3df93-385">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii.</span></span> <span data-ttu-id="3df93-386">如果您需要可匯出的憑證, 您必須核取 [將**證書私密金鑰標示為可匯出**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3df93-386">If you need an exportable certificate, you must check the **Mark certificate private key as exportable** check box.</span></span>
    
  <span data-ttu-id="3df93-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv.</span><span class="sxs-lookup"><span data-stu-id="3df93-387">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv.</span></span> <span data-ttu-id="3df93-388">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-388">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-389">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="3df93-389">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="3df93-390">在 [**組織資訊**] 頁面上, 輸入貴組織和組織單位 (OU) 的名稱。</span><span class="sxs-lookup"><span data-stu-id="3df93-390">On the **Organization Information** page, enter the name for your organization and organizational unit (OU).</span></span> <span data-ttu-id="3df93-391">您可以輸入您的部門或部門 (例如)。</span><span class="sxs-lookup"><span data-stu-id="3df93-391">You might enter your division or department (IT, for example).</span></span>
    
<span data-ttu-id="3df93-392">&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-392">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="3df93-393">在 [**地理資訊**] 頁面上, 輸入您的位置資訊。</span><span class="sxs-lookup"><span data-stu-id="3df93-393">On the **Geographical Information** page, enter your location information.</span></span>
    
<span data-ttu-id="3df93-394">&nbsp;&nbsp;&nbsp;韓文.</span><span class="sxs-lookup"><span data-stu-id="3df93-394">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="3df93-395">在 [ **Subject 名稱/Subject 替換名稱**] 頁面上, 嚮導應該會自動填入所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="3df93-395">On the **Subject Name/Subject Alternate Names** page, the needed information should be auto-populated by the wizard.</span></span>
    
<span data-ttu-id="3df93-396">&nbsp;&nbsp;&nbsp;位元組.</span><span class="sxs-lookup"><span data-stu-id="3df93-396">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="3df93-397">在 [**受領人替代名稱 (san)** ] 頁面上的 [SIP 網域設定] 上, 核取 [網域] 核取方塊以新增 SIP。<sipdomain></span><span class="sxs-lookup"><span data-stu-id="3df93-397">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, check the domain checkbox to add a sip.<sipdomain></span></span> <span data-ttu-id="3df93-398">[主題替換名稱] 清單中的專案。</span><span class="sxs-lookup"><span data-stu-id="3df93-398">entry to the subject alternative names list.</span></span>
    
<span data-ttu-id="3df93-399">&nbsp;&nbsp;&nbsp;左.</span><span class="sxs-lookup"><span data-stu-id="3df93-399">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="3df93-400">在 [**設定其他消費者替換名稱**] 頁面上, 您需要新增任何您需要的其他消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="3df93-400">On the **Configure Additional Subject Alternate Names** page, you need to add any additional subject alternative names that you need.</span></span>
    
<span data-ttu-id="3df93-401">&nbsp;&nbsp;&nbsp;m.</span><span class="sxs-lookup"><span data-stu-id="3df93-401">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="3df93-402">在 [**要求摘要**] 頁面上, 查看將要用來產生您要求之憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="3df93-402">On the **Request Summary** page, look over the certificate information that's going to be used to generate your request.</span></span> <span data-ttu-id="3df93-403">如果您需要進行變更, 請返回並立即執行。</span><span class="sxs-lookup"><span data-stu-id="3df93-403">If you need to make changes, go back and do so now.</span></span>
    
<span data-ttu-id="3df93-404">&nbsp;&nbsp;&nbsp;n.</span><span class="sxs-lookup"><span data-stu-id="3df93-404">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="3df93-405">當您準備好時, 請按一下 **[下一步]** , 以產生您需要提供給 CA 的 CSR 檔案 (您也可以按一下 [**查看記錄**] 來查看憑證要求的記錄)。</span><span class="sxs-lookup"><span data-stu-id="3df93-405">When you're ready, click **Next** to generate the CSR file you'll need to provide to the CA (you can also click **View Log** to look at the log for the certificate request).</span></span>
    
<span data-ttu-id="3df93-406">&nbsp;&nbsp;&nbsp;輸出.</span><span class="sxs-lookup"><span data-stu-id="3df93-406">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="3df93-407">在要求產生之後, 您可以按一下 [**查看**] 來查看憑證, 然後按一下 **[完成**] 來關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="3df93-407">Once the request has been generated, you can click **View** to look at the certificate, and **Finish** to close out the window.</span></span> <span data-ttu-id="3df93-408">CSR 檔案的內容需要提供給您的 CA, 因此他們可以在下一節中產生您要匯入到此電腦的憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-408">The contents of the CSR file need to be given to your CA, so they can generate a certificate for you to import to this computer in the next section.</span></span>
    
<span data-ttu-id="3df93-409">&nbsp;&nbsp;&nbsp;修剪.</span><span class="sxs-lookup"><span data-stu-id="3df93-409">&nbsp;&nbsp;&nbsp;p.</span></span> <span data-ttu-id="3df93-410">可選您可以在提交 CSR 的內容時, 要求您提供特定資訊, 如下所示 (CAs 可能會有很大的差異, 因此可能不需要這麼做):</span><span class="sxs-lookup"><span data-stu-id="3df93-410">(OPTIONAL) You may, when submitting the contents of the CSR, be asked for certain information, as follows (CAs vary greatly, so this may not be required):</span></span>
    
  - <span data-ttu-id="3df93-411">**Microsoft**作為伺服器平臺</span><span class="sxs-lookup"><span data-stu-id="3df93-411">**Microsoft** as the server platform</span></span>
    
  - <span data-ttu-id="3df93-412">**IIS**做為版本</span><span class="sxs-lookup"><span data-stu-id="3df93-412">**IIS** as the version</span></span>
    
  - <span data-ttu-id="3df93-413">**網頁伺服器**作為使用類型</span><span class="sxs-lookup"><span data-stu-id="3df93-413">**Web Server** as the usage type</span></span>
    
  - <span data-ttu-id="3df93-414">[ **PKCS7** ] 做為回應格式</span><span class="sxs-lookup"><span data-stu-id="3df93-414">**PKCS7** as the response format</span></span>
    
 
### <a name="2-import-the-certificate"></a><span data-ttu-id="3df93-415">2. 匯入憑證</span><span class="sxs-lookup"><span data-stu-id="3df93-415">2. Import the certificate</span></span>

<span data-ttu-id="3df93-416">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-416">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-417">以本機管理員群組成員的身分登入, 移至最後一個程式中您提出證書要求的邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-417">Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.</span></span>
    
<span data-ttu-id="3df93-418">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-418">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-419">在 [部署嚮導] 的 [**步驟 3] 旁。要求、安裝或指派憑證**, 請**再次**按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="3df93-419">In the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run Again**.</span></span>
    
<span data-ttu-id="3df93-420">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-420">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-421">在 [**可用的憑證**工作] 頁面上, 按一下 [**從 a 匯入憑證]。P7b、.pfx 或 .cer**檔案。</span><span class="sxs-lookup"><span data-stu-id="3df93-421">On the **Available Certificates Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>
    
<span data-ttu-id="3df93-422">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-422">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-423">在 [匯**入憑證**] 頁面上, 輸入您在前一節中取得之憑證的完整路徑和檔案名 (您也可以按一下 **[流覽]** 以尋找並選擇該檔案的方式)。</span><span class="sxs-lookup"><span data-stu-id="3df93-423">On the **Import Certificate** page, type the full path and file name of the certificate you got in the previous section (or you can click **Browse** to find and choose the file that way).</span></span> <span data-ttu-id="3df93-424">如果您的憑證包含私密金鑰, 請務必選取 [**憑證檔案包含憑證的私人金鑰**], 然後輸入私密金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="3df93-424">If your certificate contains a private key, make sure to select **Certificate file contains certificate's private key**, and enter the password for the private key.</span></span> <span data-ttu-id="3df93-425">準備就緒時, 按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="3df93-425">Click **Next** when ready.</span></span>
    
<span data-ttu-id="3df93-426">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-426">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-427">在 [匯**入憑證摘要**] 頁面上, 查看摘要資訊, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-427">On the **Import Certificate Summary** page, review the summary information, and click **Next**.</span></span>
    
<span data-ttu-id="3df93-428">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-428">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-429">在 [**執行命令**] 頁面上, 您可以按一下 [**查看記錄**], 以查看匯入完成後的結果。</span><span class="sxs-lookup"><span data-stu-id="3df93-429">On the **Executing Commands** page, you can review the result of the import when it's complete by clicking **View Log**.</span></span> <span data-ttu-id="3df93-430">按一下 **[完成]** 以完成證書匯入。</span><span class="sxs-lookup"><span data-stu-id="3df93-430">Click **Finish** to complete the certificate import.</span></span>
    
<span data-ttu-id="3df93-431">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="3df93-431">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="3df93-432">如果您在某個池中有其他邊緣伺服器, 您也必須遵循下兩個程式。</span><span class="sxs-lookup"><span data-stu-id="3df93-432">If you have other Edge Servers in a pool, you'll need to follow the next two procedures as well.</span></span> <span data-ttu-id="3df93-433">如果這是獨立的邊緣伺服器, 您就完成了 [外部憑證]。</span><span class="sxs-lookup"><span data-stu-id="3df93-433">If this is a standalone Edge Server, you're done with external certificates.</span></span>
    
 
### <a name="3-export-the-certificate"></a><span data-ttu-id="3df93-434">3. 匯出憑證</span><span class="sxs-lookup"><span data-stu-id="3df93-434">3. Export the certificate</span></span>

<span data-ttu-id="3df93-435">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-435">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-436">請確認您已登入您將憑證匯入為本機系統管理員的邊緣伺服器上。</span><span class="sxs-lookup"><span data-stu-id="3df93-436">Make sure you've logged onto the Edge Server you imported the certificate to as a local Administrator.</span></span>
    
<span data-ttu-id="3df93-437">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-437">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-438">按一下 [**開始**]、[**執行**] (或 [開啟**搜尋**]), 然後輸入 [ **MMC**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-438">Click **Start**, **Run** (or open **Search** ), and type **MMC**.</span></span>
    
<span data-ttu-id="3df93-439">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-439">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-440">從 MMC 主控台, 按一下 [ \*\*\*\* 檔案], 然後按一下 [**新增/移除管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-440">From the MMC console, click **File**, and then click **Add/Remove Snap-in**.</span></span>
    
<span data-ttu-id="3df93-441">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-441">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-442">從 [**新增或移除管理單元**] 方塊中, 按一下 [**憑證**], 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-442">From the **Add or Remove Snap-ins** box, click **Certificates**, and click **Add**.</span></span>
    
<span data-ttu-id="3df93-443">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-443">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-444">在 [**憑證**管理單元] 對話方塊中, 選擇 [**電腦帳戶**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-444">In the **Certificates** snap-in dialog box, choose **Computer account**.</span></span> <span data-ttu-id="3df93-445">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-445">Click **Next**.</span></span>
    
<span data-ttu-id="3df93-446">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-446">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-447">在 [**選取電腦**] 對話方塊中, 選取 [**本機電腦: 執行此主控台的電腦**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-447">On the **Select Computer** dialog, select **Local computer: (the computer this console is running on)**.</span></span> <span data-ttu-id="3df93-448">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-448">Click **Finish**.</span></span> <span data-ttu-id="3df93-449">按一下 **[確定]**, MMC 主控台的設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="3df93-449">Click **OK**, and the configuration of the MMC console is completed.</span></span>
    
<span data-ttu-id="3df93-450">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="3df93-450">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="3df93-451">按兩下 **[憑證 (本機電腦)** ], 展開證書存放區。</span><span class="sxs-lookup"><span data-stu-id="3df93-451">Double-click **Certificates (Local Computer)** to expand the certificate stores.</span></span> <span data-ttu-id="3df93-452">**按兩下 [個人**], 然後按一下 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-452">**Double-click Personal**, and then click **Certificates**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="3df93-453">您可能在這裡, 但在本機電腦的 [憑證個人] 商店中看不到任何憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-453">You may be here, and you don't see any certificates in the Certificates Personal store for the local computer.</span></span> <span data-ttu-id="3df93-454">您不需要搜尋, 如果該索引鍵不在該處, 則匯入的憑證沒有與其相關聯的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="3df93-454">You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it.</span></span> <span data-ttu-id="3df93-455">請稍後再試一次要求和匯入步驟, 如果您確定自己已取得正確的許可權, 請與您的 CA 管理員或提供者通話。</span><span class="sxs-lookup"><span data-stu-id="3df93-455">Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider.</span></span> 
  
<span data-ttu-id="3df93-456">&nbsp;&nbsp;&nbsp;h.</span><span class="sxs-lookup"><span data-stu-id="3df93-456">&nbsp;&nbsp;&nbsp;h.</span></span> <span data-ttu-id="3df93-457">在本機電腦的 [**認證個人] 商店**中, 以滑鼠右鍵按一下您要匯出的憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-457">In the **Certificates Personal store** for the local computer, right-click the certificate that you're exporting.</span></span> <span data-ttu-id="3df93-458">從產生的功能表中**選取 [所有任務**], 然後按一下 [**匯出**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-458">**Select All Tasks** from the resulting menu, and then click **Export**.</span></span>
    
<span data-ttu-id="3df93-459">&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-459">&nbsp;&nbsp;&nbsp;i.</span></span> <span data-ttu-id="3df93-460">在 [**證書匯出嚮導]** 中, 按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-460">In the **Certificate Export Wizard**, click **Next**.</span></span> <span data-ttu-id="3df93-461">選取 **[是, 匯出私人金鑰]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-461">Select **Yes, export the private key**.</span></span> <span data-ttu-id="3df93-462">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-462">Click **Next**.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="3df93-463">如果**是, 匯出私人金鑰**無法使用, 則在您取得此憑證的私密金鑰之前, 沒有標示為匯出。</span><span class="sxs-lookup"><span data-stu-id="3df93-463">If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it.</span></span> <span data-ttu-id="3df93-464">在成功執行此動作之前, 您需要再次從提供者要求證書, 並將私密金鑰設為 [匯出]。</span><span class="sxs-lookup"><span data-stu-id="3df93-464">You need to request the certificate from the provider again, with the private key set to export, before doing this successfully.</span></span>
  
<span data-ttu-id="3df93-465">&nbsp;&nbsp;&nbsp;韓文.</span><span class="sxs-lookup"><span data-stu-id="3df93-465">&nbsp;&nbsp;&nbsp;j.</span></span> <span data-ttu-id="3df93-466">在 [匯出檔案格式] 對話方塊中, 選取 [個人資訊交換-PKCS # 12 (。PFX), 然後選取下列專案:</span><span class="sxs-lookup"><span data-stu-id="3df93-466">On the Export File Formats dialog, select Personal Information Exchange - PKCS#12 (.PFX) and then select the following:</span></span>
    
 <span data-ttu-id="3df93-467">&nbsp;&nbsp;&nbsp;是否.</span><span class="sxs-lookup"><span data-stu-id="3df93-467">&nbsp;&nbsp;&nbsp;  i.</span></span> <span data-ttu-id="3df93-468">如果可能的話, 請將所有憑證包含在憑證路徑中。</span><span class="sxs-lookup"><span data-stu-id="3df93-468">Include all certificates in the certification path, if possible.</span></span>
    
 <span data-ttu-id="3df93-469">&nbsp;&nbsp;&nbsp;第.</span><span class="sxs-lookup"><span data-stu-id="3df93-469">&nbsp;&nbsp;&nbsp;  ii.</span></span> <span data-ttu-id="3df93-470">匯出所有延伸屬性。</span><span class="sxs-lookup"><span data-stu-id="3df93-470">Export all extended properties.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="3df93-471">**如果匯出成功**,**千萬不要**選取 [刪除金鑰]。</span><span class="sxs-lookup"><span data-stu-id="3df93-471">**NEVER** select **Delete the private key if the export is successful**.</span></span> <span data-ttu-id="3df93-472">這表示您必須重新將憑證和私密金鑰重新導入到此 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="3df93-472">It'll mean you have to reimport the certificate and private key back to this Edge Server.</span></span>
  
<span data-ttu-id="3df93-473">&nbsp;&nbsp;&nbsp;位元組.</span><span class="sxs-lookup"><span data-stu-id="3df93-473">&nbsp;&nbsp;&nbsp;k.</span></span> <span data-ttu-id="3df93-474">如果您想要指派密碼來保護私密金鑰, 您可以輸入私人金鑰的密碼。</span><span class="sxs-lookup"><span data-stu-id="3df93-474">If you want to assign a password to protect the private key, you can type a password for the private key.</span></span> <span data-ttu-id="3df93-475">重新輸入密碼以進行確認, 然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-475">Reenter the password to confirm, and then click **Next**.</span></span>
    
<span data-ttu-id="3df93-476">&nbsp;&nbsp;&nbsp;左.</span><span class="sxs-lookup"><span data-stu-id="3df93-476">&nbsp;&nbsp;&nbsp;l.</span></span> <span data-ttu-id="3df93-477">針對匯出的憑證輸入路徑和檔案名, 並使用 **.pfx**副檔名。</span><span class="sxs-lookup"><span data-stu-id="3df93-477">Type a path and file name for the exported certificate, using a file extension of **.pfx**.</span></span> <span data-ttu-id="3df93-478">路徑中的其他邊緣伺服器必須能夠存取路徑, 否則您需要使用外部媒體 (例如 USB 磁片磁碟機) 來移動檔案。</span><span class="sxs-lookup"><span data-stu-id="3df93-478">The path either needs to be accessible by the other Edge Servers in the pool, or you'll need to move the file by means of external media (such as a USB drive).</span></span> <span data-ttu-id="3df93-479">當您進行選擇時, 請按 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="3df93-479">Click **Next** when you've made your choice.</span></span>
    
<span data-ttu-id="3df93-480">&nbsp;&nbsp;&nbsp;m.</span><span class="sxs-lookup"><span data-stu-id="3df93-480">&nbsp;&nbsp;&nbsp;m.</span></span> <span data-ttu-id="3df93-481">在 [**完成證書匯出嚮導**] 對話方塊中查看摘要, 然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-481">Review the summary on the **Completing the Certificate Export Wizard** dialog, and then click **Finish**.</span></span>
    
<span data-ttu-id="3df93-482">&nbsp;&nbsp;&nbsp;n.</span><span class="sxs-lookup"><span data-stu-id="3df93-482">&nbsp;&nbsp;&nbsp;n.</span></span> <span data-ttu-id="3df93-483">按一下 [成功匯出] 對話方塊中的 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-483">Click **OK** in the successful export dialog.</span></span>
    
<span data-ttu-id="3df93-484">&nbsp;&nbsp;&nbsp;輸出.</span><span class="sxs-lookup"><span data-stu-id="3df93-484">&nbsp;&nbsp;&nbsp;o.</span></span> <span data-ttu-id="3df93-485">您現在必須回到前面的 [匯入憑證] 區段, 並將憑證匯入到所有剩餘的邊緣伺服器, 然後繼續進行分派。</span><span class="sxs-lookup"><span data-stu-id="3df93-485">You'll now need to go back to the Import the certificate section prior to this and import the certificate to all your remaining Edge Servers, then proceed with assigning, below.</span></span>
    
 
### <a name="4-assign-the-certificate"></a><span data-ttu-id="3df93-486">4. 指派憑證</span><span class="sxs-lookup"><span data-stu-id="3df93-486">4. Assign the certificate</span></span>

<span data-ttu-id="3df93-487">&nbsp;&nbsp;&nbsp;是.</span><span class="sxs-lookup"><span data-stu-id="3df93-487">&nbsp;&nbsp;&nbsp;a.</span></span> <span data-ttu-id="3df93-488">在**每個**Edge 伺服器的 [部署嚮導] 中, 在**步驟3的旁邊。要求、安裝或指派憑證**, 請**再次**按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="3df93-488">On **EACH** Edge Server, in the Deployment Wizard, next to **Step 3. Request, Install or Assign Certificates**, click **Run again**.</span></span>
    
<span data-ttu-id="3df93-489">&nbsp;&nbsp;&nbsp;乙.</span><span class="sxs-lookup"><span data-stu-id="3df93-489">&nbsp;&nbsp;&nbsp;b.</span></span> <span data-ttu-id="3df93-490">在 [**可用的憑證**工作] 頁面上, 按一下 [**指派現有的憑證**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-490">On the **Available Certificates Tasks** page, click **Assign an existing certificate**.</span></span>
    
<span data-ttu-id="3df93-491">&nbsp;&nbsp;&nbsp;c-clip.</span><span class="sxs-lookup"><span data-stu-id="3df93-491">&nbsp;&nbsp;&nbsp;c.</span></span> <span data-ttu-id="3df93-492">在 [**憑證指派**] 頁面上, 選取清單中的 [**邊緣外部**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-492">On the **Certificate Assignment** page, select **Edge External** in the list.</span></span>
    
<span data-ttu-id="3df93-493">&nbsp;&nbsp;&nbsp;希望.</span><span class="sxs-lookup"><span data-stu-id="3df93-493">&nbsp;&nbsp;&nbsp;d.</span></span> <span data-ttu-id="3df93-494">在 [**憑證存放區**] 頁面上, 選取您針對外部邊緣所匯入的憑證 (從上一節)。</span><span class="sxs-lookup"><span data-stu-id="3df93-494">On the **Certificate Store** page, select the certificate you've imported for the external Edge (from the previous section).</span></span>
    
<span data-ttu-id="3df93-495">&nbsp;&nbsp;&nbsp;e.</span><span class="sxs-lookup"><span data-stu-id="3df93-495">&nbsp;&nbsp;&nbsp;e.</span></span> <span data-ttu-id="3df93-496">在 [**憑證指派摘要**] 頁面上, 查看設定, 然後按一下 **[下一步]** 以指派憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-496">On the **Certificate Assignment Summary** page, look over the settings, and then click **Next** to assign the certificate.</span></span>
    
<span data-ttu-id="3df93-497">&nbsp;&nbsp;&nbsp;°.</span><span class="sxs-lookup"><span data-stu-id="3df93-497">&nbsp;&nbsp;&nbsp;f.</span></span> <span data-ttu-id="3df93-498">在 [嚮導完成] 頁面上, 按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="3df93-498">On the wizard completion page, click **Finish**.</span></span>
    
<span data-ttu-id="3df93-499">&nbsp;&nbsp;&nbsp;7.</span><span class="sxs-lookup"><span data-stu-id="3df93-499">&nbsp;&nbsp;&nbsp;g.</span></span> <span data-ttu-id="3df93-500">完成這個程式後, 建議您在每個伺服器上開啟 [證書] MMC 管理單元、展開 **[憑證 (本機電腦)**]、[展開**個人**]、[**憑證**], 然後確認內部邊緣[詳細資料] 窗格中列出了 [憑證]。</span><span class="sxs-lookup"><span data-stu-id="3df93-500">Once you've completed this procedure, it's a really good idea to open the Certificates MMC snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and confirm that the internal Edge certificate is listed in the details pane.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="3df93-501">您也需要為您的反向 proxy 伺服器設定憑證。</span><span class="sxs-lookup"><span data-stu-id="3df93-501">You will also have needed to set up the certificates for your reverse proxy server.</span></span> 
  
## <a name="starting-the-edge-servers"></a><span data-ttu-id="3df93-502">啟動邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="3df93-502">Starting the Edge Servers</span></span>

<span data-ttu-id="3df93-503">完成設定後, 您必須在部署中的每個 Edge 伺服器上啟動服務:</span><span class="sxs-lookup"><span data-stu-id="3df93-503">Once the setup is complete, you'll need to start the services on each Edge server in your deployment:</span></span>
  
1. <span data-ttu-id="3df93-504">在每個 Edge 伺服器的 [**部署嚮導**] 中, 在 [**步驟 4: 啟動服務**] 旁, 按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-504">On each Edge Server, in the **Deployment Wizard**, next to **Step 4: Start Services**, click **Run**.</span></span>
    
2. <span data-ttu-id="3df93-505">在 [**啟動商務用 Skype 伺服器服務**] 頁面上, 查看服務清單, 然後按一下 **[下一步]** 以啟動服務。</span><span class="sxs-lookup"><span data-stu-id="3df93-505">On the **Start Skype for Business Server Services** page, review the list of services, and then click **Next** to start the services.</span></span>
    
3. <span data-ttu-id="3df93-506">啟動服務之後, 您可以按一下 **[完成**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="3df93-506">After the services are started, you can click **Finish** to close the wizard.</span></span>
    
4. <span data-ttu-id="3df93-507">可選仍在 [**步驟 4: 啟動服務**] 下, 按一下 [**服務狀態**]。</span><span class="sxs-lookup"><span data-stu-id="3df93-507">(Optional) Still under **Step 4: Start Services**, click **Services Status**.</span></span>
    
5.  <span data-ttu-id="3df93-508">在每個伺服器的**服務 MMC**中, 確認所有商務用 Skype server 服務都在執行中。</span><span class="sxs-lookup"><span data-stu-id="3df93-508">In the **Services MMC** on each server, verify that all the Skype for Business Server services are running.</span></span>
    

