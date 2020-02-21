---
title: 'Lync Server 2013: Lync Server 管理命令介面'
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
ms.openlocfilehash: dfc4ab6a9c32a8b060308526fcdb1f1da403a9e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="dfeba-102">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="dfeba-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfeba-103">_**主題上次修改日期：** 2017年-09-20 個_</span><span class="sxs-lookup"><span data-stu-id="dfeba-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dfeba-104">Skype for Business cmdlet 參照已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="dfeba-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="dfeba-105">按一下下列連結將帶您前往 [新增 docs.microsoft.com] 頁面。</span><span class="sxs-lookup"><span data-stu-id="dfeba-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="dfeba-106">內容現在是透過 GitHub 開啟來源，並可供社群參與。</span><span class="sxs-lookup"><span data-stu-id="dfeba-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="dfeba-107">參與有興趣嗎？</span><span class="sxs-lookup"><span data-stu-id="dfeba-107">Interested in contributing?</span></span> <span data-ttu-id="dfeba-108">請參閱 「 讀我檔案中的儲存機制：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="dfeba-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="dfeba-109">Microsoft Lync Server 2010 引進了一大組的相較於什麼是 Microsoft Office Communications Server 2007 R2 中可用的新增和改善功能。</span><span class="sxs-lookup"><span data-stu-id="dfeba-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="dfeba-110">其中一項改良功能是管理實作的方式。</span><span class="sxs-lookup"><span data-stu-id="dfeba-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="dfeba-111">例如，沒有新的使用者介面，稱為 「 Lync Server Control Panel，查看大部分的人員使用 Microsoft Management Console，是用來代表 big shift 鍵。</span><span class="sxs-lookup"><span data-stu-id="dfeba-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="dfeba-112">其他主要的改善管理性是 Windows PowerShell 的相對路徑。</span><span class="sxs-lookup"><span data-stu-id="dfeba-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="dfeba-113">Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="dfeba-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="dfeba-114">它包括命令列環境、產品特定命令，以及完整指令碼語言。</span><span class="sxs-lookup"><span data-stu-id="dfeba-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="dfeba-115">Windows PowerShell 第一次中已導入與 Windows 作業系統可下載發行最遲 2006，並已合併為命令列介面的 Microsoft Exchange Server 2007 的管理性。</span><span class="sxs-lookup"><span data-stu-id="dfeba-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="dfeba-116">從該點它可以繼續成長，以及它具有已納入大部分的 Microsoft 伺服器產品，最新版的這些正在 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="dfeba-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="dfeba-117">Lync Server 2010 引進了接近 550 特定產品 cmdlet 可以用來管理您的部署的每個層面。</span><span class="sxs-lookup"><span data-stu-id="dfeba-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="dfeba-118">下列各節包含 Cmdlet 及其描述的清單。</span><span class="sxs-lookup"><span data-stu-id="dfeba-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="dfeba-119">此資訊也可以直接從命令列取得。</span><span class="sxs-lookup"><span data-stu-id="dfeba-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="dfeba-120">只在 Lync Server 管理命令介面命令提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="dfeba-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="dfeba-121">例如，若要從命令提示字元擷取 **New-CsVoicePolicy** Cmdlet 的說明，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="dfeba-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="dfeba-122">若要了解 Windows PowerShell 在 Lync Server 2013 中的項目：</span><span class="sxs-lookup"><span data-stu-id="dfeba-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="dfeba-123">若要執行 Lync Server 指令程式，開啟 [Lync Server 管理命令介面]。</span><span class="sxs-lookup"><span data-stu-id="dfeba-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="dfeba-124">如果您開啟 Windows PowerShell 視窗，而不是在 Lync Server 管理命令介面]，依預設您將無法執行 Lync Server cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dfeba-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="dfeba-125">若要執行從 Windows PowerShell 中的 Lync Server 指令程式，請先在 Windows PowerShell 命令提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="dfeba-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="dfeba-126">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="dfeba-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="dfeba-127">Lync Server 管理命令介面會自動安裝每個 Lync Server Enterprise Edition 前端伺服器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="dfeba-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="dfeba-128">最新及更新的資訊、 範例指令碼，以及開始使用並深入了解 Windows PowerShell 和 Microsoft Lync Server 2013 cmdlet 的說明位於 Lync Server Windows PowerShell 部落格[https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)。</span><span class="sxs-lookup"><span data-stu-id="dfeba-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

