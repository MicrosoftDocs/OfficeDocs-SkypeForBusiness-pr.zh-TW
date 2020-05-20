---
title: 安裝團隊 PowerShell 模組的預發行版本本
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 請依照下列步驟，從 PowerShell 測試圖庫安裝團隊 PowerShell 模組的預發行版本本。
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321766"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>安裝團隊 PowerShell 模組的預發行版本本

本文說明如何從[PowerShell 測試圖庫](https://www.poshtestgallery.com/packages/MicrosoftTeams/)安裝團隊 PowerShell 模組最新的預發行版本本。 您需要在案例中使用團隊 PowerShell 模組的預發行版本本，在此案例中，系統不支援管理團隊功能的 Cmdlet，且僅適用于預發行版本本。

使用這些步驟從 PowerShell 測試圖庫安裝團隊 PowerShell 模組的最新預發行版本本。

> [!NOTE]
> 請勿從 PowerShell 測試圖庫並排安裝團隊 PowerShell 模組與[公用 PowerShell 庫](https://www.powershellgallery.com/packages/MicrosoftTeams/)中的模組版本。 請依照下列步驟，先從公用 PowerShell 庫中卸載團隊 PowerShell 模組，然後從 PowerShell 測試圖庫安裝最新版本的模組。

1. 關閉所有現有的 PowerShell 會話。
2. 啟動新的 Windows PowerShell 模組實例。
3. 執行下列動作，從公用 PowerShell 庫中卸載團隊 PowerShell 模組：

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 關閉所有現有的 PowerShell 會話。
5. 再次啟動 Windows PowerShell 模組，然後執行下列動作，以將 PowerShell 測試圖庫註冊為受信任的來源：

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. 執行下列動作，從 PowerShell 測試圖庫安裝最新的團隊 PowerShell 模組：

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>從 PowerShell 測試圖庫更新到最新版本的團隊 PowerShell 模組

如果您已經從 PowerShell 測試庫安裝團隊 PowerShell 模組，請使用下列步驟更新到最新版本。

1. 關閉所有現有的 PowerShell 會話。
2. 啟動新的 Windows PowerShell 模組實例。
3. 執行下列操作以從 PowerShell 測試圖庫更新目前已安裝的團隊 PowerShell 模組版本：

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 執行下列動作，確認已成功安裝 PowerShell 測試圖庫中的最新版本的團隊 PowerShell 模組：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
