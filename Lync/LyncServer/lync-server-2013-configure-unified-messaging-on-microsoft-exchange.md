---
title: Lync Server 2013：在 Microsoft Exchange 上設定整合通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Unified Messaging on Microsoft Exchange
ms:assetid: 07547968-c59b-4dde-ace4-9fd286933759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398129(v=OCS.15)
ms:contentKeyID: 48183311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edac9ff9b72c00e7520d80c376e49b03a9e35bab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="4b807-102">在 Microsoft Exchange for Lync Server 2013 中設定整合通訊</span><span class="sxs-lookup"><span data-stu-id="4b807-102">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b807-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="4b807-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="4b807-104">本主題描述如何在 Microsoft Exchange Server 上設定 Exchange 整合通訊（UM），以搭配企業語音使用。</span><span class="sxs-lookup"><span data-stu-id="4b807-104">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b807-105">本主題中的 Cmdlet 範例提供 Exchange 2007 版 Exchange 管理命令介面的語法。</span><span class="sxs-lookup"><span data-stu-id="4b807-105">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="4b807-106">如果您執行的是 Exchange 2010 或 Exchange 2013，請參閱參考的相關檔。</span><span class="sxs-lookup"><span data-stu-id="4b807-106">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="4b807-107">若要設定執行 Exchange Server UM 的伺服器</span><span class="sxs-lookup"><span data-stu-id="4b807-107">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="4b807-108">針對您的每個企業語音位置設定檔，建立 UM 會話初始通訊協定（SIP）的統一資源識別項（URI）撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="4b807-108">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="4b807-109">如果您選擇使用 Exchange 管理主控台，請建立一個安全設定為安全的新撥號方案 **（喜好）**。</span><span class="sxs-lookup"><span data-stu-id="4b807-109">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4b807-110">如果將 [安全設定] 值設定為 [ <STRONG>Sip 安全</STRONG>]，且只需要 sip 流量加密（如前所述），請注意，如果將前端池設定為需要加密，則撥號方案的此安全性設定就不足，這表示該池需要對 SIP 與 RTP 流量進行加密。</span><span class="sxs-lookup"><span data-stu-id="4b807-110">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="4b807-111">當撥號方案和池安全性設定不相容時，從前端池呼叫 Exchange UM 的所有呼叫都會失敗，並產生錯誤，指出您有「不相容的安全性設定」。</span><span class="sxs-lookup"><span data-stu-id="4b807-111">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="4b807-112">如果您使用 Exchange 管理命令介面，請輸入：</span><span class="sxs-lookup"><span data-stu-id="4b807-112">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="4b807-113">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4b807-113">For details, see:</span></span>
    
      - <span data-ttu-id="4b807-114">若為 Office 通訊伺服器2007，請參閱「如何建立整合通訊 SIP URI 撥號方案」 [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632)和「新-UMDialplan： Exchange 2007 說明」。 [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666)</span><span class="sxs-lookup"><span data-stu-id="4b807-114">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268632](http://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268666](http://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="4b807-115">若為 Exchange 2010，請參閱「建立 UM 撥號方案」 [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674)和「新-UMDialplan： Exchange 2010 說明」 [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680)。</span><span class="sxs-lookup"><span data-stu-id="4b807-115">For Exchange 2010, see "Create a UM Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268674](http://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268680](http://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="4b807-116">如需 Exchange 2013，請參閱的「整合[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)通訊」。</span><span class="sxs-lookup"><span data-stu-id="4b807-116">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b807-117">您是否選取 [ <STRONG>SIPSecured</STRONG> ] 或 [安全層級] <STRONG>，取決於</STRONG>是否已啟動或停用安全即時傳輸通訊協定（SRTP）以供媒體加密使用。</span><span class="sxs-lookup"><span data-stu-id="4b807-117">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="4b807-118">針對與 Exchange UM 整合的 Lync Server 2010，這應該會對應到 Lync Server 媒體設定中的加密等級。</span><span class="sxs-lookup"><span data-stu-id="4b807-118">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="4b807-119">您可以透過執行<STRONG>CsMediaConfiguration</STRONG> Cmdlet 來查看 Lync Server 媒體設定。</span><span class="sxs-lookup"><span data-stu-id="4b807-119">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="4b807-120">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 CsMediaConfiguration。</span><span class="sxs-lookup"><span data-stu-id="4b807-120">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="4b807-121">如需有關選取適當的 VoIP 安全性設定的詳細資訊，請參閱<A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">整合內部部署整合訊息和 Lync Server 2013 的部署程式</A>。</span><span class="sxs-lookup"><span data-stu-id="4b807-121">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="4b807-122">執行下列 Cmdlet 以取得每個 UM 撥號方案的完整功能變數名稱（FQDN）：</span><span class="sxs-lookup"><span data-stu-id="4b807-122">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="4b807-123">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4b807-123">For details, see:</span></span>
    
      - <span data-ttu-id="4b807-124">若為 Exchange 2007，請參閱 "UMDialplan： Exchange 2007 說明" [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678)。</span><span class="sxs-lookup"><span data-stu-id="4b807-124">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268678](http://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="4b807-125">若為 Exchange 2010，請參閱 "UMDialplan： Exchange 2010 說明" [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679)。</span><span class="sxs-lookup"><span data-stu-id="4b807-125">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268679](http://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="4b807-126">如需 Exchange 2013，請參閱的「整合[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)通訊」。</span><span class="sxs-lookup"><span data-stu-id="4b807-126">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="4b807-127">錄製每個 UM 撥號方案的撥號方案名稱。</span><span class="sxs-lookup"><span data-stu-id="4b807-127">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="4b807-128">根據您的 Exchange Server 版本而定，您可能需要在每個 UM 撥號方案對應的 Lync Server 撥號方案名稱之後，再使用每個撥號方案名稱的 FQDN，使撥號計畫名稱相符。</span><span class="sxs-lookup"><span data-stu-id="4b807-128">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b807-129">如果 UM 撥號方案是在 Exchange 2010 SP1<EM>之前</EM>的 Exchange 版本上執行，則 Lync Server 撥號方案名稱必須符合 um 撥號方案名稱。</span><span class="sxs-lookup"><span data-stu-id="4b807-129">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="4b807-130">將撥號方案新增至執行 Exchange UM 的伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4b807-130">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="4b807-131">如果您選擇使用 Exchange 管理主控台，您可以從伺服器的屬性工作表中新增撥號方案。</span><span class="sxs-lookup"><span data-stu-id="4b807-131">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="4b807-132">如需特定指示，請參閱 Exchange Server 產品檔。</span><span class="sxs-lookup"><span data-stu-id="4b807-132">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="4b807-133">針對 Exchange 2007，請參閱如何將整合通訊伺服器新增至撥號方案」 [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681)。</span><span class="sxs-lookup"><span data-stu-id="4b807-133">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [http://go.microsoft.com/fwlink/p/?LinkId=268681](http://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="4b807-134">若為 Exchange 2010，請參閱「查看或設定 UM 伺服器的屬性」 [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682)。</span><span class="sxs-lookup"><span data-stu-id="4b807-134">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [http://go.microsoft.com/fwlink/p/?LinkId=268682](http://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="4b807-135">如需 Exchange 2013，請參閱的「整合[http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579)通訊」。</span><span class="sxs-lookup"><span data-stu-id="4b807-135">For Exchange 2013, see "Unified Messaging" at [http://go.microsoft.com/fwlink/p/?LinkID=266579](http://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="4b807-136">如果您使用 Exchange 管理命令介面，請針對您的每個 Exchange UM 伺服器執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4b807-136">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b807-137">在執行下列步驟之前，請確認所有企業語音使用者都已設定 Exchange 伺服器信箱。</span><span class="sxs-lookup"><span data-stu-id="4b807-137">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="4b807-138">若為 Exchange 2007，請參閱 Exchange Server 2007 TechNet 文檔<A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>庫。</span><span class="sxs-lookup"><span data-stu-id="4b807-138">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268685">http://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="4b807-139">若為 Exchange 2010，請參閱 Exchange Server 2010 TechNet 文檔<A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>庫。</span><span class="sxs-lookup"><span data-stu-id="4b807-139">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268686">http://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="4b807-140">針對您在步驟1中建立的每個撥號方案指定信箱原則時，請選取您已建立的預設原則。</span><span class="sxs-lookup"><span data-stu-id="4b807-140">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="4b807-141">流覽至\<exchange 安裝目錄\>\\腳本，然後，如果 Exchange 是在單一目錄林中部署，請輸入：</span><span class="sxs-lookup"><span data-stu-id="4b807-141">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="4b807-142">或者，如果 Exchange 是部署在多個目錄林中，請輸入：</span><span class="sxs-lookup"><span data-stu-id="4b807-142">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="4b807-143">其中，目錄林 FQDN 會指定要在其中部署 Lync Server 的林。</span><span class="sxs-lookup"><span data-stu-id="4b807-143">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="4b807-144">如果您有一個或多個與多個 IP 閘道相關聯的 UM 撥號方案，請繼續執行步驟6。</span><span class="sxs-lookup"><span data-stu-id="4b807-144">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="4b807-145">如果您的撥號方案只與單一 IP 閘道相關聯，請跳過步驟6。</span><span class="sxs-lookup"><span data-stu-id="4b807-145">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b807-146">執行 exchucutil<EM>後</EM>，請務必重新開機<STRONG>Lync Server 前端</STRONG>服務（rtcsrv）。</span><span class="sxs-lookup"><span data-stu-id="4b807-146">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="4b807-147">否則，Lync Server 將不會在拓撲中偵測到統一訊息。</span><span class="sxs-lookup"><span data-stu-id="4b807-147">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="4b807-148">使用 Exchange 管理命令介面或 Exchange 管理主控台，除了其中一個與您的撥號方案相關聯的 IP 閘道之外，停用出站通話。</span><span class="sxs-lookup"><span data-stu-id="4b807-148">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b807-149">您必須執行這個步驟，以確保執行 Exchange Server 的傳出通話與外部使用者（例如，與電話撥打電話案例一樣）可靠地穿越企業防火牆。</span><span class="sxs-lookup"><span data-stu-id="4b807-149">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b807-150">選取要允許撥出電話的 UM IP 閘道時，請選擇可能會處理最大交通的通訊。</span><span class="sxs-lookup"><span data-stu-id="4b807-150">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="4b807-151">不要透過連接至 Lync Server 主管池的 IP 閘道來允許傳出流量。</span><span class="sxs-lookup"><span data-stu-id="4b807-151">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="4b807-152">此外，還要避免在另一個中央網站或分支網站中使用池。</span><span class="sxs-lookup"><span data-stu-id="4b807-152">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="4b807-153">您可以使用下列其中一種方法來封鎖撥出的呼叫，讓它透過 IP 閘道傳遞：</span><span class="sxs-lookup"><span data-stu-id="4b807-153">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="4b807-154">如果您使用 Exchange 管理命令介面，請執行下列命令以停用每個 IP 閘道：</span><span class="sxs-lookup"><span data-stu-id="4b807-154">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="4b807-155">若為 Exchange 2007，請參閱 "UMIPGateway： Exchange 2007 說明" [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687)。</span><span class="sxs-lookup"><span data-stu-id="4b807-155">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268687](http://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="4b807-156">若為 Exchange 2010，請參閱 "UMIPGateway： Exchange 2010 說明" [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688)。</span><span class="sxs-lookup"><span data-stu-id="4b807-156">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268688](http://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="4b807-157">如果您使用 Exchange 管理主控台，請清除 [**允許透過此 IP 閘道撥出電話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4b807-157">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b807-158">如果您的 UM SIP URI 撥號方案只與單一 IP 閘道相關聯，請不要透過此閘道禁止撥出通話。</span><span class="sxs-lookup"><span data-stu-id="4b807-158">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="4b807-159">針對每個 Lync Server 撥號方案建立 UM 自動助理。</span><span class="sxs-lookup"><span data-stu-id="4b807-159">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="4b807-160">不要在自動語音應答的名稱中包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="4b807-160">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="4b807-161">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4b807-161">For details, see:</span></span>
    
      - <span data-ttu-id="4b807-162">若為 Exchange 2007，請參閱「新-UMAutoAttendant： Exchange 2007 說明[http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689)」。</span><span class="sxs-lookup"><span data-stu-id="4b807-162">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268689](http://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="4b807-163">若為 Exchange 2010，請參閱「新-UMAutoAttendant： Exchange 2010 說明[http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690)」。</span><span class="sxs-lookup"><span data-stu-id="4b807-163">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268690](http://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="4b807-164">當您已為企業語音啟用 Lync Server 使用者並知道其 SIP Uri 之後，就應該針對每位使用者執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="4b807-164">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="4b807-165">將 Exchange UM 使用者（每位使用者都應該使用 Exchange 信箱設定）與 UM 撥號方案建立關聯，並為每位使用者建立 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="4b807-165">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4b807-166">下列範例中的<STRONG>SIPResourceIdentifier</STRONG>必須是 Lync Server 使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="4b807-166">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="4b807-167">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4b807-167">For details, see:</span></span>
    
      - <span data-ttu-id="4b807-168">若為 Exchange 2007，請參閱 "Enable-UMMailbox： Exchange 2007 說明[http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691)"。</span><span class="sxs-lookup"><span data-stu-id="4b807-168">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268691](http://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="4b807-169">若為 Exchange 2010，請參閱 "Enable-UMMailbox： Exchange 2010 說明[http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692)"。</span><span class="sxs-lookup"><span data-stu-id="4b807-169">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [http://go.microsoft.com/fwlink/p/?LinkId=268692](http://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

