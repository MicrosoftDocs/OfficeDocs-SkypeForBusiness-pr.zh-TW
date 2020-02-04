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

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>將商務用 Skype Online Cmdlet 與其他 Windows PowerShell Cmdlet 結合在一起

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-05_

當您使用 Windows PowerShell 連線到商務用 Skype Online 時，您可以使用大約40的商務用 Skype Online Cmdlet。 不過，管理商務用 Skype Online 時，您並不限於只使用這些 40 Cmdlet。 除了商務用 Skype Online Cmdlet 之外，您還可以使用安裝在您電腦上的任何其他 Windows PowerShell Cmdlet。 （當您安裝 Windows PowerShell 3.0 時，也會安裝上百個核心 Windows PowerShell Cmdlet）。您的命令可以混合搭配商務用 Skype Online Cmdlet 和電腦上可用的任何其他 Cmdlet。

雖然 Windows PowerShell 3.0 中的完整課程超出本文的範圍，以下幾個範例會示範您可能會想要混合搭配 Cmdlet 的原因。 首先，所有商務用 Skype Online Cmdlet 都不含 [列印] 命令，而且在 Windows PowerShell 主控台中也無法找到此類命令。 您該如何取得由 Cmdlet 檢索之資訊的列印成品？ 其中一個方法是取回信息，然後將該資訊傳送給**印表機外**Cmdlet：

    Get-CsTenant | Out-Printer

由於不包含任何其他參數，因此由**印表機**Cmdlet 傳回的所有資訊都會列印到預設印表機。

同樣地，任何商務用 Skype Online Cmdlet 都不包含可讓您將資料儲存至檔案的參數。 但這樣就可以了：這個命令使用**Out**檔案 Cmdlet，將傳回的資訊儲存到文字檔 C：\\記錄\\承租人：

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

這個命令會使用**Select 物件**Cmdlet 來限制在螢幕上傳回及顯示的資料。 在這個範例中， [CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) Cmdlet 會為您所有的商務用 Skype Online 使用者取得資訊，然後使用**Select-物件**Cmdlet 來將顯示的資料限制為使用者的身分識別值和其存檔原則：

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

因為您可以在電腦上使用幾百個 Cmdlet，所以您可能無法判斷哪些 Cmdlet 是商務用 Skype Online Cmdlet，哪些是不是的。 若要傳回商務用 Skype Online Cmdlet （且僅適用于商務用 Skype Online Cmdlet）的清單，您必須先判斷包含所有商務用 Skype Online Cmdlet 的臨時 Windows PowerShell 模組的名稱。 若要執行此動作，請從 Windows PowerShell 提示執行此命令：

    Get-Module

類似下列的資訊將會出現在螢幕上：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

含 ModuleType 腳本的模組是包含商務用 Skype Online Cmdlet 的模組。 若要傳回這些 Cmdlet 的清單，請執行**Command** Cmdlet，並使用腳本模組的名稱做為模組名稱：

    Get-Command -Module tmp_5astd3uh.m5v

您可能會有多個含 ModuleType 等於 Script 的模組。 在這種情況下，您可以執行下列命令，找出包含**CsTenant** Cmdlet 的模組：

    Get-Command Get-CsTenant

針對**CsTenant** Cmdlet 傳回的模組將是包含所有商務用 Skype Online Cmdlet 的模組：

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>請參閱


[Windows PowerShell 與 Lync Online 的簡介](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

