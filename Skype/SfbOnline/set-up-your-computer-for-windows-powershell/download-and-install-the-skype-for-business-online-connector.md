---
title: 下載並安裝商務用 Skype Online Connector 模組
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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 下載、安裝，然後使用商務用 Skype Online Connector 來建立連線至商務用 Skype Online 的遠端 Windows PowerShell 會話。
ms.openlocfilehash: 5883eba8dc4dd959e67e45aa27413624e0f5d941
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568939"
---
# <a name="download-and-install-the-teams-powershell-module"></a>下載並安裝 Teams PowerShell 模組

> [!NOTE]

> 最新的 [Teams PowerShell 公開](https://www.powershellgallery.com/packages/MicrosoftTeams/) 發行已與商務用 Skype Online Connector 整合，為 Teams 和商務用 Skype 線上 PowerShell 管理提供單一模組。


1. 安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示程式，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   如果您想要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定電腦進行商務用 Skype 線上管理](set-up-your-computer-for-windows-powershell.md)
