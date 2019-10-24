---
title: 下載並安裝商務用 Skype Online 連接器模組
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: '下載、安裝及使用商務用 Skype Online 連接器，以建立連線至商務用 Skype Online 的遠端 Windows PowerShell 會話。 '
ms.openlocfilehash: 7e97bc31d85370919eec7c50fae01d00f5b1ddac
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "37642679"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>下載並安裝商務用 Skype Online 連接器模組

商務用 Skype Online 連接器模組包含**新的 CsOnlineSession** Cmdlet，可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援（請參閱[使用 Windows PowerShell 設定商務用 Skype Online 管理電腦](set-up-your-computer-for-windows-powershell.md)），以取得詳細資訊），可以從 Microsoft 下載中心下載[https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366)。 下載 SkypeOnlinePowershell 檔案，然後完成下列程式：
  
1. 按兩下**SkypeOnlinePowershell**檔案。
    
2. 在商務用 Skype Online 的 Windows PowerShell 設定向導中，選取 [ **Microsoft 軟體授權條款**] 頁面上的 [**我接受授權合約中的條款**]，然後按一下 [**安裝**]。 如果出現 [**使用者帳戶控制**] 對話方塊，請按一下 **[是]** 以繼續安裝。
    
3. 在 [**已完成商務用 Skype Online，Windows PowerShell 模組**] 頁面上，按一下 **[完成]**。
    
安裝程式會將商務用 Skype Online 連接器模組（以及新的**CsOnlineSession** Cmdlet）複製到您的電腦。 若要存取模組，請在 [管理員認證] 底下啟動 Windows PowerShell 會話，然後執行下列命令：
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

如果您不想在每次啟動 Windows PowerShell 時都輸入這個命令，您可以將命令新增至您的 Windows PowerShell 設定檔。 若要執行此動作，請在 Windows PowerShell 提示中輸入下列命令，然後按 ENTER：
  
```
notepad.exe $profile
```

 [記事本] 出現時，在設定檔中已有的命令底部新增下列行：
  
```
Import-Module SkypeOnlineConnector
```

儲存檔案。 下次啟動 Windows PowerShell 時，系統會自動匯入商務用 Skype Online 連接器模組。 請注意，如果您沒有在 [管理員認證] 下執行 Windows PowerShell，就會收到錯誤訊息，且不會載入模組。
  
除了安裝商務用 Skype Online 連接器模組之外，SkypeOnlinePowershell 也會安裝三個額外的元件：1）身分識別服務用戶端執行時間程式庫（IDCRL），用來處理商務用 Skype 的用戶端驗證Online2） .NET Framework 4.5;以及3） Microsoft Visual c + + 2012 可再發行（x64）套件（版本11.0.50727）。 .NET Framework 4.5 提供用來建立及執行 .NET 應用程式的基礎結構，包括 Windows PowerShell。 Visual c + + 可再發行套件會針對沒有安裝 Microsoft Visual Studio 2012 的電腦安裝 Visual c + + 執行時間元件。
  
若要確認您電腦上目前安裝的連接器模組版本號碼，請開啟 [控制台]，開啟 [**程式和功能**]，然後檢查**商務用 Skype Online、Windows PowerShell 模組**的版本號碼。
  
## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定商務用 skype online 管理電腦](set-up-your-computer-for-windows-powershell.md)

  
 
