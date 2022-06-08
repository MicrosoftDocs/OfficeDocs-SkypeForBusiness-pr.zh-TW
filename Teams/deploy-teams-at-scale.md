---
title: 在 Microsoft Teams 中針對第一線工作人員大規模部署團隊
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對組織中的一線工作人員，以規模部署團隊。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 655e79e70945419c446dab3d721334a1a70b0e9e
ms.sourcegitcommit: d54217d3c339fe02f83d86efe50dabe67528a14c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/08/2022
ms.locfileid: "65947224"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>在 Microsoft Teams 中針對第一線工作人員大規模部署團隊

> [!NOTE]
> 這項功能目前處於私人預覽中。 如果您想要參與私人預覽，請在 [dscale@microsoft.com](mailto:dscale@microsoft.com)與我們連絡。

## <a name="overview"></a>概觀
 
您的組織可能有許多團隊可用來促進前線員工之間的通訊和共同作業，他們分散在不同的商店、地點和角色。 目前，部署、設定及管理這些團隊和使用者的解決方案並不簡單。

我們正在建置解決方案，讓系統管理員能夠以規模部署和管理團隊。

以下是目前可用來一次建立及管理大量團隊的功能概觀，以及近期的規劃。

||今天提供 |2022 年稍後版本  |
|---------|---------|---------|
|**每批可建立的團隊數目**|最多 100 個 |最多 500 個|
|**您可以為每個團隊新增的使用者數目**|最多 25 個|最多 25 個|

以縮放比例部署團隊可讓您：

- 使用預先建立的範本或您自己的自訂範本來建立團隊。
- 以擁有者或成員的身分將使用者新增至團隊。
- 從現有團隊新增或移除使用者，以規模管理團隊。
- 透過電子郵件持續收到通知，包括完成、狀態和錯誤 (如果有) 。 團隊擁有者和成員會收到通知。

## <a name="how-to-deploy-teams-at-scale"></a>如何大規模部署團隊

> [!NOTE]
> 在部署您的團隊之前，請確定所有團隊擁有者都擁有 Teams 授權。

請依照下列步驟一次部署大量團隊。

您可以使用 ```New-CsBatchTeamsDeployment``` Cmdlet 提交一批要建立的團隊。 系統會針對每個批次產生協調識別碼。 接著， ```Get-CsBatchTeamsDeployment``` 您可以使用 Cmdlet 來追蹤每個批次的進度和狀態。

1. 安裝 PowerShell 版本 7 或更新版本。 如需逐步指引，請參閱 [在 Windows 上安裝 PowerShell](/powershell/scripting/install/installing-powershell-on-windows)。
1. 以系統管理員模式執行 PowerShell。
1. 執行下列動作以卸載任何先前安裝的 Teams PowerShell 模組。

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    如果您收到錯誤訊息，表示您已設定完成。 移至下一個步驟。
1. 下載並安裝 [最新版的 Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。

1. 執行下列動作以連線至 Teams。

    ```powershell
    Connect-MicrosoftTeams
    ```

    出現提示時，請使用您的系統管理員認證登入。

1. 執行下列動作以取得 Teams PowerShell 模組中的命令清單。

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    確認並 ```New-CsBatchTeamsDeployment``` ```Get-CsBatchTeamsDeployment``` 列出。

1. 執行下列動作以部署一批團隊。 您最多可以在 **UsersToNotify** 參數中輸入五個電子郵件地址。

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "*Your file path*" -UsersFilePath "*Your file path*" -UsersToNotify *Email addresses* 
    ```

1. 執行下列動作以檢查您提交的批次狀態。

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>傳送意見反應給我們

我們很重視您的意見反應。 我們歡迎我們提供可用性、可靠性和效 &mdash; 能！

電子郵件 [dscale@microsoft.com](mailto:dscale@microsoft.com) ，如果有的話，請包含您的編排識別碼和錯誤檔案。

## <a name="related-articles"></a>相關文章

- [Teams PowerShell 概觀](teams-powershell-overview.md)
