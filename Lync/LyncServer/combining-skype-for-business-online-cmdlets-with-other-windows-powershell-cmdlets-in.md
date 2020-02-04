---
title: 將商務用 Skype Online Cmdlet 與其他 Windows PowerShell Cmdlet 結合在一起
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
ms.openlocfilehash: e7d0dd6070eb3c69b23f03e56bf542025c221b15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="96d3c-102">將商務用 Skype Online Cmdlet 與其他 Windows PowerShell Cmdlet 結合在一起</span><span class="sxs-lookup"><span data-stu-id="96d3c-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96d3c-103">_**主題上次修改日期：** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="96d3c-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="96d3c-104">當您使用 Windows PowerShell 連線到商務用 Skype Online 時，您可以使用大約40的商務用 Skype Online Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96d3c-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="96d3c-105">不過，管理商務用 Skype Online 時，您並不限於只使用這些 40 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96d3c-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="96d3c-106">除了商務用 Skype Online Cmdlet 之外，您還可以使用安裝在您電腦上的任何其他 Windows PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96d3c-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="96d3c-107">（當您安裝 Windows PowerShell 3.0 時，也會安裝上百個核心 Windows PowerShell Cmdlet）。您的命令可以混合搭配商務用 Skype Online Cmdlet 和電腦上可用的任何其他 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96d3c-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="96d3c-108">雖然 Windows PowerShell 3.0 中的完整課程超出本文的範圍，以下幾個範例會示範您可能會想要混合搭配 Cmdlet 的原因。</span><span class="sxs-lookup"><span data-stu-id="96d3c-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="96d3c-109">首先，所有商務用 Skype Online Cmdlet 都不含 [列印] 命令，而且在 Windows PowerShell 主控台中也無法找到此類命令。</span><span class="sxs-lookup"><span data-stu-id="96d3c-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="96d3c-110">您該如何取得由 Cmdlet 檢索之資訊的列印成品？</span><span class="sxs-lookup"><span data-stu-id="96d3c-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="96d3c-111">其中一個方法是取回信息，然後將該資訊傳送給**印表機外**Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="96d3c-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="96d3c-112">由於不包含任何其他參數，因此由**印表機**Cmdlet 傳回的所有資訊都會列印到預設印表機。</span><span class="sxs-lookup"><span data-stu-id="96d3c-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="96d3c-113">同樣地，任何商務用 Skype Online Cmdlet 都不包含可讓您將資料儲存至檔案的參數。</span><span class="sxs-lookup"><span data-stu-id="96d3c-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="96d3c-114">但這樣就可以了：這個命令使用**Out**檔案 Cmdlet，將傳回的資訊儲存到文字檔 C：\\記錄\\承租人：</span><span class="sxs-lookup"><span data-stu-id="96d3c-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="96d3c-115">這個命令會使用**Select 物件**Cmdlet 來限制在螢幕上傳回及顯示的資料。</span><span class="sxs-lookup"><span data-stu-id="96d3c-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="96d3c-116">在這個範例中， [CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) Cmdlet 會為您所有的商務用 Skype Online 使用者取得資訊，然後使用**Select-物件**Cmdlet 來將顯示的資料限制為使用者的身分識別值和其存檔原則：</span><span class="sxs-lookup"><span data-stu-id="96d3c-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="96d3c-117">因為您可以在電腦上使用幾百個 Cmdlet，所以您可能無法判斷哪些 Cmdlet 是商務用 Skype Online Cmdlet，哪些是不是的。</span><span class="sxs-lookup"><span data-stu-id="96d3c-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="96d3c-118">若要傳回商務用 Skype Online Cmdlet （且僅適用于商務用 Skype Online Cmdlet）的清單，您必須先判斷包含所有商務用 Skype Online Cmdlet 的臨時 Windows PowerShell 模組的名稱。</span><span class="sxs-lookup"><span data-stu-id="96d3c-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="96d3c-119">若要執行此動作，請從 Windows PowerShell 提示執行此命令：</span><span class="sxs-lookup"><span data-stu-id="96d3c-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="96d3c-120">類似下列的資訊將會出現在螢幕上：</span><span class="sxs-lookup"><span data-stu-id="96d3c-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="96d3c-121">含 ModuleType 腳本的模組是包含商務用 Skype Online Cmdlet 的模組。</span><span class="sxs-lookup"><span data-stu-id="96d3c-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="96d3c-122">若要傳回這些 Cmdlet 的清單，請執行**Command** Cmdlet，並使用腳本模組的名稱做為模組名稱：</span><span class="sxs-lookup"><span data-stu-id="96d3c-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="96d3c-123">您可能會有多個含 ModuleType 等於 Script 的模組。</span><span class="sxs-lookup"><span data-stu-id="96d3c-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="96d3c-124">在這種情況下，您可以執行下列命令，找出包含**CsTenant** Cmdlet 的模組：</span><span class="sxs-lookup"><span data-stu-id="96d3c-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="96d3c-125">針對**CsTenant** Cmdlet 傳回的模組將是包含所有商務用 Skype Online Cmdlet 的模組：</span><span class="sxs-lookup"><span data-stu-id="96d3c-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="96d3c-126">請參閱</span><span class="sxs-lookup"><span data-stu-id="96d3c-126">See Also</span></span>


<span data-ttu-id="96d3c-127">[Windows PowerShell 與 Lync Online 的簡介](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="96d3c-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

