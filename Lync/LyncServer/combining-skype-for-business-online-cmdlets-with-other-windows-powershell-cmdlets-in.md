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
ms.openlocfilehash: f95d242ec5a1f24f403e59b49e305d9e0a6c84b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>合併 Skype 商務 Online cmdlet 與在其他 Windows PowerShell cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-07-05_

當您連接至 Skype for Business Online 使用 Windows PowerShell 時，約 40 Skype for Business Online cmdlet 將可供您使用。 不過，您不一定要管理商務用 Skype 時使用只有 40 指令程式。 除了 Skype for Business Online 指令程式，您也可以使用任何其他電腦安裝的 Windows PowerShell cmdlet。 （當您安裝 Windows PowerShell 3.0 時，數百個核心 Windows PowerShell 指令程式會安裝，以及）。命令可以混合和相符 Skype for Business Online cmdlet 與任何其他指令程式可以在您電腦上。

雖然這是在 Windows PowerShell 3.0 的完整課程超出本文章的涵蓋範圍，以下是一些範例，說明您可能想可以混合及比對指令程式。 首先，無 Skype for Business Online 指令程式包含列印] 命令，並沒有這類命令中，可以找到 [Windows PowerShell 主控台，或是。 您要那要如何取得列印文件的指令程式所擷取的資訊？ 一種方式是擷取的詳細資訊，並再將該資訊傳送至**Out-printer**指令程式：

    Get-CsTenant | Out-Printer

因為沒有其他參數都包含在內，將會以預設的印表機列印**Out-printer** cmdlet 所傳回的所有資訊。

同樣地，無 Skype for Business Online 指令程式包含參數，可讓您將資料儲存至檔案。 但這是 [確定]: 這個命令會使用**Out-file** cmdlet 以將傳回的資訊儲存到文字檔 c:\\記錄\\Tenants.txt:

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

與此命令會使用**Select-object** cmdlet 來限制傳回並顯示在螢幕上的資料。 在這個範例中， [Get-csonlineuser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet 會擷取所有您 Skype for Business Online 使用者的資訊，然後**Select-object**指令程式會用來限制顯示的資料至使用者的 Identity 值與他們的封存原則：

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

因為會有數百個 cmdlet 可供使用您電腦上，您可能無法判斷哪個 cmdlet Skype for Business Online cmdlet 且哪些項目都不是。 若要傳回 Skype for Business Online cmdlet （和 Skype 商務 Online 指令程式） 的清單，您必須先決定暫時 Windows PowerShell 模組，其中包含所有商務用 Skype 商務 Online 指令程式的名稱。 若要這樣做，請從 Windows PowerShell 提示字元中執行此命令：

    Get-Module

下面類似的資訊將出現在螢幕上：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

與 ModuleType 指令碼的模組是包含 Skype for Business Online 指令程式的模組。 若要傳回這些 cmdlet 的清單，請執行**Get-command**指令程式，使用指令碼模組的名稱與模組名稱：

    Get-Command -Module tmp_5astd3uh.m5v

有可能，您可能有多個模組中的使用 ModuleType 等於指令碼。 在此情況下，您可以執行下列命令，以找出哪一個模組包含**Get-cstenant**指令程式：

    Get-Command Get-CsTenant

**Get-cstenant** cmdlet 傳回的模組將包含所有商務用 Skype 商務 Online 指令程式的模組：

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>另請參閱


[Windows PowerShell 與 Skype for Business Online 簡介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

