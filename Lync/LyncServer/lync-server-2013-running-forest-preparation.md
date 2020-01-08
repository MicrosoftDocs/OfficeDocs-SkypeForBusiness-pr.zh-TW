---
title: Lync Server 2013：執行樹系準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b011623b9091c1c707ae77381dacb99ba4642a21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="00055-102">針對 Lync Server 2013 執行樹系準備</span><span class="sxs-lookup"><span data-stu-id="00055-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00055-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="00055-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="00055-104">您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備目錄林。</span><span class="sxs-lookup"><span data-stu-id="00055-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="00055-105">準備林的 Cmdlet 是**Enable-CsAdForest**。</span><span class="sxs-lookup"><span data-stu-id="00055-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="00055-106">準備好林之後，您必須先確認全域設定已先進行複製，然後再執行網域準備作業。</span><span class="sxs-lookup"><span data-stu-id="00055-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="00055-107">使用安裝程式準備林</span><span class="sxs-lookup"><span data-stu-id="00055-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="00055-108">登入加入網域的電腦，作為林根網域之 [企業系統管理員] 群組的成員。</span><span class="sxs-lookup"><span data-stu-id="00055-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="00055-109">從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="00055-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="00055-110">按一下 [準備 Active Directory]\*\*\*\*，然後等候決定部署狀態。</span><span class="sxs-lookup"><span data-stu-id="00055-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="00055-111">在**步驟3：準備目前的林**，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="00055-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="00055-112">在 [**準備林**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="00055-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00055-113">[林準備] 可讓您選擇要放置 Lync Server 2013 通用群組的位置。</span><span class="sxs-lookup"><span data-stu-id="00055-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="00055-114">請選擇和組織需求一致的位置。</span><span class="sxs-lookup"><span data-stu-id="00055-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="00055-115">在 [執行命令] \*\*\*\* 頁面上，尋找 [工作狀態: 已完成]\*\*\*\*，然後按一下 [檢視記錄檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="00055-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="00055-116">在 [**動作**] 欄底下，展開 [**林準備**]，尋找每個工作結尾的\*\* \<成功\> \*\*執行結果，確認已成功完成 [目錄林準備]，然後關閉記錄，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="00055-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="00055-117">在執行網域準備前，請等候 Active Directory 複製完成，或強制複製到林中根網網域控制站的**Active Directory 網站和服務**管理單元中所列的所有網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="00055-117">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="00055-118">在所有 Active Directory 網站的網網域控制站之間強制進行複製，以在幾分鐘內進行複製。</span><span class="sxs-lookup"><span data-stu-id="00055-118">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="00055-119">使用 Cmdlet 準備林</span><span class="sxs-lookup"><span data-stu-id="00055-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="00055-120">以網域管理員群組的成員身分登入加入網域的電腦（在林根網域中）。</span><span class="sxs-lookup"><span data-stu-id="00055-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="00055-121">安裝 Lync Server Core 元件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="00055-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="00055-122">從 Lync Server 2013 安裝資料夾或媒體，執行 setup.exe 以啟動 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="00055-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="00055-123">如果系統提示您安裝 Microsoft Visual c + + 可轉散發元件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="00055-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="00055-124">[Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="00055-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="00055-125">選擇預設位置，或**流覽**至您選擇的位置，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="00055-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="00055-126">在 [授權協定] 頁面上，核取 [**我接受授權合約中的條款**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="00055-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="00055-127">安裝程式會安裝 Lync Server 2013 核心元件。</span><span class="sxs-lookup"><span data-stu-id="00055-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="00055-128">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="00055-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="00055-129">用盡</span><span class="sxs-lookup"><span data-stu-id="00055-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="00055-130">例如：</span><span class="sxs-lookup"><span data-stu-id="00055-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="00055-131">如果您沒有指定 GroupDomain 參數，則預設值為本地域。</span><span class="sxs-lookup"><span data-stu-id="00055-131">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span> <span data-ttu-id="00055-132">如果通用群組是先前在非預設網域的網域中建立，您必須明確指定 GroupDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="00055-132">If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="00055-133">在執行網域準備前，請等候 Active Directory 複製完成，或強制複製到林中根網網域控制站的**Active Directory 網站和服務**管理單元中所列的所有網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="00055-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="00055-134">確認林準備已成功完成。</span><span class="sxs-lookup"><span data-stu-id="00055-134">Verify that forest preparation was successful.</span></span> <span data-ttu-id="00055-135">用盡</span><span class="sxs-lookup"><span data-stu-id="00055-135">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="00055-136">如果林準備成功，這個 Cmdlet 會傳回**\_LC FORESTSETTINGS\_狀態\_** 的值。</span><span class="sxs-lookup"><span data-stu-id="00055-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="00055-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="00055-137">See Also</span></span>


[<span data-ttu-id="00055-138">使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="00055-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="00055-139">為 Lync Server 2013 準備樹系</span><span class="sxs-lookup"><span data-stu-id="00055-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

