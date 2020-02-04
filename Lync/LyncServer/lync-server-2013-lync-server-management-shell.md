---
title: Lync Server 2013： Lync Server Management 命令介面
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
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="7b623-102">Lync Server 2013 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="7b623-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b623-103">_**主題上次修改日期：** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="7b623-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7b623-104">商務用 Skype Cmdlet 參考已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="7b623-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="7b623-105">按一下下方的連結，會將您帶到 [新增 docs.microsoft.com] 頁面。</span><span class="sxs-lookup"><span data-stu-id="7b623-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="7b623-106">內容現在已開啟來源，且可供 GitHub 的群組發佈。</span><span class="sxs-lookup"><span data-stu-id="7b623-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="7b623-107">想要進行共同作業嗎？</span><span class="sxs-lookup"><span data-stu-id="7b623-107">Interested in contributing?</span></span> <span data-ttu-id="7b623-108">查看存放庫中的讀我檔案：<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="7b623-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="7b623-109">Microsoft Lync Server 2010 引進了一組較大的新功能和改良功能，與 Microsoft Office 通訊伺服器 2007 R2 中提供的功能比較。</span><span class="sxs-lookup"><span data-stu-id="7b623-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="7b623-110">其中一個改善是您管理實施的方式。</span><span class="sxs-lookup"><span data-stu-id="7b623-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="7b623-111">例如，有一個新的使用者介面（稱為 Lync Server [控制台]），代表在 Microsoft 管理主控台中使用大部分人員的大量班次。</span><span class="sxs-lookup"><span data-stu-id="7b623-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="7b623-112">易管理性的另一個主要改進，就是加入了 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7b623-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="7b623-113">Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7b623-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="7b623-114">它包含命令列環境、產品特定命令及完整的腳本撰寫語言。</span><span class="sxs-lookup"><span data-stu-id="7b623-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="7b623-115">Windows PowerShell 最初是在2006中提供給 Windows 作業系統的可下載版本，並已融入為 Microsoft Exchange Server 2007 可管理性的命令列介面。</span><span class="sxs-lookup"><span data-stu-id="7b623-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="7b623-116">從那一開始，我們已將它整合到大部分的 Microsoft 伺服器產品中，最新的是 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="7b623-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="7b623-117">Lync Server 2010 引進了550個產品專用的 Cmdlet，您可以用來管理您的部署的各個方面。</span><span class="sxs-lookup"><span data-stu-id="7b623-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="7b623-118">下列各節包含 Cmdlet 及其描述的清單。</span><span class="sxs-lookup"><span data-stu-id="7b623-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="7b623-119">此資訊也可以直接從命令列取得。</span><span class="sxs-lookup"><span data-stu-id="7b623-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="7b623-120">只要在 Lync Server 管理命令介面命令提示字元輸入以下內容：</span><span class="sxs-lookup"><span data-stu-id="7b623-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="7b623-121">例如，若要從命令提示字元擷取 **New-CsVoicePolicy** Cmdlet 的說明，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7b623-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="7b623-122">有關 Lync Server 2013 中的 Windows PowerShell 須知：</span><span class="sxs-lookup"><span data-stu-id="7b623-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="7b623-123">若要執行 Lync Server Cmdlet，請開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="7b623-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7b623-124">如果您開啟的是 Windows PowerShell 視窗，而不是 Lync Server 管理命令介面，預設將無法執行 Lync Server Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7b623-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="7b623-125">若要從 Windows PowerShell 中執行 Lync Server Cmdlet，請先在 Windows PowerShell 命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="7b623-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="7b623-126">匯入模組 Lync</span><span class="sxs-lookup"><span data-stu-id="7b623-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="7b623-127">Lync Server 管理命令介面會自動安裝在每個 Lync Server 企業版前端伺服器或標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="7b623-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="7b623-128">新功能和更新的資訊、範例腳本，以及有關 Windows PowerShell 和 Microsoft Lync Server 2013 Cmdlet 的說明，可在 Lync Server Windows PowerShell 博客[https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)中取得。</span><span class="sxs-lookup"><span data-stu-id="7b623-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

