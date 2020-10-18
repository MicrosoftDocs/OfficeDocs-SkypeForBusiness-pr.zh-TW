---
title: Lync Server 2013：在 Microsoft Exchange 上設定整合通訊
description: Lync Server 2013：在 Microsoft Exchange 上設定整合通訊。
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
ms.openlocfilehash: 8db43bbe50061a1a044bdd34b637ba86f626ca85
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577519"
---
# <a name="configure-unified-messaging-on-microsoft-exchange-for-lync-server-2013"></a><span data-ttu-id="d5059-103">在 Microsoft Exchange 上設定 Lync Server 2013 的整合通訊</span><span class="sxs-lookup"><span data-stu-id="d5059-103">Configure Unified Messaging on Microsoft Exchange for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5059-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d5059-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="d5059-105">本主題說明如何在 Microsoft Exchange Server 上設定 Exchange 整合通訊 (UM) ，以與 Enterprise Voice 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d5059-105">This topic describes how to configure Exchange Unified Messaging (UM) on a Microsoft Exchange Server for use with Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5059-106">本主題中的 Cmdlet 範例會提供 exchange 2007 版本的 Exchange 管理命令介面的語法。</span><span class="sxs-lookup"><span data-stu-id="d5059-106">The cmdlet examples in this topic provide syntax for the Exchange 2007 version of Exchange Management Shell.</span></span> <span data-ttu-id="d5059-107">如果您正在執行 Exchange 2010 或 Exchange 2013，請參閱參考的適當檔。</span><span class="sxs-lookup"><span data-stu-id="d5059-107">If you are running Exchange 2010 or Exchange 2013, see the appropriate documentation as referenced.</span></span>



</div>

<div>

## <a name="to-configure-a-server-running-exchange-server-um"></a><span data-ttu-id="d5059-108">設定執行 Exchange Server UM 的伺服器</span><span class="sxs-lookup"><span data-stu-id="d5059-108">To configure a server running Exchange Server UM</span></span>

