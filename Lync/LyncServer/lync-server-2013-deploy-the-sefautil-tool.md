---
title: Lync Server 2013：部署 SEFAUtil 工具
description: Lync Server 2013：部署 SEFAUtil 工具。
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
ms.openlocfilehash: 311f14f33dff30b388836a7f02483c4afe5da1b1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558609"
---
# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a><span data-ttu-id="0c856-103">在 Lync Server 2013 中部署 SEFAUtil 工具</span><span class="sxs-lookup"><span data-stu-id="0c856-103">Deploy the SEFAUtil tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c856-104">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="0c856-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="0c856-105">若要部署及管理群組通話，您必須使用 SEFAUtil 資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="0c856-105">To deploy and manage Group Call Pickup, you need to use the SEFAUtil resource kit tool.</span></span> <span data-ttu-id="0c856-106">工具屬於 Lync Server 2013 資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="0c856-106">The tool is part of the Lync Server 2013 resource kit tools.</span></span> <span data-ttu-id="0c856-107">在您安裝 SEFAUtil 之前，您必須在拓撲中有信任的應用程式集區，並將 SEFAUtil 指定為信任的應用程式，並啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="0c856-107">Before you can install SEFAUtil, you must have a trusted application pool in your topology, specify SEFAUtil as a trusted application, and enable the topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0c856-108">Microsoft 整合通訊 Managed API (UCMA) 3.0 核心 SDK 必須安裝在您計畫執行 SEFAUtil 工具的任何電腦上。</span><span class="sxs-lookup"><span data-stu-id="0c856-108">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span>



</div>

<span data-ttu-id="0c856-109">您可以在部署中的任何前端集區中執行 SEFAUtil。</span><span class="sxs-lookup"><span data-stu-id="0c856-109">You can run the SEFAUtil in any Front End pool in your deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c856-110">如需有關執行 SEFAUtil 的詳細資訊，請參閱 Technet 博客文章：「如何取得 SEFAutil？」？</span><span class="sxs-lookup"><span data-stu-id="0c856-110">For more details about running SEFAUtil, see the Technet blog article, "How to get SEFAutil running?"</span></span> <span data-ttu-id="0c856-111">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A> 。</span><span class="sxs-lookup"><span data-stu-id="0c856-111">at <A href="https://go.microsoft.com/fwlink/?linkid=278940">https://go.microsoft.com/fwlink/?LinkId=278940</A>.</span></span>



</div>

<div>

## <a name="to-deploy-sefautil"></a><span data-ttu-id="0c856-112">若要部署 SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="0c856-112">To deploy SEFAUtil</span></span>

1.  <span data-ttu-id="0c856-113">以 [Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="0c856-113">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0c856-114">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="0c856-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0c856-115">SEFAUtil 工具只能在屬於受信任應用程式集區一部分的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="0c856-115">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="0c856-116">如有需要，針對您計畫執行 SEFAUtil 的前端集區定義信任的應用程式集區。</span><span class="sxs-lookup"><span data-stu-id="0c856-116">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="0c856-117">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="0c856-117">At the command line, run:</span></span>
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  <span data-ttu-id="0c856-118">將 SEFAUtil 工具定義為信任的應用程式。</span><span class="sxs-lookup"><span data-stu-id="0c856-118">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="0c856-119">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="0c856-119">At the command line, run:</span></span>
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0c856-120">如有需要，您可以使用不同的埠。</span><span class="sxs-lookup"><span data-stu-id="0c856-120">You can use a different port if needed.</span></span>

    
    </div>

5.  <span data-ttu-id="0c856-121">使用您的變更來啟用拓撲。</span><span class="sxs-lookup"><span data-stu-id="0c856-121">Enable the topology with your changes.</span></span> <span data-ttu-id="0c856-122">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="0c856-122">At the command line, run:</span></span>
    
        Enable-CsTopology

6.  <span data-ttu-id="0c856-123">在您于步驟3建立的受信任應用程式集區中的前端伺服器上，安裝 Lync Server 2013 資源工具組工具。</span><span class="sxs-lookup"><span data-stu-id="0c856-123">Install the Lync Server 2013 resource kit tools on a Front End Server that is in the trusted application pool that you created in step 3.</span></span>

7.  <span data-ttu-id="0c856-124">請確認 SEFAUtil 工具是否運作正常，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0c856-124">Verify that the SEFAUtil tool is running correctly, as follows:</span></span>
    
    1.  <span data-ttu-id="0c856-125">從具有管理員許可權的 Windows 命令提示字元執行工具，以顯示部署中使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="0c856-125">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0c856-126">工具位於 \Program Files\Microsoft Lync Server 2013 \ Reskit。</span><span class="sxs-lookup"><span data-stu-id="0c856-126">The tool is located at \Program Files\Microsoft Lync Server 2013\Reskit.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="0c856-127">顯示使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="0c856-127">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="0c856-128">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="0c856-128">At the command line, run:</span></span>
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        <span data-ttu-id="0c856-129">將會顯示使用者的「來電轉接」設定。</span><span class="sxs-lookup"><span data-stu-id="0c856-129">The call forwarding settings for the user will be displayed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

