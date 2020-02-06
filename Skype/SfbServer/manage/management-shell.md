---
title: 商務用 Skype Server 管理命令介面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: 商務用 Skype Server 管理命令介面提供伺服器管理和管理的命令列介面。 它是在 Windows PowerShell 中建立的，包含一組專用於 Skype 與舊版 Lync server 產品的完整管理和管理 Cmdlet。
ms.openlocfilehash: 294de750795985d50c6301a88f4b835f1cad78b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817552"
---
# <a name="skype-for-business-server-management-shell"></a>商務用 Skype Server 管理命令介面
 
商務用 Skype Server 管理命令介面提供伺服器管理和管理的命令列介面。 它是在 Windows PowerShell 中建立的，包含一組專用於 Skype 與舊版 Lync server 產品的完整管理和管理 Cmdlet。
  
Windows PowerShell 可讓您從命令列管理 Microsoft 應用程式。 它包含命令列環境、產品特定命令及完整的腳本撰寫語言。 Windows PowerShell 最初是在2006中提供給 Windows 作業系統的可下載版本，並已融入為 Microsoft Exchange Server 2007 可管理性的命令列介面。 它已融入大部分的 Microsoft 伺服器產品中，包括從 Lync Server 2010 開始的 Lync 和 Skype 伺服器。 商務用 Skype Server Management Shell 中有超過700的 Lync 和 Skype 特定 Cmdlet。
  
> [!NOTE]
> 商務用 Skype Cmdlet 參考已移至 docs.microsoft.com。 按一下下方的連結，會將您帶到 [新增 docs.microsoft.com] 頁面。 內容現在已開啟來源，且可供 GitHub 的群組發佈。 想要進行共同作業嗎？ 查看存放庫中的讀我檔案：[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
商務用 skype 伺服器隨附700個以上的 Cmdlet，讓系統管理員可以使用商務用 Skype Server Management Shell 來管理商務用 Skype 伺服器。 您可以直接從命令列取得 Cmdlet 的說明，方法是輸入類似以下的命令：
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

上述命令會檢索**CsVoicePolicy** Cmdlet 提供的完整說明。 若要查看其他 Cmdlet 的說明，請以**新的 CsVoicePolicy**取代您要取得其說明的 Cmdlet 名稱。
  
若要取得可用於管理商務用 Skype Server 的完整 Cmdlet 清單，請在 shell 命令提示字元輸入以下內容： 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



商務用 Skype Server 中的 Windows PowerShell 須知：
  
- 若要執行商務用 Skype Server Cmdlet，請開啟商務用 Skype Server 管理命令介面。
    
    > [!CAUTION]
    > 如果您開啟的是 Windows PowerShell 視窗，而不是商務用 Skype Server Management Shell，則預設可能無法執行 Skype Cmdlet。 若要在 Windows PowerShell 中執行商務用 Skype Server Cmdlet，請先在 Windows PowerShell 命令提示字元輸入以下命令： >`Import-Module SkypeforBusiness`
  
- 商務用 skype Server Management 命令介面會自動安裝在每個商務用 Skype Server Enterprise Edition 前端伺服器或標準版伺服器上。
    
- 您可以執行[update-help](https://technet.microsoft.com/en-us/library/hh849720.aspx) Cmdlet 來更新商務用 Skype Server Management Shell 說明內容。 Update-Help Cmdlet 會下載並安裝您電腦上安裝的所有模組可用的最新說明檔案，包括商務用 Skype Cmdlet 的更新。
    
    根據預設， **update-Help** Cmdlet 會更新所有安裝在商務用 Skype Server 上的模組。 如果只要更新特定模組，可以使用 _Module_ 參數來限制 Cmdlet 的範圍。 下列範例只會更新商務用 Skype 模組。
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    如果您需要更新未連線至網際網路之伺服器上的說明，您可以使用[Save-help](https://technet.microsoft.com/en-us/library/hh849724.aspx) Cmdlet 來取得最新版本的說明，並將它儲存到您指定的位置。 接著，您可以在未連線至網際網路的伺服器上，將**Update help** Cmdlet 與 _-SourcePath_參數搭配使用，從您選取的位置取得更新的說明。 下列範例顯示如何將說明檔案儲存至網路檔案共用，然後從檔案共用更新商務用 Skype 模組的說明。
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    如需更多詳細資訊，請參閱[關於可更新的協助](https://technet.microsoft.com/library/hh847735.aspx)。
    
    > [!NOTE]
    > 如果您是在遠端使用 PowerShell，您可能需要允許透過防火牆進行通訊。 若要深入瞭解 PowerShell remoting 使用的埠，請參閱[Powershell Remoting 使用哪個埠？](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)。
    

