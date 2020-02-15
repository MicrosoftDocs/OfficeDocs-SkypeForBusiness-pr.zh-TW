---
title: Lync Server 2013： 執行網域準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 960a3664bb7b629a9d66b375d072f826ed9e2738
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="6b6e0-102">執行網域準備 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b6e0-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b6e0-103">_**上次修改主題：** 2013年-04-16_</span><span class="sxs-lookup"><span data-stu-id="6b6e0-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="6b6e0-104">您可以使用安裝程式或 Lync Server 管理命令介面指令程式來準備網域。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="6b6e0-105">準備網域指令程式會**Enable-csaddomain**。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="6b6e0-106">網域準備是準備 Lync Server 2013 的 Active Directory 網域服務的最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="6b6e0-107">若要使用安裝程式來準備網域</span><span class="sxs-lookup"><span data-stu-id="6b6e0-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="6b6e0-108">以 Domain Admins 群組成員的身分登入網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="6b6e0-109">從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署精靈。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="6b6e0-110">按一下 **[準備 Active Directory]**，然後等候決定部署狀態。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="6b6e0-111">在 **[步驟 5：準備目前的網域]**，按一下 **[執行]**。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="6b6e0-112">在 [**準備網域**] 頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="6b6e0-113">在「執行命令」\*\*\*\* 頁面上，尋找 [工作狀態: 已完成]\*\*\*\*，然後按一下 [檢視記錄檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="6b6e0-114">在 [**動作**] 欄中，依序展開 [**網域準備**]，並尋找**\<成功\>** 的每一項工作結尾的執行結果，若要確認已順利完成網域準備，關閉記錄檔，然後按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="6b6e0-115">等候 Active Directory 複寫完成，或是強制複寫到所有網域控制站 [Active Directory 站台及服務] 嵌入式管理單元中樹系根網域控制站列出。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="6b6e0-116">若要使用 Cmdlet 準備網域</span><span class="sxs-lookup"><span data-stu-id="6b6e0-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="6b6e0-117">以 Domain Admins 群組成員的身分登入網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="6b6e0-118">安裝 Lync Server 核心元件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6b6e0-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="6b6e0-119">從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署精靈。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="6b6e0-120">如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="6b6e0-121">Lync Server 2013 安裝程式] 對話方塊會提示您安裝 Lync Server 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="6b6e0-122">請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="6b6e0-123">在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="6b6e0-124">安裝程式會安裝 Lync Server 2013 核心元件。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="6b6e0-125">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="6b6e0-126">執行：</span><span class="sxs-lookup"><span data-stu-id="6b6e0-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="6b6e0-127">例如：</span><span class="sxs-lookup"><span data-stu-id="6b6e0-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="6b6e0-128">如果不指定 Domain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="6b6e0-129">確認網域準備成功。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-129">Verify that domain preparation was successful.</span></span> <span data-ttu-id="6b6e0-130">執行：</span><span class="sxs-lookup"><span data-stu-id="6b6e0-130">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="6b6e0-131">例如：</span><span class="sxs-lookup"><span data-stu-id="6b6e0-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6b6e0-132">GlobalSettingsDomainController 參數可讓您指出通用設定的存放位置。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="6b6e0-133">如果您的設定會儲存在將系統容器 (也就是一般升級部署未有通用設定移轉至組態容器)，在您的 Active Directory 樹系根中定義的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="6b6e0-134">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="6b6e0-135">如果您未指定此參數，指令程式會假設此設定會儲存在 [Configuration] 容器，且所參照的任何網域控制站 AD&nbsp;DS。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="6b6e0-136">如果您不指定**Domain**參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="6b6e0-137">此 cmdlet 會傳回的值為**小寫\_DOMAINSETTINGS\_狀態\_好**如果網域準備是否成功。</span><span class="sxs-lookup"><span data-stu-id="6b6e0-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b6e0-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6b6e0-138">See Also</span></span>


[<span data-ttu-id="6b6e0-139">使用 cmdlet 來反轉網域準備 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b6e0-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="6b6e0-140">Lync Server 2013 的準備網域</span><span class="sxs-lookup"><span data-stu-id="6b6e0-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

