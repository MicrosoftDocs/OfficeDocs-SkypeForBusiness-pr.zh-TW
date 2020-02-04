---
title: Lync Server 2013：安裝規劃工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Planning Tool
ms:assetid: ebdc9e26-4b22-4b02-85b9-7462bcfe7c93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615046(v=OCS.15)
ms:contentKeyID: 51541525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7a427ab99368d74180e1d0321741117a9ed97e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="6fada-102">在 Lync Server 2013 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="6fada-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6fada-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="6fada-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="6fada-104">在您開始設計及規劃 Lync Server 2013 基礎結構之前，請先使用 Microsoft Lync Server 2013 （規劃工具）安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="6fada-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="6fada-105">規劃工具不需要部署到您打算安裝 Lync Server 2013 之網域或基礎結構中的工作站或伺服器。</span><span class="sxs-lookup"><span data-stu-id="6fada-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="6fada-106">規劃工具隨附的 Readme 檔案會詳細說明有關安裝及使用工具的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="6fada-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="6fada-107">讀我檔案中的部分資訊會在此重複，以清楚起見。</span><span class="sxs-lookup"><span data-stu-id="6fada-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6fada-108">規劃工具必須由使用者在安裝該工具的電腦上擁有系統管理員權利和許可權，才能安裝。</span><span class="sxs-lookup"><span data-stu-id="6fada-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="6fada-109">規劃工具所支援的安裝及作業作業系統包括：</span><span class="sxs-lookup"><span data-stu-id="6fada-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="6fada-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="6fada-110">Windows 8</span></span>

  - <span data-ttu-id="6fada-111">Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="6fada-111">Windows 8.1</span></span>

  - <span data-ttu-id="6fada-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6fada-112">Windows Server 2012</span></span>

  - <span data-ttu-id="6fada-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6fada-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="6fada-114">Windows 7、32位版本</span><span class="sxs-lookup"><span data-stu-id="6fada-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="6fada-115">Windows 7，64在 Win32 上使用 Windows （WOW）</span><span class="sxs-lookup"><span data-stu-id="6fada-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="6fada-116">Windows Server 2008 R2，使用 WOW</span><span class="sxs-lookup"><span data-stu-id="6fada-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="6fada-117">此外，規劃工具需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="6fada-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="6fada-118">在符合預先安裝需求之後，您就可以安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="6fada-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="6fada-119">若要安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="6fada-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="6fada-120">以管理員群組的成員身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="6fada-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="6fada-121">使用 Windows 資源管理器或命令視窗，找出您下載規劃工具安裝檔的目錄。</span><span class="sxs-lookup"><span data-stu-id="6fada-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="6fada-122">找出 LyncPlanningTool。</span><span class="sxs-lookup"><span data-stu-id="6fada-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="6fada-123">在 Windows 資源管理器中，按兩下檔案。</span><span class="sxs-lookup"><span data-stu-id="6fada-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="6fada-124">在命令視窗中，輸入檔案名，然後按**enter**執行檔案。</span><span class="sxs-lookup"><span data-stu-id="6fada-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="6fada-125">在 Microsoft Lync Server 2013 的 [歡迎] 頁面上，選擇 [**規劃工具設定向導]**，然後按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="6fada-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="6fada-126">查看 [**使用者授權合約**]，如果您選擇接受授權協定中的使用條款，請選取 [**我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="6fada-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="6fada-127">選擇安裝規劃工具檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="6fada-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="6fada-128">預設位置為 C：\\Program Files （x86）\\Microsoft Lync Server 2013\\規劃工具。</span><span class="sxs-lookup"><span data-stu-id="6fada-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="6fada-129">如果您想要變更安裝位置，請按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="6fada-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="6fada-130">在 [**變更目的地] 資料夾**中，流覽或輸入安裝盤案的位置，按一下 **[確定]**，然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="6fada-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="6fada-131">安裝程式現已準備好安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="6fada-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="6fada-132">按一下 [**安裝**] 以開始安裝程式。</span><span class="sxs-lookup"><span data-stu-id="6fada-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="6fada-133">隨即會啟動安裝，並顯示進度。</span><span class="sxs-lookup"><span data-stu-id="6fada-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="6fada-134">成功完成安裝後，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="6fada-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="6fada-135">規劃工具已就緒，可供使用。</span><span class="sxs-lookup"><span data-stu-id="6fada-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6fada-136">請參閱</span><span class="sxs-lookup"><span data-stu-id="6fada-136">See Also</span></span>


[<span data-ttu-id="6fada-137">在 Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="6fada-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

