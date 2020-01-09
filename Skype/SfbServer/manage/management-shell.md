---
title: 商務用 Skype Server 管理命令介面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 商務用 Skype Server 管理命令介面提供伺服器管理和管理的命令列介面。 它是在 Windows PowerShell 中建立的，包含一組專用於 Skype 與舊版 Lync server 產品的完整管理和管理 Cmdlet。
ms.openlocfilehash: 4890194824caaea771d31e008d4546d871d0da8a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991588"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="27840-104">商務用 Skype Server 管理命令介面</span><span class="sxs-lookup"><span data-stu-id="27840-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="27840-105">商務用 Skype Server 管理命令介面提供伺服器管理和管理的命令列介面。</span><span class="sxs-lookup"><span data-stu-id="27840-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="27840-106">它是在 Windows PowerShell 中建立的，包含一組專用於 Skype 與舊版 Lync server 產品的完整管理和管理 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27840-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="27840-107">Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。</span><span class="sxs-lookup"><span data-stu-id="27840-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="27840-108">它包含命令列環境、產品特定命令及完整的腳本撰寫語言。</span><span class="sxs-lookup"><span data-stu-id="27840-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="27840-109">Windows PowerShell 最初是在2006中提供給 Windows 作業系統的可下載版本，並已融入為 Microsoft Exchange Server 2007 可管理性的命令列介面。</span><span class="sxs-lookup"><span data-stu-id="27840-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="27840-110">它已融入大部分的 Microsoft 伺服器產品中，包括從 Lync Server 2010 開始的 Lync 和 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="27840-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="27840-111">商務用 Skype Server Management Shell 中有超過700的 Lync 和 Skype 特定 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27840-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27840-112">商務用 Skype Cmdlet 參考已移至 docs.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="27840-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="27840-113">按一下下方的連結，會將您帶到 [新增 docs.microsoft.com] 頁面。</span><span class="sxs-lookup"><span data-stu-id="27840-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="27840-114">內容現在已開啟來源，且可供 GitHub 的群組發佈。</span><span class="sxs-lookup"><span data-stu-id="27840-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="27840-115">想要進行共同作業嗎？</span><span class="sxs-lookup"><span data-stu-id="27840-115">Interested in contributing?</span></span> <span data-ttu-id="27840-116">查看存放庫中的讀我檔案：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="27840-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="27840-117">商務用 skype 伺服器隨附700個以上的 Cmdlet，讓系統管理員可以使用商務用 Skype Server Management Shell 來管理商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="27840-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="27840-118">您可以直接從命令列取得 Cmdlet 的說明，方法是輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="27840-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="27840-119">上述命令會檢索**CsVoicePolicy** Cmdlet 提供的完整說明。</span><span class="sxs-lookup"><span data-stu-id="27840-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="27840-120">若要查看其他 Cmdlet 的說明，請以**新的 CsVoicePolicy**取代您要取得其說明的 Cmdlet 名稱。</span><span class="sxs-lookup"><span data-stu-id="27840-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="27840-121">若要取得可用於管理商務用 Skype Server 的完整 Cmdlet 清單，請在 shell 命令提示字元輸入以下內容：</span><span class="sxs-lookup"><span data-stu-id="27840-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="27840-122">商務用 Skype Server 中的 Windows PowerShell 須知：</span><span class="sxs-lookup"><span data-stu-id="27840-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="27840-123">若要執行商務用 Skype Server Cmdlet，請開啟商務用 Skype Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="27840-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="27840-124">如果您開啟的是 Windows PowerShell 視窗，而不是商務用 Skype Server Management Shell，則預設可能無法執行 Skype Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="27840-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="27840-125">若要在 Windows PowerShell 中執行商務用 Skype Server Cmdlet，請先在 Windows PowerShell 命令提示字元輸入以下命令： >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="27840-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="27840-126">商務用 skype Server Management 命令介面會自動安裝在每個商務用 Skype Server Enterprise Edition 前端伺服器或標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="27840-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="27840-127">您可以執行[update-help](https://technet.microsoft.com/en-us/library/hh849720.aspx) Cmdlet 來更新商務用 Skype Server Management Shell 說明內容。</span><span class="sxs-lookup"><span data-stu-id="27840-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="27840-128">Update-Help Cmdlet 會下載並安裝您電腦上安裝的所有模組可用的最新說明檔案，包括商務用 Skype Cmdlet 的更新。</span><span class="sxs-lookup"><span data-stu-id="27840-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="27840-129">根據預設， **update-Help** Cmdlet 會更新所有安裝在商務用 Skype Server 上的模組。</span><span class="sxs-lookup"><span data-stu-id="27840-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="27840-130">如果只要更新特定模組，可以使用 _Module_ 參數來限制 Cmdlet 的範圍。</span><span class="sxs-lookup"><span data-stu-id="27840-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="27840-131">下列範例只會更新商務用 Skype 模組。</span><span class="sxs-lookup"><span data-stu-id="27840-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="27840-132">如果您需要更新未連線至網際網路之伺服器上的說明，您可以使用[Save-help](https://technet.microsoft.com/en-us/library/hh849724.aspx) Cmdlet 來取得最新版本的說明，並將它儲存到您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="27840-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="27840-133">接著，您可以在未連線至網際網路的伺服器上，將**Update help** Cmdlet 與 _-SourcePath_參數搭配使用，從您選取的位置取得更新的說明。</span><span class="sxs-lookup"><span data-stu-id="27840-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="27840-134">下列範例顯示如何將說明檔案儲存至網路檔案共用，然後從檔案共用更新商務用 Skype 模組的說明。</span><span class="sxs-lookup"><span data-stu-id="27840-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="27840-135">如需更多詳細資訊，請參閱[關於可更新的協助](https://technet.microsoft.com/library/hh847735.aspx)。</span><span class="sxs-lookup"><span data-stu-id="27840-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="27840-136">如果您是在遠端使用 PowerShell，您可能需要允許透過防火牆進行通訊。</span><span class="sxs-lookup"><span data-stu-id="27840-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="27840-137">若要深入瞭解 PowerShell remoting 使用的埠，請參閱[Powershell Remoting 使用哪個埠？](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。</span><span class="sxs-lookup"><span data-stu-id="27840-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

