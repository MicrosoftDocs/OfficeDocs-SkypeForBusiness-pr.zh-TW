---
title: Lync Server 2013：執行架構準備
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12dda05b36406e620c08abac494dceecc7d314d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="ce648-102">在 Lync Server 2013 中執行 Active Directory 架構準備</span><span class="sxs-lookup"><span data-stu-id="ce648-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce648-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="ce648-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="ce648-104">您可以使用安裝程式或 Lync Server 管理命令介面 Cmdlet 來準備 Active Directory 架構。</span><span class="sxs-lookup"><span data-stu-id="ce648-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="ce648-105">擴充 Active Directory 架構的指令程式已**Install-CsAdServerSchema**。</span><span class="sxs-lookup"><span data-stu-id="ce648-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce648-106">架構準備指令程式 (<STRONG>Install-CsAdServerSchema</STRONG>) 必須存取架構主機，這需要遠端登入服務執行，且已啟用遠端登入機碼。</span><span class="sxs-lookup"><span data-stu-id="ce648-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="ce648-107">如果無法在架構主機上啟用遠端登入服務，您可以在架構主機上以本機方式執行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce648-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="ce648-108">如需有關登錄遠端存取的詳細資訊，請參閱 Microsoft 知識庫文章314837：如何管理登錄的遠端存取，位置是 <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> 。</span><span class="sxs-lookup"><span data-stu-id="ce648-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="ce648-109">完成架構準備工作之後，請在繼續進行樹系準備之前，手動驗證架構磁碟分割是否已複製。</span><span class="sxs-lookup"><span data-stu-id="ce648-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="ce648-110">如需詳細資訊，請參閱[在 Lync Server 2013 中驗證 Active Directory 架構](lync-server-2013-verifying-schema-replication.md)複寫。</span><span class="sxs-lookup"><span data-stu-id="ce648-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="ce648-111">若要使用安裝程式來準備目前樹系的架構</span><span class="sxs-lookup"><span data-stu-id="ce648-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="ce648-112">以架構管理員群組成員的身分，以架構主機上的系統管理員許可權，登入樹系中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce648-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="ce648-113">從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="ce648-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="ce648-114">如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="ce648-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="ce648-115">[Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="ce648-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="ce648-116">請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。</span><span class="sxs-lookup"><span data-stu-id="ce648-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="ce648-117">在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ce648-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="ce648-118">安裝程式會安裝 Lync Server 核心元件。</span><span class="sxs-lookup"><span data-stu-id="ce648-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="ce648-119">當部署嚮導準備好時，請按一下 [**準備 Active Directory**]，然後等候決定部署狀態。</span><span class="sxs-lookup"><span data-stu-id="ce648-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="ce648-120">在 [**步驟1：準備架構**] 中，按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="ce648-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="ce648-121">在 [**準備架構**] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce648-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="ce648-122">在「執行命令」\*\*\*\* 頁面上，尋找 [工作狀態: 已完成]\*\*\*\*，然後按一下 [檢視記錄檔]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ce648-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="ce648-123">在 [**動作**] 欄下，展開 [**架構準備**]，並在每個工作結束時尋找\*\* \< 成功 \> \*\*執行結果，以確認架構準備順利完成，關閉記錄檔，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="ce648-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="ce648-124">等候 Active Directory 複寫完成或強制複寫。</span><span class="sxs-lookup"><span data-stu-id="ce648-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="ce648-125">手動驗證架構變更是否已複寫至其他所有的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="ce648-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="ce648-126">如需詳細資訊，請參閱[在 Lync Server 2013 中驗證 Active Directory 架構](lync-server-2013-verifying-schema-replication.md)複寫。</span><span class="sxs-lookup"><span data-stu-id="ce648-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="ce648-127">若要使用 Cmdlet 準備目前樹系的架構</span><span class="sxs-lookup"><span data-stu-id="ce648-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="ce648-128">以架構管理員群組成員的身分，以架構主機上的系統管理員許可權，登入樹系中的電腦。</span><span class="sxs-lookup"><span data-stu-id="ce648-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="ce648-129">安裝 Lync Server 核心元件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ce648-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="ce648-130">從 Lync Server 2013 安裝資料夾或媒體，執行 Setup.exe 以啟動 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="ce648-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="ce648-131">如果系統提示您安裝 Microsoft Visual C++ 可轉散發套件，請按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="ce648-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="ce648-132">[Lync Server 2013 設定] 對話方塊會提示您輸入安裝 Lync Server 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="ce648-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="ce648-133">請選擇預設位置或 **[瀏覽]** 至您想要的位置，然後按一下 **[安裝]**。</span><span class="sxs-lookup"><span data-stu-id="ce648-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="ce648-134">在 [授權合約] 頁面上，勾選 **[我接受授權合約中的條款]**，然後按 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ce648-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="ce648-135">安裝程式會安裝 Lync Server 2013 核心元件。</span><span class="sxs-lookup"><span data-stu-id="ce648-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="ce648-136">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ce648-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="ce648-137">執行：</span><span class="sxs-lookup"><span data-stu-id="ce648-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="ce648-138">如果您未指定 Ldf 參數，則預設值為從登錄讀取的 Lync Server 2013 安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="ce648-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="ce648-139">例如：</span><span class="sxs-lookup"><span data-stu-id="ce648-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="ce648-140">使用下列 Cmdlet 來驗證架構準備是否已完成。</span><span class="sxs-lookup"><span data-stu-id="ce648-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="ce648-141">如果架構準備成功，則此 Cmdlet 會傳回\*\*架構 \_ 版本 \_ 狀態 \_ \*\*的值。</span><span class="sxs-lookup"><span data-stu-id="ce648-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="ce648-142">等候 Active Directory 複寫完成或強制複寫。</span><span class="sxs-lookup"><span data-stu-id="ce648-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="ce648-143">手動驗證架構變更是否已複寫至其他所有的網域控制站。</span><span class="sxs-lookup"><span data-stu-id="ce648-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="ce648-144">如需詳細資訊，請參閱[在 Lync Server 2013 中驗證 Active Directory 架構](lync-server-2013-verifying-schema-replication.md)複寫。</span><span class="sxs-lookup"><span data-stu-id="ce648-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce648-145">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce648-145">See Also</span></span>


[<span data-ttu-id="ce648-146">在 Lync Server 2013 中驗證 Active Directory 架構複寫</span><span class="sxs-lookup"><span data-stu-id="ce648-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="ce648-147">在 Lync Server 2013 中準備 Active Directory 架構</span><span class="sxs-lookup"><span data-stu-id="ce648-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

