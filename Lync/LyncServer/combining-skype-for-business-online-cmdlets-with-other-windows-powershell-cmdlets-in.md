---
title: 結合商務用 Skype Online Cmdlet 與其他 Windows PowerShell Cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: bd4f08370e5aeab6688fdbf2ce13a3e5ccb11a37
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a>結合商務用 Skype Online Cmdlet 與其他 Windows PowerShell Cmdlet

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-07-05_

當您使用 Windows PowerShell 連接至商務用 Skype Online 時，大約40的商務用 Skype Online Cmdlet 可供您使用。 不過，當您管理商務用 Skype Online 時，並不局限于只使用那些 40 Cmdlet。 除了商務用 Skype Online Cmdlet 之外，您還可以使用電腦上安裝的任何其他 Windows PowerShell Cmdlet。 （當您安裝 Windows PowerShell 3.0 時，會同時安裝數百個核心 Windows PowerShell Cmdlet。）您的命令可以混合和比對您電腦上可用的商務用 Skype Online Cmdlet 及任何其他 Cmdlet。

雖然 Windows PowerShell 3.0 中的完整課程超出本文的範疇，但這裡有幾個範例會示範為何您可能想要混合和符合 Cmdlet。 首先，沒有任何商務用 Skype Online Cmdlet 包含 Print 命令，而且在 Windows PowerShell 主控台中也無法找到這類命令。 那麼，如何取得 Cmdlet 所取得資訊的列印輸出？ 其中一種方法是取回信息，然後將該資訊傳送至**Out-Printer** Cmdlet：

    Get-CsTenant | Out-Printer

因為未包含其他參數，所以**Out-Printer** Cmdlet 所傳回的所有資訊都會列印到預設印表機。

同樣地，任何商務用 Skype Online Cmdlet 都不包含可讓您將資料儲存至檔案的參數。 不過，這也是好的：這個命令會使用**Out-File** Cmdlet，將傳回的資訊儲存至文字檔 C： \\ Logs \\Tenants.txt：

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

而且，此命令會使用**Select-Object** Cmdlet 來限制在螢幕上傳回及顯示的資料。 在此範例中， [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) Cmdlet 會為所有商務用 Skype Online 使用者檢索資訊，然後使用**Select-Object**指令程式，將顯示的資料限制為使用者的身分識別值及其封存原則：

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

由於您的電腦上有數百個 Cmdlet 可供使用，您可能無法判斷哪些 Cmdlet 是商務用 Skype Online Cmdlet，哪些是不是。 若要傳回商務用 Skype Online Cmdlet 的清單（而且只是商務用 Skype Online Cmdlet），您必須先決定包含所有商務用 Skype Online Cmdlet 的臨時 Windows PowerShell 模組的名稱。 若要這樣做，請從 Windows PowerShell 提示字元中執行此命令：

    Get-Module

螢幕上會出現類似下列的資訊：

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

包含 ModuleType 腳本的模組是包含商務用 Skype Online Cmdlet 的模組。 若要傳回這些 Cmdlet 的清單，請使用 Script 模組的名稱作為模組名稱，以執行**Get-Command** Cmdlet：

    Get-Command -Module tmp_5astd3uh.m5v

您可能會有多個模組的 ModuleType 等於 Script。 在此情況下，您可以執行下列命令，以找出哪個模組包含**Get-CsTenant** Cmdlet：

    Get-Command Get-CsTenant

為**Get-CsTenant** Cmdlet 所傳回的模組將是包含所有商務用 Skype Online Cmdlet 的模組：

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a>另請參閱


[Windows PowerShell 和商務用 Skype Online 簡介](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