1.  <span data-ttu-id="d5059-109">針對每個企業語音位置設定檔，建立 UM 會話初始通訊協定 (SIP) 統一資源識別項 (URI) 撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="d5059-109">Create a UM Session Initiation Protocol (SIP) Uniform Resource Identifier (URI) dial plan for each of your Enterprise Voice location profiles.</span></span> <span data-ttu-id="d5059-110">如果您選擇使用 Exchange 管理主控台，請建立新的撥號對應表，安全性設定 \*\* (偏好的) \*\*。</span><span class="sxs-lookup"><span data-stu-id="d5059-110">If you choose to use the Exchange Management Console, create a new dial plan with the security setting **Secured (preferred)**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d5059-111">如果您將安全性設定值設定為 <STRONG>Sip 安全</STRONG> ，只需要加密 sip 流量（先前建議使用），請注意，如果前端集區已設定為需要加密，則此撥號對應表上的此安全性設定是不夠的，這表示集區要求對 SIP 和 RTP 流量進行加密。</span><span class="sxs-lookup"><span data-stu-id="d5059-111">If you set your security setting value to <STRONG>SIP Secured</STRONG> to require encryption for SIP traffic only, as previously recommended, note that this security setting on a dial plan is insufficient if the Front End pool is configured to require encryption, which means the pool requires encryption for both SIP and RTP traffic.</span></span> <span data-ttu-id="d5059-112">當撥號對應表與集區安全性設定不相容時，前端集區中的所有 Exchange UM 呼叫將會失敗，並導致錯誤，指出您具有「不相容的安全性設定」。</span><span class="sxs-lookup"><span data-stu-id="d5059-112">When the dial plan and pool security settings are not compatible, all calls to Exchange UM from the Front End pool will fail, resulting in an error indicating that you have an "Incompatible security setting."</span></span>

    
    </div>
    
    <span data-ttu-id="d5059-113">如果您使用 Exchange 管理命令介面，請輸入：</span><span class="sxs-lookup"><span data-stu-id="d5059-113">If you use the Exchange Management Shell, type:</span></span>
    ```powershell
     New-UMDialPlan -Name <dial plan name> -UriType "SipName" -VoipSecurity <SIPSecured|Unsecured|Secured> -NumberOfDigitsInExtension <number of digits> -AccessTelephoneNumbers <access number in E.164 format>
    ```
    <span data-ttu-id="d5059-114">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d5059-114">For details, see:</span></span>
    
      - <span data-ttu-id="d5059-115">如需 Office 通訊伺服器2007，請參閱《如何建立整合通訊 SIP URI 撥號對應表》 [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) 和「New-UMDialplan： Exchange 2007 Help」 at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-115">For Office Communications Server 2007, see "How to Create a Unified Messaging SIP URI Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268632](https://go.microsoft.com/fwlink/p/?linkid=268632) and "New-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268666](https://go.microsoft.com/fwlink/p/?linkid=268666).</span></span>
    
      - <span data-ttu-id="d5059-116">若為 Exchange 2010，請參閱 at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) 和「New-UMDialplan： Exchange 2010 Help "at 中的「建立 UM 撥號對應表」 [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-116">For Exchange 2010, see "Create a UM Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268674](https://go.microsoft.com/fwlink/p/?linkid=268674) and "New-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268680](https://go.microsoft.com/fwlink/p/?linkid=268680).</span></span>
    
      - <span data-ttu-id="d5059-117">若為 Exchange 2013，請參閱的「整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-117">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5059-118">您是否選取 <STRONG>SIPSecured</STRONG> 或安全的安全性層級 <STRONG>，取決於</STRONG> 是否要啟用或停用 (SRTP) 的安全即時傳輸通訊協定，以進行媒體加密。</span><span class="sxs-lookup"><span data-stu-id="d5059-118">Whether you select a security level of <STRONG>SIPSecured</STRONG> or <STRONG>Secured</STRONG> depends on whether secure real-time transport protocol (SRTP) is activated or deactivated for media encryption.</span></span> <span data-ttu-id="d5059-119">對於 Lync Server 2010 與 Exchange UM 的整合，這應該對應至 Lync Server media 設定中的加密層級。</span><span class="sxs-lookup"><span data-stu-id="d5059-119">For the Lync Server 2010 integration with Exchange UM, this should correspond to the encryption level in the Lync Server media configuration.</span></span> <span data-ttu-id="d5059-120">您可以執行 <STRONG>Get-CsMediaConfiguration</STRONG> Cmdlet 來查看 Lync Server 媒體設定。</span><span class="sxs-lookup"><span data-stu-id="d5059-120">The Lync Server media configuration can be viewed by running the <STRONG>Get-CsMediaConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="d5059-121">如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 Get-CsMediaConfiguration。</span><span class="sxs-lookup"><span data-stu-id="d5059-121">For details, see Get-CsMediaConfiguration in the Lync Server Management Shell documentation.</span></span><BR><span data-ttu-id="d5059-122">如需選擇適當 VoIP 安全性設定的詳細資訊，請參閱 <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">整合內部部署整合通訊和 Lync Server 2013 的部署程式</A>。</span><span class="sxs-lookup"><span data-stu-id="d5059-122">For details about selecting the appropriate VoIP Security setting, see <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Deployment process for integrating on-premises Unified Messaging and Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="d5059-123">執行下列 Cmdlet，以取得每個 UM 撥號對應表的完整功能變數名稱 (FQDN) ：</span><span class="sxs-lookup"><span data-stu-id="d5059-123">Run the following cmdlet to obtain the fully qualified domain name (FQDN) for each UM dial plan:</span></span>
    
    ```powershell
    (Get-UMDialPlan <dialplanname>).PhoneContext  
    ```
    
    <span data-ttu-id="d5059-124">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d5059-124">For details, see:</span></span>
    
      - <span data-ttu-id="d5059-125">針對 Exchange 2007，請參閱《 Get-UMDialplan： Exchange 2007 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-125">For Exchange 2007, see "Get-UMDialplan: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268678](https://go.microsoft.com/fwlink/p/?linkid=268678).</span></span>
    
      - <span data-ttu-id="d5059-126">針對 Exchange 2010，請參閱《 Get-UMDialplan： Exchange 2010 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-126">For Exchange 2010, see "Get-UMDialplan: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268679](https://go.microsoft.com/fwlink/p/?linkid=268679).</span></span>
    
      - <span data-ttu-id="d5059-127">若為 Exchange 2013，請參閱的「整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-127">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>

3.  <span data-ttu-id="d5059-128">記錄每個 UM 撥號對應表的撥號對應表名稱。</span><span class="sxs-lookup"><span data-stu-id="d5059-128">Record the dial plan name of each UM dial plan.</span></span> <span data-ttu-id="d5059-129">視 Exchange 伺服器的版本而定，您可能需要將每個撥號對應表名稱的 FQDN 當做每個 UM 撥號對應表對應的 Lync Server 撥號對應表的名稱，以便撥號對應表名稱相符。</span><span class="sxs-lookup"><span data-stu-id="d5059-129">Depending on your version of Exchange Server, you may need to use the FQDN of each dial plan name later as the name of each UM dial plan’s corresponding Lync Server dial plan so that the dial plan names match.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5059-130">只有當 UM 撥號對應表在 exchange 2010 SP1 <EM>之前</EM> 的 exchange 版本上執行時，Lync Server 撥號對應表名稱才必須符合 um 撥號對應表名稱。</span><span class="sxs-lookup"><span data-stu-id="d5059-130">Lync Server dial plan names must match UM dial plan names only if the UM dial plan is running on a version of Exchange <EM>earlier</EM> than Exchange 2010 SP1.</span></span>

    
    </div>

4.  <span data-ttu-id="d5059-131">將撥號對應表新增至執行 Exchange UM 的伺服器，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d5059-131">Add the dial plan to the server running Exchange UM as follows:</span></span>
    
      - <span data-ttu-id="d5059-132">如果您選擇使用 Exchange 管理主控台，您可以從伺服器的屬性工作表中新增撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="d5059-132">If you choose to use the Exchange Management Console, you can add the dial plan from the property sheet for the server.</span></span> <span data-ttu-id="d5059-133">如需詳細指示，請參閱 Exchange Server 產品檔。</span><span class="sxs-lookup"><span data-stu-id="d5059-133">For specific instructions, see the Exchange Server product documentation.</span></span>
        
        <span data-ttu-id="d5059-134">如需 Exchange 2007，請參閱如何將整合通訊伺服器新增至撥號對應表 [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-134">For Exchange 2007, see "How to Add Unified Messaging Server to a Dial Plan" at [https://go.microsoft.com/fwlink/p/?LinkId=268681](https://go.microsoft.com/fwlink/p/?linkid=268681).</span></span>
        
        <span data-ttu-id="d5059-135">針對 Exchange 2010，請參閱「查看或設定 UM 伺服器的屬性」 [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-135">For Exchange 2010, see "View or Configure the Properties of a UM Server" at [https://go.microsoft.com/fwlink/p/?LinkId=268682](https://go.microsoft.com/fwlink/p/?linkid=268682).</span></span>
        
        <span data-ttu-id="d5059-136">若為 Exchange 2013，請參閱的「整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-136">For Exchange 2013, see "Unified Messaging" at [https://go.microsoft.com/fwlink/p/?LinkID=266579](https://go.microsoft.com/fwlink/p/?linkid=266579).</span></span>
    
      - <span data-ttu-id="d5059-137">如果您使用 Exchange 管理命令介面，請針對每個 Exchange UM 伺服器執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d5059-137">If you use the Exchange Management Shell, run the following for each of your Exchange UM servers:</span></span>
        ```powershell
        $ums=get-umserver; 
        $dp=get-umdialplan -id <name of dial-plan created in step 1>; 
        $ums[0].DialPlans +=$dp.Identity; 
        set-umservice -instance $ums[0]
        ```
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5059-138">在執行下列步驟之前，請確定所有的 Enterprise Voice 使用者皆已設定 Exchange Server 信箱。</span><span class="sxs-lookup"><span data-stu-id="d5059-138">Before you perform the following step, make sure that all Enterprise Voice users have been configured with an Exchange Server mailbox.</span></span><BR><span data-ttu-id="d5059-139">若為 Exchange 2007，請參閱 Exchange Server 2007 TechNet 程式庫，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A> 。</span><span class="sxs-lookup"><span data-stu-id="d5059-139">For Exchange 2007, see the Exchange Server 2007 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268685">https://go.microsoft.com/fwlink/p/?LinkId=268685</A>.</span></span><BR><span data-ttu-id="d5059-140">若為 Exchange 2010，請參閱 Exchange Server 2010 TechNet 程式庫，網址為 <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A> 。</span><span class="sxs-lookup"><span data-stu-id="d5059-140">For Exchange 2010, see the Exchange Server 2010 TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268686">https://go.microsoft.com/fwlink/p/?LinkId=268686</A>.</span></span><BR><span data-ttu-id="d5059-141">為您在步驟1中建立的每個撥號對應表指定信箱原則時，請選取 [預設原則] 或您建立的一個。</span><span class="sxs-lookup"><span data-stu-id="d5059-141">When specifying a mailbox policy for each dial plan that you created in step 1, select either the default policy or one that you have created.</span></span>

    
    </div>

5.  <span data-ttu-id="d5059-142">流覽至 [ \<Exchange installation directory\> \\ 腳本]，然後如果 Exchange 部署在單一樹系中，請輸入：</span><span class="sxs-lookup"><span data-stu-id="d5059-142">Navigate to \<Exchange installation directory\>\\Scripts, and then if Exchange is deployed in a single forest, type:</span></span>
    ```console
    exchucutil.ps1
    ```
    <span data-ttu-id="d5059-143">或者，如果 Exchange 部署在多個樹系中，請輸入：</span><span class="sxs-lookup"><span data-stu-id="d5059-143">Or, if Exchange is deployed in multiple forests, type:</span></span>
    ```console
    exchucutil.ps1 -Forest:"<forest FQDN>"
    ```
    <span data-ttu-id="d5059-144">其中，樹系 FQDN 會指定要在其中部署 Lync Server 的樹系。</span><span class="sxs-lookup"><span data-stu-id="d5059-144">where forest FQDN specifies the forest in which Lync Server is deployed.</span></span>
    
    <span data-ttu-id="d5059-145">如果您有一個或多個與多個 IP 閘道相關聯的 UM 撥號對應表，請繼續進行步驟6。</span><span class="sxs-lookup"><span data-stu-id="d5059-145">If you have one or more UM dial plans that are associated with multiple IP gateways, continue to step 6.</span></span> <span data-ttu-id="d5059-146">如果您的撥號對應表彼此只與單一 IP 閘道相關聯，請跳過步驟6。</span><span class="sxs-lookup"><span data-stu-id="d5059-146">If your dial plans are each associated with only a single IP gateway, skip step 6.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5059-147">請務必在執行 exchucutil.ps1 之後<EM></EM>，重新啟動 <STRONG>[Lync Server 前端]</STRONG> 服務 (rtcsrv.exe)。</span><span class="sxs-lookup"><span data-stu-id="d5059-147">Be sure to restart the <STRONG>Lync Server Front-End</STRONG> service (rtcsrv.exe) <EM>after</EM> you run exchucutil.ps1.</span></span> <span data-ttu-id="d5059-148">否則，Lync Server 將不會在拓撲中偵測到整合通訊。</span><span class="sxs-lookup"><span data-stu-id="d5059-148">Otherwise, Lync Server will not detect Unified Messaging in the topology.</span></span>

    
    </div>

6.  <span data-ttu-id="d5059-149">使用 Exchange 管理命令介面或 Exchange 管理主控台，針對所有與您的撥號對應表相關聯的 IP 閘道，停用撥出電話。</span><span class="sxs-lookup"><span data-stu-id="d5059-149">Using either the Exchange Management Shell or Exchange Management Console, disable outbound calling for all but one of the IP gateways associated with each of your dial plans.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5059-150">您必須執行此步驟，才能確保執行 Exchange Server 整合通訊的伺服器撥出電話給外部使用者 (例如，在電話上播放案例) 會以可靠的方式流覽公司防火牆。</span><span class="sxs-lookup"><span data-stu-id="d5059-150">This step is necessary to make sure that outbound calls by the server running Exchange Server Unified Messaging to external users (for example, as is the case with play-on-phone scenarios) reliably traverse the corporate firewall.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5059-151">當您選取允許撥出電話的 UM IP 閘道時，請選擇一種可能處理最多流量的 UM IP 閘道。</span><span class="sxs-lookup"><span data-stu-id="d5059-151">When selecting the UM IP gateway through which to allow outgoing calls, choose the one that is likely to handle the most traffic.</span></span> <span data-ttu-id="d5059-152">不允許透過連接至 Lync Server Director 集區的 IP 閘道來進行傳出流量。</span><span class="sxs-lookup"><span data-stu-id="d5059-152">Do not allow outgoing traffic through an IP gateway that connects to a pool of Lync Server Directors.</span></span> <span data-ttu-id="d5059-153">此外，請避免在另一個中央網站或分支網站上的集區。</span><span class="sxs-lookup"><span data-stu-id="d5059-153">Also avoid pools in another central site or a branch site.</span></span> <span data-ttu-id="d5059-154">您可以使用下列任何一種方法來封鎖撥出的來電，使其無法透過 IP 閘道傳遞：</span><span class="sxs-lookup"><span data-stu-id="d5059-154">You can use either of the following methods to block outgoing calls from passing through an IP gateway:</span></span>

    
    </div>
    
      - <span data-ttu-id="d5059-155">如果您使用 Exchange 管理命令介面，請執行下列命令來停用每個 IP 閘道：</span><span class="sxs-lookup"><span data-stu-id="d5059-155">If you use the Exchange Management Shell, disable each IP gateway by running the following command:</span></span>
        ```powershell
        Set-UMIPGateway <gatewayname> -OutcallsAllowed $false
        ```
        <span data-ttu-id="d5059-156">針對 Exchange 2007，請參閱《 Set-UMIPGateway： Exchange 2007 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-156">For Exchange 2007, see "Set-UMIPGateway: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268687](https://go.microsoft.com/fwlink/p/?linkid=268687).</span></span>
        
        <span data-ttu-id="d5059-157">針對 Exchange 2010，請參閱《 Set-UMIPGateway： Exchange 2010 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-157">For Exchange 2010, see "Set-UMIPGateway: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268688](https://go.microsoft.com/fwlink/p/?linkid=268688).</span></span>
    
      - <span data-ttu-id="d5059-158">如果您使用 Exchange 管理主控台，請清除 [ **允許透過此 IP 閘道的撥出電話** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d5059-158">If you use the Exchange Management Console, clear the **Allow outgoing calls through this IP gateway** check box.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5059-159">如果您的 UM SIP URI 撥號對應表只與單一 IP 閘道相關聯，請勿禁止透過此閘道撥出電話。</span><span class="sxs-lookup"><span data-stu-id="d5059-159">If your UM SIP URI dial plan is associated with only a single IP gateway, do not disallow outgoing calls through this gateway.</span></span>

    
    </div>

7.  <span data-ttu-id="d5059-160">建立每個 Lync Server 撥號對應表的 UM 自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="d5059-160">Create a UM auto-attendant for each Lync Server dial plan.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d5059-161">請勿在自動語音應答名稱中包含任何空格。</span><span class="sxs-lookup"><span data-stu-id="d5059-161">Do not include any spaces in the name of the auto attendant.</span></span>

    
    </div>
    
    ```powershell
    New-umautoattendant -name <auto attendant name> -umdialplan < name of dial plan created in step 1> -PilotIdentifierList <auto attendant phone number in E.164 format> -SpeechEnabled $true -Status Enabled
    ```
    <span data-ttu-id="d5059-162">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d5059-162">For details, see:</span></span>
    
      - <span data-ttu-id="d5059-163">針對 Exchange 2007，請參閱《 New-UMAutoAttendant： Exchange 2007 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-163">For Exchange 2007, see "New-UMAutoAttendant: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268689](https://go.microsoft.com/fwlink/p/?linkid=268689).</span></span>
    
      - <span data-ttu-id="d5059-164">針對 Exchange 2010，請參閱《 New-UMAutoAttendant： Exchange 2010 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-164">For Exchange 2010, see "New-UMAutoAttendant: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268690](https://go.microsoft.com/fwlink/p/?linkid=268690).</span></span>
    
    <span data-ttu-id="d5059-165">在您為企業語音啟用 Lync Server 使用者並知道其 SIP URIs 後，每個使用者都應該執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="d5059-165">The following step should be performed for each user after you have enabled Lync Server users for Enterprise Voice and know their SIP URIs.</span></span>

8.  <span data-ttu-id="d5059-166">建立 Exchange UM 使用者 (每個使用者都應該設定 Exchange 信箱) 與 UM 撥號對應表，並為每位使用者建立 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="d5059-166">Associate Exchange UM users (each of whom should be configured with an Exchange mail box) with the UM dial plan and create a SIP URI for each user.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d5059-167">下列範例中的 <STRONG>SIPResourceIdentifier</STRONG> 必須是 Lync Server 使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="d5059-167">The <STRONG>SIPResourceIdentifier</STRONG> in the following sample must be the SIP address of the Lync Server user.</span></span>

    
    </div>
    
    ```powershell
    enable-ummailbox -id <user name> -ummailboxpolicy <name of the mailbox policy for the dial plan created in step 1> -Extensions <extension> -SIPResourceIdentifier "<user name>@<full domain name>" -PIN <user pin>
    ```
    <span data-ttu-id="d5059-168">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="d5059-168">For details, see:</span></span>
    
      - <span data-ttu-id="d5059-169">針對 Exchange 2007，請參閱《 Enable-UMMailbox： Exchange 2007 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-169">For Exchange 2007, see "Enable-UMMailbox: Exchange 2007 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268691](https://go.microsoft.com/fwlink/p/?linkid=268691).</span></span>
    
      - <span data-ttu-id="d5059-170">針對 Exchange 2010，請參閱《 Enable-UMMailbox： Exchange 2010 Help "at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692) 。</span><span class="sxs-lookup"><span data-stu-id="d5059-170">For Exchange 2010, see "Enable-UMMailbox: Exchange 2010 Help" at [https://go.microsoft.com/fwlink/p/?LinkId=268692](https://go.microsoft.com/fwlink/p/?linkid=268692).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

