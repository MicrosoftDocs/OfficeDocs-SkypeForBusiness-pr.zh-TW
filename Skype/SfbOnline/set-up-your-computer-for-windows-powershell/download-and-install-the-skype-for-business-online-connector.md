---
title: 下載並安裝 商務用 Skype線上連接器模組
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 下載、安裝，然後使用 商務用 Skype 線上連接器來建立Windows PowerShell連線至線上商務用 Skype會話。
ms.openlocfilehash: 9e7bb6f4ad58e04fa8e42077205b17005aed3506
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597837"
---
# <a name="download-and-install-the-teams-powershell-module"></a>下載並安裝 powerShell Teams模組

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> 最新版[powerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本已與 商務用 Skype Online Connector 整合，提供單一模組Teams及商務用 Skype PowerShell 管理。


1. 安裝 Teams [PowerShell 模組](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell命令提示符，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   若要進一Windows PowerShell，請參閱連線視窗中連線所有 Microsoft 365 或 Office 365 [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服務，或設定您的電腦[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>相關主題
[使用電腦設定商務用 skype 線上管理Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
