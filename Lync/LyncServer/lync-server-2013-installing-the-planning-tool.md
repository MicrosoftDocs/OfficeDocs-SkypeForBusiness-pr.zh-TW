---
title: Lync Server 2013： 安裝規劃工具
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
ms.openlocfilehash: 792f72daac7eb1d7edb10087256bfda0912edfe9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-planning-tool-in-lync-server-2013"></a><span data-ttu-id="4981a-102">Lync Server 2013 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="4981a-102">Installing the Planning Tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4981a-103">_**上次修改主題：** 2013年-11-07_</span><span class="sxs-lookup"><span data-stu-id="4981a-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="4981a-104">之前開始設計和規劃 Lync Server 2013 基礎結構使用 Microsoft Lync Server 2013 規劃工具，您必須先安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="4981a-104">Before you begin designing and planning your Lync Server 2013 infrastructure by using the Microsoft Lync Server 2013, Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="4981a-105">規劃工具不需要部署至工作站或伺服器的網域或基礎結構一部分您預計要安裝 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4981a-105">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Lync Server 2013.</span></span> <span data-ttu-id="4981a-106">規劃工具時所附帶的讀我檔案詳細說明安裝及使用此工具的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="4981a-106">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="4981a-107">系統會以方便識別以下重複部分讀我檔案中的資訊。</span><span class="sxs-lookup"><span data-stu-id="4981a-107">Some of the information in the Readme file is duplicated here for clarity.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4981a-108">規劃工具需要由系統管理員權限和安裝此工具的電腦上的權限的使用者安裝。</span><span class="sxs-lookup"><span data-stu-id="4981a-108">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>



</div>

<span data-ttu-id="4981a-109">支援的作業系統安裝和規劃工具的作業包括：</span><span class="sxs-lookup"><span data-stu-id="4981a-109">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

  - <span data-ttu-id="4981a-110">Windows 8</span><span class="sxs-lookup"><span data-stu-id="4981a-110">Windows 8</span></span>

  - <span data-ttu-id="4981a-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="4981a-111">Windows 8.1</span></span>

  - <span data-ttu-id="4981a-112">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4981a-112">Windows Server 2012</span></span>

  - <span data-ttu-id="4981a-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4981a-113">Windows Server 2012 R2</span></span>

  - <span data-ttu-id="4981a-114">Windows 7，32 位元版本</span><span class="sxs-lookup"><span data-stu-id="4981a-114">Windows 7, 32-bit edition</span></span>

  - <span data-ttu-id="4981a-115">Windows 7 64 位元版本，使用 Windows on Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="4981a-115">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

  - <span data-ttu-id="4981a-116">Windows Server 2008 R2，使用 WOW</span><span class="sxs-lookup"><span data-stu-id="4981a-116">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="4981a-117">此外，規劃工具需要 Microsoft.NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="4981a-117">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="4981a-118">符合安裝前需求之後，您可以再安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="4981a-118">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>

<div>

## <a name="to-install-the-planning-tool"></a><span data-ttu-id="4981a-119">若要安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="4981a-119">To install the Planning Tool</span></span>

1.  <span data-ttu-id="4981a-120">系統管理員群組的成員身分登入本機電腦。</span><span class="sxs-lookup"><span data-stu-id="4981a-120">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="4981a-121">使用 Windows 檔案總管] 或 [命令視窗，找出您下載的規劃工具安裝檔案所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="4981a-121">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3.  <span data-ttu-id="4981a-122">找出 LyncPlanningTool.msi。</span><span class="sxs-lookup"><span data-stu-id="4981a-122">Locate the LyncPlanningTool.msi.</span></span> <span data-ttu-id="4981a-123">在 [Windows 檔案總管]，連按兩下檔案。</span><span class="sxs-lookup"><span data-stu-id="4981a-123">In Windows Explorer, double-click the file.</span></span> <span data-ttu-id="4981a-124">在命令視窗中，輸入檔案名稱，然後按**Enter**來執行檔案。</span><span class="sxs-lookup"><span data-stu-id="4981a-124">In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4.  <span data-ttu-id="4981a-125">在 [ **Microsoft Lync Server 2013、 規劃工具安裝嚮導**的 [歡迎] 頁面中，按一下 [**下一步**]。</span><span class="sxs-lookup"><span data-stu-id="4981a-125">On the Welcome page of the **Microsoft Lync Server 2013, Planning Tool Setup Wizard**, click **Next**.</span></span>

5.  <span data-ttu-id="4981a-126">檢閱**授權合約**，然後選取 [**我接受授權合約中的條款]** 如果您選擇以接受授權合約]，使用中的條款，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4981a-126">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6.  <span data-ttu-id="4981a-127">選擇要安裝規劃工具檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="4981a-127">Choose where to install the Planning Tool files.</span></span> <span data-ttu-id="4981a-128">預設位置為 c:\\Program Files (x86)\\Microsoft Lync Server 2013\\規劃工具。</span><span class="sxs-lookup"><span data-stu-id="4981a-128">The default location is C:\\Program Files (x86)\\Microsoft Lync Server 2013\\Planning Tool.</span></span> <span data-ttu-id="4981a-129">如果您想要變更的安裝位置，按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="4981a-129">If you want to change the installation location, click **Change**.</span></span> <span data-ttu-id="4981a-130">在**變更目的地資料夾**中，瀏覽或輸入要安裝的檔案，按一下 [**確定**]，然後按一下 [**下一步**的位置。</span><span class="sxs-lookup"><span data-stu-id="4981a-130">On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7.  <span data-ttu-id="4981a-131">安裝程式已準備好安裝規劃工具。</span><span class="sxs-lookup"><span data-stu-id="4981a-131">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="4981a-132">按一下 [**安裝**] 以開始安裝程序。</span><span class="sxs-lookup"><span data-stu-id="4981a-132">Click **Install** to begin the installation process.</span></span>

8.  <span data-ttu-id="4981a-133">開始安裝，並會顯示進度。</span><span class="sxs-lookup"><span data-stu-id="4981a-133">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="4981a-134">成功完成安裝之後，按一下 [**完成**]。</span><span class="sxs-lookup"><span data-stu-id="4981a-134">After the installation is successfully completed, click **Finish**.</span></span>

9.  <span data-ttu-id="4981a-135">規劃工具可供使用。</span><span class="sxs-lookup"><span data-stu-id="4981a-135">The Planning Tool is ready for use.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4981a-136">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4981a-136">See Also</span></span>


[<span data-ttu-id="4981a-137">Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="4981a-137">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

