---
title: 合併 Skype 商務 Online cmdlet 與在其他 Windows PowerShell cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7455ba7d98ecc11fcfc6e0c255eb430e213d3f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="58b65-102">合併 Skype 商務 Online cmdlet 與在其他 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="58b65-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58b65-103">_**上次修改主題：** 2013年-07-05_</span><span class="sxs-lookup"><span data-stu-id="58b65-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="58b65-104">當您連接至 Skype for Business Online 使用 Windows PowerShell 時，約 40 Skype for Business Online cmdlet 將可供您使用。</span><span class="sxs-lookup"><span data-stu-id="58b65-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="58b65-105">不過，您不一定要管理商務用 Skype 時使用只有 40 指令程式。</span><span class="sxs-lookup"><span data-stu-id="58b65-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="58b65-106">除了 Skype for Business Online 指令程式，您也可以使用任何其他電腦安裝的 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="58b65-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="58b65-107">（當您安裝 Windows PowerShell 3.0 時，數百個核心 Windows PowerShell 指令程式會安裝，以及）。命令可以混合和相符 Skype for Business Online cmdlet 與任何其他指令程式可以在您電腦上。</span><span class="sxs-lookup"><span data-stu-id="58b65-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="58b65-108">雖然這是在 Windows PowerShell 3.0 的完整課程超出本文章的涵蓋範圍，以下是一些範例，說明您可能想可以混合及比對指令程式。</span><span class="sxs-lookup"><span data-stu-id="58b65-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="58b65-109">首先，無 Skype for Business Online 指令程式包含列印] 命令，並沒有這類命令中，可以找到 [Windows PowerShell 主控台，或是。</span><span class="sxs-lookup"><span data-stu-id="58b65-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="58b65-110">您要那要如何取得列印文件的指令程式所擷取的資訊？</span><span class="sxs-lookup"><span data-stu-id="58b65-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="58b65-111">一種方式是擷取的詳細資訊，並再將該資訊傳送至**Out-printer**指令程式：</span><span class="sxs-lookup"><span data-stu-id="58b65-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="58b65-112">因為沒有其他參數都包含在內，將會以預設的印表機列印**Out-printer** cmdlet 所傳回的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="58b65-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="58b65-113">同樣地，無 Skype for Business Online 指令程式包含參數，可讓您將資料儲存至檔案。</span><span class="sxs-lookup"><span data-stu-id="58b65-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="58b65-114">但這是 [確定]: 這個命令會使用**Out-file** cmdlet 以將傳回的資訊儲存到文字檔 c:\\記錄\\Tenants.txt:</span><span class="sxs-lookup"><span data-stu-id="58b65-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="58b65-115">與此命令會使用**Select-object** cmdlet 來限制傳回並顯示在螢幕上的資料。</span><span class="sxs-lookup"><span data-stu-id="58b65-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="58b65-116">在這個範例中， [Get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet 會擷取所有您 Skype for Business Online 使用者的資訊，然後**Select-object**指令程式會用來限制顯示的資料至使用者的 Identity 值與他們的封存原則：</span><span class="sxs-lookup"><span data-stu-id="58b65-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="58b65-117">因為會有數百個 cmdlet 可供使用您電腦上，您可能無法判斷哪個 cmdlet Skype for Business Online cmdlet 且哪些項目都不是。</span><span class="sxs-lookup"><span data-stu-id="58b65-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="58b65-118">若要傳回 Skype for Business Online cmdlet （和 Skype 商務 Online 指令程式） 的清單，您必須先決定暫時 Windows PowerShell 模組，其中包含所有商務用 Skype 商務 Online 指令程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="58b65-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="58b65-119">若要這樣做，請從 Windows PowerShell 提示字元中執行此命令：</span><span class="sxs-lookup"><span data-stu-id="58b65-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="58b65-120">下面類似的資訊將出現在螢幕上：</span><span class="sxs-lookup"><span data-stu-id="58b65-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="58b65-121">與 ModuleType 指令碼的模組是包含 Skype for Business Online 指令程式的模組。</span><span class="sxs-lookup"><span data-stu-id="58b65-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="58b65-122">若要傳回這些 cmdlet 的清單，請執行**Get-command**指令程式，使用指令碼模組的名稱與模組名稱：</span><span class="sxs-lookup"><span data-stu-id="58b65-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="58b65-123">有可能，您可能有多個模組中的使用 ModuleType 等於指令碼。</span><span class="sxs-lookup"><span data-stu-id="58b65-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="58b65-124">在此情況下，您可以執行下列命令，以找出哪一個模組包含**Get-cstenant**指令程式：</span><span class="sxs-lookup"><span data-stu-id="58b65-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="58b65-125">**Get-cstenant** cmdlet 傳回的模組將包含所有商務用 Skype 商務 Online 指令程式的模組：</span><span class="sxs-lookup"><span data-stu-id="58b65-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="58b65-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="58b65-126">See Also</span></span>


<span data-ttu-id="58b65-127">[Windows PowerShell 與 Skype for Business Online 簡介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="58b65-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

