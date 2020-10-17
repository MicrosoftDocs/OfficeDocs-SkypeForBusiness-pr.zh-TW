---
title: Lync Server 2013： Lync Server 管理命令介面
description: Lync Server 2013： Lync Server 管理命令介面。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45727c42899defcf20ce36e2a27a9268a52ecd71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543179"
---
# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="d4d33-103">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="d4d33-103">Lync Server 2013 Management Shell</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4d33-104">_**主題上次修改日期：** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="d4d33-104">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d4d33-105">商務用 Skype Cmdlet 參考已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="d4d33-105">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="d4d33-106">按一下下列連結將會帶您前往 [新增 docs.microsoft.com] 頁面。</span><span class="sxs-lookup"><span data-stu-id="d4d33-106">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="d4d33-107">內容現在已開啟，且可透過 GitHub 進行社區貢獻。</span><span class="sxs-lookup"><span data-stu-id="d4d33-107">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="d4d33-108">對共同作業感興趣？</span><span class="sxs-lookup"><span data-stu-id="d4d33-108">Interested in contributing?</span></span> <span data-ttu-id="d4d33-109">請參閱下列位置的讀我檔案： <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="d4d33-109">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="d4d33-110">Microsoft Lync Server 2010 引進了一組龐大的新功能與改進功能，與 Microsoft Office 通訊伺服器 2007 R2 中提供的功能相較。</span><span class="sxs-lookup"><span data-stu-id="d4d33-110">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="d4d33-111">其中一項改良功能是管理實作的方式。</span><span class="sxs-lookup"><span data-stu-id="d4d33-111">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="d4d33-112">例如，有一個新的使用者介面（稱為 Lync Server 控制台），它代表與 Microsoft 管理主控台使用大部分人員的大量班次。</span><span class="sxs-lookup"><span data-stu-id="d4d33-112">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="d4d33-113">其他可管理性的重大改善是包含 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d4d33-113">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="d4d33-114">Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4d33-114">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="d4d33-115">它包括命令列環境、產品特定命令，以及完整指令碼語言。</span><span class="sxs-lookup"><span data-stu-id="d4d33-115">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="d4d33-116">Windows PowerShell 第一次是在2006中新增為 Windows 作業系統的可下載版本，已融入為 Microsoft Exchange Server 2007 的可管理性命令列介面。</span><span class="sxs-lookup"><span data-stu-id="d4d33-116">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="d4d33-117">從該點繼續成長，並已合併至大多數的 Microsoft Server 產品中，最新的是 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d4d33-117">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d4d33-118">Lync Server 2010 引進接近550產品特有的 Cmdlet，您可以用來管理部署的各個層面。</span><span class="sxs-lookup"><span data-stu-id="d4d33-118">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="d4d33-119">下列各節包含 Cmdlet 及其描述的清單。</span><span class="sxs-lookup"><span data-stu-id="d4d33-119">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="d4d33-120">此資訊也可以直接從命令列取得。</span><span class="sxs-lookup"><span data-stu-id="d4d33-120">This information is also available directly from the command line.</span></span> <span data-ttu-id="d4d33-121">只需在 Lync Server 管理命令介面命令提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d4d33-121">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="d4d33-122">例如，若要從命令提示字元擷取 **New-CsVoicePolicy** Cmdlet 的說明，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d4d33-122">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="d4d33-123">有關在 Lync Server 2013 中瞭解 Windows PowerShell 的事項：</span><span class="sxs-lookup"><span data-stu-id="d4d33-123">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="d4d33-124">若要執行 Lync Server Cmdlet，請開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d4d33-124">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d4d33-125">如果您開啟的是 Windows PowerShell 視窗，而不是 Lync Server 管理命令介面，依預設，您將無法執行 Lync Server Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d4d33-125">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="d4d33-126">若要從 Windows PowerShell 內執行 Lync Server Cmdlet，請先在 Windows PowerShell 命令提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d4d33-126">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="d4d33-127">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="d4d33-127">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="d4d33-128">Lync Server 管理命令介面會自動安裝在每一部 Lync Server Enterprise Edition 前端伺服器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="d4d33-128">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="d4d33-129">有關 Windows PowerShell 和 Microsoft Lync Server 2013 Cmdlet 的新增及更新資訊、範例腳本及協助，可在 Lync Server Windows PowerShell 博客中取得 [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) 。</span><span class="sxs-lookup"><span data-stu-id="d4d33-129">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

