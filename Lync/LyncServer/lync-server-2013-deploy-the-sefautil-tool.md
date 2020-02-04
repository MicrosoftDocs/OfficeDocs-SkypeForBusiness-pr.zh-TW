---
title: Lync Server 2013：部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729613"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="57b94-102">在 Lync Server 2013 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="57b94-102">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57b94-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="57b94-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="57b94-104">若要部署和管理群組呼叫挑選，您需要使用 SEFAUtil 資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="57b94-104">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="57b94-105">此工具是 Lync Server 2013 資源套件工具的一部分。</span><span class="sxs-lookup"><span data-stu-id="57b94-105">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="57b94-106">您必須先在拓撲中擁有受信任的應用程式池，並將 SEFAUtil 指定為信任的應用程式，並啟用拓撲，才能安裝 SEFAUtil。</span><span class="sxs-lookup"><span data-stu-id="57b94-106">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="57b94-107">Microsoft 整合通訊管理 API （UCMA）3.0 核心 SDK 必須安裝在任何您打算執行 SEFAUtil 工具的電腦上。</span><span class="sxs-lookup"><span data-stu-id="57b94-107">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="57b94-108">您可以在部署的任何前端池中執行 SEFAUtil。</span><span class="sxs-lookup"><span data-stu-id="57b94-108">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="57b94-109">如需有關執行 SEFAUtil 的詳細資訊，請參閱 Technet 博客文章：「如何取得 SEFAutil 執行？」</span><span class="sxs-lookup"><span data-stu-id="57b94-109">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="57b94-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>。</span><span class="sxs-lookup"><span data-stu-id="57b94-110">at <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="57b94-111">若要部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="57b94-111">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="57b94-112">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="57b94-112">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="57b94-113">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="57b94-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="57b94-114">SEFAUtil 工具只能在屬於受信任的應用程式池的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="57b94-114">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="57b94-115">如有需要，請為您打算執行 SEFAUtil 的前端池定義受信任的應用程式池。</span><span class="sxs-lookup"><span data-stu-id="57b94-115">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="57b94-116">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="57b94-116">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="57b94-117">將 SEFAUtil 工具定義為受信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="57b94-117">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="57b94-118">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="57b94-118">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="57b94-119">如有需要，您可以使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="57b94-119">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="57b94-120">使用您的變更啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="57b94-120">Enable the topology with your changes.</span></span> <span data-ttu-id="57b94-121">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="57b94-121">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="57b94-122">在您在步驟3中建立之受信任的應用程式池中的前端伺服器上，安裝 Lync Server 2013 資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="57b94-122">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="57b94-123">確認 SEFAUtil 工具正常運作，如下所示：</span><span class="sxs-lookup"><span data-stu-id="57b94-123">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="57b94-124">從具有系統管理員許可權的 Windows 命令提示字元執行該工具，以在您的部署中顯示使用者的來電轉接設定。</span><span class="sxs-lookup"><span data-stu-id="57b94-124">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="57b94-125">此工具位於 \Program Files\Microsoft Lync Server 2013 \ Reskit。</span><span class="sxs-lookup"><span data-stu-id="57b94-125">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="57b94-126">顯示使用者的 [來電轉接] 設定。</span><span class="sxs-lookup"><span data-stu-id="57b94-126">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="57b94-127">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="57b94-127">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="57b94-128">隨即會顯示使用者的 [來電轉接] 設定。</span><span class="sxs-lookup"><span data-stu-id="57b94-128">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

