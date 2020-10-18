---
title: Lync Server 2013：安裝規劃工具
description: Lync Server 2013：安裝規劃工具。
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
ms.openlocfilehash: 11836e2c86cb01d6f911670a9eeafef0c31c0af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575059"
---
# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="af105-103">在 Lync Server 2013 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="af105-103">Installing the Planning Tool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af105-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="af105-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="af105-105">在您開始設計及規劃 Lync Server 2013 基礎結構之前，使用 Microsoft Lync Server 2013 （規劃工具）之前，您必須先安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="af105-105">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="af105-106">規劃工具不需要部署到屬於您計畫安裝 Lync Server 2013 之網域或基礎結構一部分的工作站或伺服器上。</span><span class="sxs-lookup"><span data-stu-id="af105-106">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="af105-107">規劃工具附帶的讀我檔案詳細說明安裝及使用此工具的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="af105-107">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="af105-108">為了清楚起見，自述檔中的部分資訊是重複的。</span><span class="sxs-lookup"><span data-stu-id="af105-108">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="af105-109">規劃工具需要安裝要安裝該工具之電腦的系統管理員權利和許可權的使用者。</span><span class="sxs-lookup"><span data-stu-id="af105-109">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="af105-110">規劃工具的安裝及作業支援的作業系統包括：</span><span class="sxs-lookup"><span data-stu-id="af105-110">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="af105-111">Windows 8</span><span class="sxs-lookup"><span data-stu-id="af105-111">Windows 8</span></span>

  - <span data-ttu-id="af105-112">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="af105-112">Windows 8.1</span></span>

  - <span data-ttu-id="af105-113">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="af105-113">Windows Server 2012</span></span>

  - <span data-ttu-id="af105-114">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="af105-114">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="af105-115">Windows 7、32位版本</span><span class="sxs-lookup"><span data-stu-id="af105-115">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="af105-116">使用 Windows on Win32 的 windows 7、64位版本 (WOW) </span><span class="sxs-lookup"><span data-stu-id="af105-116">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="af105-117">Windows Server 2008 R2，使用 WOW</span><span class="sxs-lookup"><span data-stu-id="af105-117">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="af105-118">此外，規劃工具需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="af105-118">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="af105-119">符合預先安裝需求之後，即可安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="af105-119">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="af105-120">安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="af105-120">To install the Planning Tool</span></span>

1.  <span data-ttu-id="af105-121">以 Administrators 群組成員的身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="af105-121">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="af105-122">使用 Windows Explorer 或命令視窗，找到您下載規劃工具安裝檔的目錄。</span><span class="sxs-lookup"><span data-stu-id="af105-122">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="af105-123">找出 LyncPlanningTool.msi。</span><span class="sxs-lookup"><span data-stu-id="af105-123">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="af105-124">在 [Windows Explorer] 中，按兩下檔案。</span><span class="sxs-lookup"><span data-stu-id="af105-124">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="af105-125">在命令視窗中，輸入檔案名，然後按 **enter** 執行該檔案。</span><span class="sxs-lookup"><span data-stu-id="af105-125">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="af105-126">在 [ **Microsoft Lync Server 2013，規劃工具安裝精靈]** 的 [歡迎] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="af105-126">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="af105-127">檢查 **End-User 授權合約**，如果您選擇接受授權合約中的使用條款，請選取 [ **我接受授權合約中的條款** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="af105-127">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="af105-128">選擇安裝規劃工具檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="af105-128">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="af105-129">預設位置是 C： \\ Program Files (x86) \\ Microsoft Lync Server 2013 \\ 規劃工具。</span><span class="sxs-lookup"><span data-stu-id="af105-129">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="af105-130">若要變更安裝位置，請按一下 [ **變更**]。</span><span class="sxs-lookup"><span data-stu-id="af105-130">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="af105-131">在 [ **變更目的地資料夾**] 中，流覽或輸入要安裝盤案的位置，按一下 **[確定]**，然後按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="af105-131">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="af105-132">安裝程式現在已準備好安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="af105-132">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="af105-133">按一下 [ **安裝** ] 以開始安裝程式。</span><span class="sxs-lookup"><span data-stu-id="af105-133">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="af105-134">安裝會開始，並會顯示進度。</span><span class="sxs-lookup"><span data-stu-id="af105-134">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="af105-135">安裝順利完成後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="af105-135">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="af105-136">規劃工具可供使用。</span><span class="sxs-lookup"><span data-stu-id="af105-136">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="af105-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="af105-137">See Also</span></span>


[<span data-ttu-id="af105-138">在 Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="af105-138">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

