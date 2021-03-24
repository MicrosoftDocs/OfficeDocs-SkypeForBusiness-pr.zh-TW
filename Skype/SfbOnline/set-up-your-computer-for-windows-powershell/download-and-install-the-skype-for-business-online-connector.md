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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 下載、安裝，然後使用商務用 Skype Online 連接器來建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。
ms.openlocfilehash: 0e00b9dd18b04deaf3d2123de1fa9609040c4e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097199"
---
# <a name="download-and-install-the-teams-powershell-module"></a><span data-ttu-id="81315-103">下載並安裝 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="81315-103">Download and install the Teams PowerShell module</span></span>

> [!NOTE]

> <span data-ttu-id="81315-104">最新的 [Teams PowerShell 公開](https://www.powershellgallery.com/packages/MicrosoftTeams/) 發行已與商務用 Skype Online Connector 整合，為 Teams 和商務用 Skype Online PowerShell 管理提供單一模組。</span><span class="sxs-lookup"><span data-stu-id="81315-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams and Skype for Business online PowerShell management.</span></span>


1. <span data-ttu-id="81315-105">安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="81315-105">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="81315-106">開啟 Windows PowerShell 命令提示符，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="81315-106">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="81315-107">如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 服務，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="81315-107">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="81315-108">相關主題</span><span class="sxs-lookup"><span data-stu-id="81315-108">Related topics</span></span>
[<span data-ttu-id="81315-109">使用 Windows PowerShell 設定商務用 Skype 線上管理的電腦</span><span class="sxs-lookup"><span data-stu-id="81315-109">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)