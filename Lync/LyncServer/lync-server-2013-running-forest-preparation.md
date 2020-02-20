---
title: Lync Server 2013： 執行樹系準備
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
ms.openlocfilehash: df862c99d05ea27a305a9965e9026065ecfe7792
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="71834-102">執行 Lync Server 2013 的樹系準備</span><span class="sxs-lookup"><span data-stu-id="71834-102">Running forest preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71834-103">_**主題上次修改日期：** 2012年-10-29_</span><span class="sxs-lookup"><span data-stu-id="71834-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="71834-104">您可以使用安裝程式或 Lync Server 管理命令介面指令程式來準備樹系。</span><span class="sxs-lookup"><span data-stu-id="71834-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="71834-105">準備樹系的 cmdlet 是**Enable-csadforest**。</span><span class="sxs-lookup"><span data-stu-id="71834-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="71834-106">準備樹系之後，您必須確認通用設定都已複寫之前執行網域準備作業。</span><span class="sxs-lookup"><span data-stu-id="71834-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="71834-107">若要使用安裝程式來準備樹系</span><span class="sxs-lookup"><span data-stu-id="71834-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="71834-108">登入已加入網域的樹系根網域 Enterprise Admins 群組成員身分的電腦。</span><span class="sxs-lookup"><span data-stu-id="71834-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="71834-109">從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 [部署精靈。</span><span class="sxs-lookup"><span data-stu-id="71834-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="71834-110">按一下 **[準備 Active Directory]**，然後等候決定部署狀態。</span><span class="sxs-lookup"><span data-stu-id="71834-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="71834-111">在**步驟 3： 準備目前樹系**，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="71834-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="71834-112">在 [**準備樹系**] 頁面上，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="71834-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71834-113">樹系準備可讓您選擇的位置 Lync Server 2013 的萬用群組。</span><span class="sxs-lookup"><span data-stu-id="71834-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="71834-114">請選擇和組織需求一致的位置。</span><span class="sxs-lookup"><span data-stu-id="71834-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="71834-115">在「執行命令」\*\*\*\* 頁面上，尋找 [工作狀態: 已完成]\*\*\*\*，然後按一下 [檢視記錄檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="71834-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="71834-116">在 [**動作**] 欄中，依序展開 [**樹系準備**]，並尋找**\<成功\>** 的每一項工作結尾的執行結果，若要確認已順利完成樹系準備，關閉記錄檔，然後按一下 [**完成]**。</span><span class="sxs-lookup"><span data-stu-id="71834-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="71834-117">等候 Active Directory 複寫完成，或是強制複寫到所有網域控制站列在 [ **Active Directory 站台及服務**嵌入式管理單元中樹系根網域控制站，再執行網域準備作業。</span><span class="sxs-lookup"><span data-stu-id="71834-117">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="71834-118">強制導致複寫分鐘內發生的站台內的所有 Active Directory 站台的網域控制站之間的複寫。</span><span class="sxs-lookup"><span data-stu-id="71834-118">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="71834-119">若要使用 cmdlet 準備樹系</span><span class="sxs-lookup"><span data-stu-id="71834-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="71834-120">登入已加入網域的樹系根網域中 Domain Admins 群組成員身分的電腦。</span><span class="sxs-lookup"><span data-stu-id="71834-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="71834-121">安裝 Lync Server 核心元件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="71834-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="71834-122">從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署精靈。</span><span class="sxs-lookup"><span data-stu-id="71834-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="71834-123">如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="71834-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="71834-124">Lync Server 2013 安裝程式] 對話方塊會提示您安裝 Lync Server 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="71834-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="71834-125">請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。</span><span class="sxs-lookup"><span data-stu-id="71834-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="71834-126">在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="71834-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="71834-127">安裝程式會安裝 Lync Server 2013 核心元件。</span><span class="sxs-lookup"><span data-stu-id="71834-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="71834-128">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="71834-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="71834-129">執行：</span><span class="sxs-lookup"><span data-stu-id="71834-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="71834-130">例如：</span><span class="sxs-lookup"><span data-stu-id="71834-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="71834-131">如果您未指定 GroupDomain 參數，預設值為本機網域。</span><span class="sxs-lookup"><span data-stu-id="71834-131">If you do not specify the GroupDomain parameter, the default value is the local domain.</span></span> <span data-ttu-id="71834-132">如果不是預設網域的網域中先前建立萬用群組，您必須明確指定 GroupDomain 參數。</span><span class="sxs-lookup"><span data-stu-id="71834-132">If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="71834-133">等候 Active Directory 複寫完成，或是強制複寫到所有網域控制站列在 [ **Active Directory 站台及服務**嵌入式管理單元中樹系根網域控制站，再執行網域準備作業。</span><span class="sxs-lookup"><span data-stu-id="71834-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="71834-134">確認樹系準備成功。</span><span class="sxs-lookup"><span data-stu-id="71834-134">Verify that forest preparation was successful.</span></span> <span data-ttu-id="71834-135">執行：</span><span class="sxs-lookup"><span data-stu-id="71834-135">Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="71834-136">此 cmdlet 會傳回的值為**小寫\_FORESTSETTINGS\_狀態\_好**如果樹系準備是否成功。</span><span class="sxs-lookup"><span data-stu-id="71834-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71834-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="71834-137">See Also</span></span>


[<span data-ttu-id="71834-138">使用 cmdlet 反向樹系準備 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71834-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="71834-139">準備樹系的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71834-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

