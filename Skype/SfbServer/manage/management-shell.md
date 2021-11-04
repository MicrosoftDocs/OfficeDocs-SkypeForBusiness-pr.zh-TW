---
title: 商務用 Skype Server 管理命令介面
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 商務用 Skype Server 管理命令介面提供伺服器管理和管理的命令列介面。 它是以 Windows PowerShell 為基礎，包含一組完整的管理和管理 Cmdlet，專門針對 Skype 和舊版 Lync server 產品。
ms.openlocfilehash: 2d8caadfb1dfe80af74861cf20fa0b155dd20d1a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750312"
---
# <a name="skype-for-business-server-management-shell"></a>商務用 Skype Server 管理命令介面
 
商務用 Skype Server 管理命令介面提供伺服器管理和管理的命令列介面。 它是以 Windows PowerShell 為基礎，包含一組完整的管理和管理 Cmdlet，專門針對 Skype 和舊版 Lync server 產品。
  
Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。 它包括命令列環境、產品特定命令，以及完整指令碼語言。 Windows PowerShell 是第一次在2006中新增為 Windows 作業系統的可下載版本，而且已融入為命令列介面，以 Microsoft Exchange Server 2007 的可管理性。 它已整合至大多數的 Microsoft 伺服器產品，包括從 lync Server 2010 開始的 lync server 和 Skype server。 商務用 Skype Server 管理命令介面中提供超過700的 Lync 和 Skype 特定 Cmdlet。
  
> [!NOTE]
> 商務用 Skype Cmdlet 參照已移至 docs.microsoft.com。 按一下下列連結將會帶您前往 [新增 docs.microsoft.com] 頁面。 內容現在已開啟，且可透過 GitHub 進行社區貢獻。 對共同作業感興趣？ 請參閱下列位置的讀我檔案： [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
商務用 Skype Server 隨附700個以上的 Cmdlet，讓系統管理員可以使用商務用 Skype Server 管理命令介面管理商務用 Skype Server。 您可以輸入類似如下的命令，直接從命令列取得 Cmdlet 的說明：
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

上述命令會檢索可用於 **New-CsVoicePolicy** Cmdlet 的完整説明。 若要查看其他 Cmdlet 的說明，請以您想要取得 help 之 Cmdlet 的名稱取代 **New-CsVoicePolicy** 。
  
若要取得可用於管理商務用 Skype Server 的完整 Cmdlet 清單，請在命令介面命令提示字元處輸入下列命令： 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



商務用 Skype Server 中 Windows PowerShell 的相關須知：
  
- 若要執行商務用 Skype Server Cmdlet，請開啟商務用 Skype Server 管理命令介面。
    
    > [!CAUTION]
    > 如果您開啟 Windows PowerShell 視窗，而不是商務用 Skype Server 管理命令介面，則預設可能無法執行 Skype Cmdlet。 若要從 Windows PowerShell 中執行商務用 Skype Server Cmdlet，請先在 Windows PowerShell 命令提示字元處輸入下列命令： >`Import-Module SkypeforBusiness`
  
- 商務用 Skype Server管理命令介面會自動安裝在每一部商務用 Skype Server Enterprise Edition 前端伺服器或 Standard Edition 伺服器上。
    
- 您可以執行[Update-Help](/powershell/module/microsoft.powershell.core/update-help) Cmdlet 來更新商務用 Skype Server 管理命令介面說明內容。 Update-Help Cmdlet 會下載並安裝適用于電腦上所有模組（包括商務用 Skype Cmdlet 的更新）的最新說明檔。
    
    根據預設， **Update-Help** Cmdlet 會更新您商務用 Skype Server 上安裝的所有模組。 如果您只想更新特定的模組，您可以使用 _Module_ 參數來限制 Cmdlet 的範圍。 下列範例只會更新商務用 Skype 模組。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    如果您需要更新未連接至網際網路之伺服器上的說明，您可以使用 [Save-Help](/powershell/module/microsoft.powershell.core/save-help) Cmdlet 來取得最新版本的說明，並將其儲存至您指定的位置。 然後，您可以在未連線至網際網路的伺服器上使用 _-SourcePath_ 參數的 **Update-Help** Cmdlet，以從選取的位置取得更新的說明。 下列範例會示範如何將說明檔案儲存至網路檔案共用，然後從檔案共用更新商務用 Skype 模組的說明。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    如需詳細資訊，請參閱 [關於可更新的協助](/powershell/module/microsoft.powershell.core/about/about_updatable_help)。
    
    > [!NOTE]
    > 如果您遠端使用 PowerShell，您可能需要透過防火牆允許通訊。 若要深入瞭解 PowerShell 遠端使用的埠，請參閱 [Remoting 使用哪個埠 PowerShell？](/archive/blogs/christwe/what-port-does-powershell-remoting-use)。
