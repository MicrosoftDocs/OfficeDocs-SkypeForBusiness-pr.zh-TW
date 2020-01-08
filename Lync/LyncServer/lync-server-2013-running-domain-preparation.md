---
title: Lync Server 2013：執行網域準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fdd01b15fe5858129300c3a9f2f26c3d3de672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="90e95-102">為 Lync Server 2013 執行網域準備</span><span class="sxs-lookup"><span data-stu-id="90e95-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90e95-103">_**主題上次修改日期：** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="90e95-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="90e95-104">您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備網域。</span><span class="sxs-lookup"><span data-stu-id="90e95-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="90e95-105">準備網域的 Cmdlet 為**Enable-CsAdDomain**。</span><span class="sxs-lookup"><span data-stu-id="90e95-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="90e95-106">[網域準備] 是為 Lync Server 2013 準備 Active Directory 網域服務的最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="90e95-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="90e95-107">使用安裝程式準備網域</span><span class="sxs-lookup"><span data-stu-id="90e95-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="90e95-108">以網域系統管理員群組的成員身分登入網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="90e95-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="90e95-109">從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="90e95-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="90e95-110">按一下 [準備 Active Directory]\*\*\*\*，然後等候決定部署狀態。</span><span class="sxs-lookup"><span data-stu-id="90e95-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="90e95-111">在 [步驟 5：準備目前的網域]\*\*\*\*，按一下 [執行]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90e95-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="90e95-112">在 [**準備網域**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="90e95-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="90e95-113">在 [執行命令]\*\*\*\* 頁面上，尋找 [工作狀態：完成]\*\*\*\*，然後按一下 [檢視記錄檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="90e95-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="90e95-114">在 [**動作**] 欄底下，展開 [**網域準備**]，尋找每個工作\*\* \< \> \*\*結尾的成功執行結果，確認已成功完成 [網域準備]，然後關閉記錄，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="90e95-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="90e95-115">等待 Active Directory 複製完成，或強制複製到林中根網網域控制站之 Active Directory 網站和服務管理單元中列出的所有網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="90e95-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="90e95-116">使用 Cmdlet 準備網域</span><span class="sxs-lookup"><span data-stu-id="90e95-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="90e95-117">以網域系統管理員群組的成員身分登入網域中的任何伺服器。</span><span class="sxs-lookup"><span data-stu-id="90e95-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="90e95-118">安裝 Lync Server Core 元件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="90e95-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="90e95-119">從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="90e95-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="90e95-120">如果系統提示您安裝 Microsoft Visual c + + 可轉散發元件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="90e95-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="90e95-121">[Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="90e95-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="90e95-122">選擇預設位置，或**流覽**至您選擇的位置，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="90e95-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="90e95-123">在 [授權協定] 頁面上，核取 [**我接受授權合約中的條款**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="90e95-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="90e95-124">安裝程式會安裝 Lync Server 2013 核心元件。</span><span class="sxs-lookup"><span data-stu-id="90e95-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="90e95-125">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="90e95-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="90e95-126">用盡</span><span class="sxs-lookup"><span data-stu-id="90e95-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="90e95-127">例如：</span><span class="sxs-lookup"><span data-stu-id="90e95-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="90e95-128">如果您沒有指定 Domain 參數，則預設為本地域。</span><span class="sxs-lookup"><span data-stu-id="90e95-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="90e95-129">確認網域準備順利完成。</span><span class="sxs-lookup"><span data-stu-id="90e95-129">Verify that domain preparation was successful.</span></span> <span data-ttu-id="90e95-130">用盡</span><span class="sxs-lookup"><span data-stu-id="90e95-130">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="90e95-131">例如：</span><span class="sxs-lookup"><span data-stu-id="90e95-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="90e95-132">[參數 GlobalSettingsDomainController] 可讓您指出儲存全域設定的位置。</span><span class="sxs-lookup"><span data-stu-id="90e95-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="90e95-133">如果您的設定是儲存在系統容器中（這通常是將未將全域設定遷移至配置容器的升級部署），您可以在 Active Directory 目錄林的根目錄中定義網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="90e95-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="90e95-134">如果全域設定位於 Configuration 容器中 (在全新部署或升級部署作業期間，當設定已經移轉至 Configuration 容器時的常見現象)，您可以在樹系中定義任何網域控制站。</span><span class="sxs-lookup"><span data-stu-id="90e95-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="90e95-135">如果您沒有指定此參數，Cmdlet 會假設設定會儲存在配置容器中，並參照 AD&nbsp;DS 中的任何網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="90e95-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="90e95-136">如果您沒有指定**Domain**參數，則預設為本地域。</span><span class="sxs-lookup"><span data-stu-id="90e95-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="90e95-137">如果網域準備成功，這個**Cmdlet\_就\_會\_傳回 LC DOMAINSETTINGS 狀態**的值。</span><span class="sxs-lookup"><span data-stu-id="90e95-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="90e95-138">請參閱</span><span class="sxs-lookup"><span data-stu-id="90e95-138">See Also</span></span>


[<span data-ttu-id="90e95-139">將 Cmdlet 用於 Lync Server 2013 的反向網域準備</span><span class="sxs-lookup"><span data-stu-id="90e95-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="90e95-140">針對 Lync Server 2013 準備網域</span><span class="sxs-lookup"><span data-stu-id="90e95-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

