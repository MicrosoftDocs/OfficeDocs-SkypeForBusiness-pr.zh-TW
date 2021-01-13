---
title: 商務用 Skype Server 管理命令介面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 商務用 Skype Server 管理命令介面提供伺服器管理和管理的命令列介面。 它是以 Windows PowerShell 為基礎，包含一組完整的 Skype 和舊版 Lync server 產品特有的管理和管理 Cmdlet。
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816533"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="bc3de-104">商務用 Skype Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="bc3de-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="bc3de-105">商務用 Skype Server 管理命令介面提供伺服器管理和管理的命令列介面。</span><span class="sxs-lookup"><span data-stu-id="bc3de-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="bc3de-106">它是以 Windows PowerShell 為基礎，包含一組完整的 Skype 和舊版 Lync server 產品特有的管理和管理 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bc3de-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="bc3de-107">Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="bc3de-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="bc3de-108">它包括命令列環境、產品特定命令，以及完整指令碼語言。</span><span class="sxs-lookup"><span data-stu-id="bc3de-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="bc3de-109">Windows PowerShell 第一次是在2006中新增為 Windows 作業系統的可下載版本，已融入為 Microsoft Exchange Server 2007 的可管理性命令列介面。</span><span class="sxs-lookup"><span data-stu-id="bc3de-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="bc3de-110">它已整合至大多數的 Microsoft Server 產品，包括從 Lync Server 2010 開始的 Lync 和 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="bc3de-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="bc3de-111">商務用 Skype Server 管理命令介面中提供超過700的 Lync 和 Skype 特有 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bc3de-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bc3de-112">商務用 Skype Cmdlet 參考已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="bc3de-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="bc3de-113">按一下下列連結將會帶您前往 [新增 docs.microsoft.com] 頁面。</span><span class="sxs-lookup"><span data-stu-id="bc3de-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="bc3de-114">內容現在已開啟，且可透過 GitHub 進行社區貢獻。</span><span class="sxs-lookup"><span data-stu-id="bc3de-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="bc3de-115">對共同作業感興趣？</span><span class="sxs-lookup"><span data-stu-id="bc3de-115">Interested in contributing?</span></span> <span data-ttu-id="bc3de-116">請參閱下列位置的讀我檔案： [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="bc3de-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="bc3de-117">商務用 skype 伺服器隨附超過700個 Cmdlet，可讓系統管理員使用商務用 Skype Server 管理命令介面來管理商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="bc3de-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="bc3de-118">您可以輸入類似如下的命令，直接從命令列取得 Cmdlet 的說明：</span><span class="sxs-lookup"><span data-stu-id="bc3de-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="bc3de-119">上述命令會檢索可用於 **New-CsVoicePolicy** Cmdlet 的完整説明。</span><span class="sxs-lookup"><span data-stu-id="bc3de-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="bc3de-120">若要查看其他 Cmdlet 的說明，請以您想要取得 help 之 Cmdlet 的名稱取代 **New-CsVoicePolicy** 。</span><span class="sxs-lookup"><span data-stu-id="bc3de-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="bc3de-121">若要取得可用於管理商務用 Skype 伺服器的完整 Cmdlet 清單，請在命令介面命令提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="bc3de-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="bc3de-122">在商務用 Skype Server 中瞭解 Windows PowerShell 的相關事項：</span><span class="sxs-lookup"><span data-stu-id="bc3de-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="bc3de-123">若要執行商務用 Skype Server Cmdlet，請開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="bc3de-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="bc3de-124">如果您開啟 Windows PowerShell 視窗，而不是商務用 Skype Server 管理命令介面，預設可能無法執行 Skype Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bc3de-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="bc3de-125">若要在 Windows PowerShell 中執行商務用 Skype Server Cmdlet，請先在 Windows PowerShell 命令提示字元處輸入下列命令： >  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="bc3de-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="bc3de-126">商務用 skype Server 管理命令介面會自動安裝在每家商務用 Skype Server Enterprise Edition 前端伺服器或 Standard Edition server 上。</span><span class="sxs-lookup"><span data-stu-id="bc3de-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="bc3de-127">您可以執行 [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) Cmdlet 來更新商務用 Skype Server 管理命令介面說明內容。</span><span class="sxs-lookup"><span data-stu-id="bc3de-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="bc3de-128">Update-Help Cmdlet 會下載並安裝適用于電腦上所有模組的最新説明檔案，包括商務用 Skype Cmdlet 的更新。</span><span class="sxs-lookup"><span data-stu-id="bc3de-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="bc3de-129">根據預設， **Update-Help** Cmdlet 會更新所有安裝在商務用 Skype Server 上的模組。</span><span class="sxs-lookup"><span data-stu-id="bc3de-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="bc3de-130">如果您只想更新特定的模組，您可以使用 _Module_ 參數來限制 Cmdlet 的範圍。</span><span class="sxs-lookup"><span data-stu-id="bc3de-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="bc3de-131">下列範例只會更新商務用 Skype 模組。</span><span class="sxs-lookup"><span data-stu-id="bc3de-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="bc3de-132">如果您需要更新未連接至網際網路之伺服器上的說明，您可以使用 [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) Cmdlet 來取得最新版本的說明，並將其儲存至您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="bc3de-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="bc3de-133">然後，您可以在未連線至網際網路的伺服器上使用 _-SourcePath_ 參數的 **Update-Help** Cmdlet，以從選取的位置取得更新的說明。</span><span class="sxs-lookup"><span data-stu-id="bc3de-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="bc3de-134">下列範例顯示如何將說明檔案儲存至網路檔案共用，然後從檔案共用更新商務用 Skype 模組的說明。</span><span class="sxs-lookup"><span data-stu-id="bc3de-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="bc3de-135">如需詳細資訊，請參閱 [關於可更新的協助](https://technet.microsoft.com/library/hh847735.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bc3de-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bc3de-136">如果您遠端使用 PowerShell，您可能需要透過防火牆允許通訊。</span><span class="sxs-lookup"><span data-stu-id="bc3de-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="bc3de-137">若要深入瞭解 PowerShell 遠端使用的埠，請參閱 [Remoting 使用哪個埠 PowerShell？](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。</span><span class="sxs-lookup"><span data-stu-id="bc3de-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

