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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 下載、安裝，然後使用 商務用 Skype Online 連接器來建立Windows PowerShell連線至線上商務用 Skype會話。
ms.openlocfilehash: e9429b385f83f6b76e211614f953f7d439df524e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238864"
---
# <a name="download-and-install-the-teams-powershell-module"></a><span data-ttu-id="e4866-103">下載並安裝 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="e4866-103">Download and install the Teams PowerShell module</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> <span data-ttu-id="e4866-104">最新的[PowerShell Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本已與 商務用 Skype Online Connector 整合，提供單一模組Teams及商務用 Skype PowerShell 管理。</span><span class="sxs-lookup"><span data-stu-id="e4866-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams and Skype for Business online PowerShell management.</span></span>


1. <span data-ttu-id="e4866-105">安裝[powerShell Teams模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="e4866-105">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="e4866-106">開啟 Windows PowerShell命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e4866-106">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="e4866-107">如果您想要啟動 Windows PowerShell 功能連線，請參閱在單一 Microsoft 365 視窗中Office 365所有 Microsoft 365 或 Office 365 [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服務，或設定您的電腦[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e4866-107">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e4866-108">相關主題</span><span class="sxs-lookup"><span data-stu-id="e4866-108">Related topics</span></span>
[<span data-ttu-id="e4866-109">使用電腦設定商務用 skype 線上管理Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e4866-109">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
