---
title: Lync Server 2013：執行樹系準備
description: Lync Server 2013：執行樹系準備。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad3ef2d7583d541701d6606946ca1df1bbd8cf23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577759"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="e8145-103">對 Lync Server 2013 執行樹系準備</span><span class="sxs-lookup"><span data-stu-id="e8145-103">Running forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8145-104">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e8145-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e8145-105">您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備樹系。</span><span class="sxs-lookup"><span data-stu-id="e8145-105">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="e8145-106">準備樹系的 Cmdlet 是 **Enable-CsAdForest**。</span><span class="sxs-lookup"><span data-stu-id="e8145-106">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="e8145-107">準備好樹系之後，您必須在執行網域準備作業之前，先確認全域設定是否已複製。</span><span class="sxs-lookup"><span data-stu-id="e8145-107">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="e8145-108">若要使用安裝程式來準備樹系</span><span class="sxs-lookup"><span data-stu-id="e8145-108">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="e8145-109">以樹系根域的 Enterprise Admins 群組成員身分登入加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="e8145-109">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="e8145-110">從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8145-110">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="e8145-111">按一下 **[準備 Active Directory]**，然後等候決定部署狀態。</span><span class="sxs-lookup"><span data-stu-id="e8145-111">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="e8145-112">在 [ **步驟3：準備目前的樹**系] 中，按一下 [ **執行**]。</span><span class="sxs-lookup"><span data-stu-id="e8145-112">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="e8145-113">在 [ **準備樹** 系] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e8145-113">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8145-114">樹系準備可讓您選擇放置 Lync Server 2013 通用群組的位置。</span><span class="sxs-lookup"><span data-stu-id="e8145-114">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="e8145-115">請選擇和組織需求一致的位置。</span><span class="sxs-lookup"><span data-stu-id="e8145-115">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="e8145-116">在「執行命令」\*\*\*\* 頁面上，尋找 [工作狀態: 已完成]\*\*\*\*，然後按一下 [檢視記錄檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e8145-116">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="e8145-117">在 [ **動作** ] 欄下，展開 [ **樹系準備**]，尋找 **\<Success\>** 每項工作結尾的執行結果，以驗證樹系準備是否順利完成，關閉記錄檔，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e8145-117">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="e8145-118">等候 Active Directory 複寫完成，或是強制複寫到樹系根域控制 **站 [Active Directory 網站和服務** ] 嵌入式管理單元中列出的所有網域控制站，然後再執行網域準備作業。</span><span class="sxs-lookup"><span data-stu-id="e8145-118">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="e8145-119">強制在所有 Active Directory 網站的網域控制站之間進行複寫，以在幾分鐘內進行網站的複寫。</span><span class="sxs-lookup"><span data-stu-id="e8145-119">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="e8145-120">若要使用 Cmdlet 準備樹系</span><span class="sxs-lookup"><span data-stu-id="e8145-120">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="e8145-121">以樹系根域的 Domain Admins 群組成員身分登入加入網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="e8145-121">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="e8145-122">安裝 Lync Server 核心元件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e8145-122">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="e8145-123">從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8145-123">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="e8145-124">如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e8145-124">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="e8145-125">[Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="e8145-125">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="e8145-126">請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。</span><span class="sxs-lookup"><span data-stu-id="e8145-126">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="e8145-127">在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e8145-127">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="e8145-128">安裝程式會安裝 Lync Server 2013 核心元件。</span><span class="sxs-lookup"><span data-stu-id="e8145-128">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="e8145-129">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="e8145-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="e8145-130">運行：</span><span class="sxs-lookup"><span data-stu-id="e8145-130">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="e8145-131">例如：</span><span class="sxs-lookup"><span data-stu-id="e8145-131">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="e8145-132">如果您未指定 GroupDomain 參數，則預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="e8145-132">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span> <span data-ttu-id="e8145-133">如果通用群組先前是在非預設網域的網域中建立，您必須明確地指定 GroupDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="e8145-133">If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="e8145-134">等候 Active Directory 複寫完成，或是強制複寫到樹系根域控制 **站 [Active Directory 網站和服務** ] 嵌入式管理單元中列出的所有網域控制站，然後再執行網域準備作業。</span><span class="sxs-lookup"><span data-stu-id="e8145-134">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="e8145-135">確認樹系準備成功。</span><span class="sxs-lookup"><span data-stu-id="e8145-135">Verify that forest preparation was successful.</span></span> <span data-ttu-id="e8145-136">運行：</span><span class="sxs-lookup"><span data-stu-id="e8145-136">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="e8145-137">若樹系準備成功，則此 Cmdlet 會傳回 \*\*LC \_ FORESTSETTINGS \_ 狀態 \_ \*\* 的值。</span><span class="sxs-lookup"><span data-stu-id="e8145-137">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e8145-138">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e8145-138">See Also</span></span>


[<span data-ttu-id="e8145-139">使用 Cmdlet 進行 Lync Server 2013 的反向樹系準備</span><span class="sxs-lookup"><span data-stu-id="e8145-139">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="e8145-140">準備 Lync Server 2013 的樹系</span><span class="sxs-lookup"><span data-stu-id="e8145-140">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

