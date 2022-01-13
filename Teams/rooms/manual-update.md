---
title: 手動更新Microsoft Teams 會議室裝置
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 瞭解如何手動將裝置Microsoft Teams 會議室到特定版本。
ms.openlocfilehash: 0b8ec08880d3f8c7ecce28293c92fb6ada901277
ms.sourcegitcommit: d2c76fe7705acf6e53f7673861671b1b018813dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2022
ms.locfileid: "62014993"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>手動更新Microsoft Teams 會議室裝置

此Microsoft Teams 會議室應用程式會透過 Microsoft Store。 應用程式更新會在夜間維護Microsoft Store自動從應用程式安裝;這是取得更新的建議方法。 不過，在某些情況下，Teams 會議室裝置無法從Microsoft Store。 例如，安全性原則可能不允許裝置連接到網際網路，或可能不允許應用程式從 Microsoft Store。 或者，在執行設定之前，您可能想要先更新裝置，Microsoft Store無法使用裝置。

如果您無法從 Microsoft Store 取得更新，您可以使用離線應用程式更新 PowerShell 腳本，將 Teams 會議室 裝置手動更新至較新版本的 Teams 會議室 App。 請遵循本文中的步驟，手動更新您的Teams 會議室裝置。

> [!NOTE]
> 此程式只能更新Teams 會議室已安裝Teams 會議室裝置。 它無法用來執行新安裝。 它也無法用來將應用程式降級為較舊版本。 若要執行新安裝的 Teams 會議室應用程式，請與您的裝置製造商聯繫，以尋找特定媒體。

## <a name="step-1-download-the-offline-app-update-script"></a>步驟 1：下載離線應用程式更新腳本

首先，下載最新版本的離線應用程式更新腳本。 若要下載腳本，請按一下 <https://go.microsoft.com/fwlink/?linkid=2151817> 。 腳本會下載到您裝置上的預設下載資料夾。

下載的檔案可能會標示為封鎖Windows。 如果您需要執行腳本而不進行任何互動，則需要解除封鎖腳本。 若要解除封鎖腳本，請執行下列操作：

1. 在檔案檔案管理器中以滑鼠右鍵按一下檔案
2. 按一下 **[屬性**
3. 選取 **取消封鎖**
4. 按一下 **[確定**

若要使用 PowerShell 解除封鎖腳本，請參閱 [解除封鎖-檔案](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。

下載離線應用程式更新腳本之後，將檔案傳輸至Teams 會議室裝置。 您可以使用 USB 磁碟機，或在裝置上的系統管理模式中從網路檔案共用存取檔案，將檔案傳輸至裝置。 請務必記下檔案儲存在裝置上的位置。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>步驟 2：執行腳本以更新Teams 會議室應用程式

離線應用程式更新腳本必須從提升的命令提示符執行，Skype使用者 (應用程式執行) 的使用者仍然會登錄。 若要進一步瞭解如何登入系統管理員帳戶，以在 Skype 使用者仍登入時使用提升的命令提示，請參閱切換到系統管理模式，以及當 Microsoft Teams 會議室 應用程式當機[時](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes)返回 。

執行下列操作，從提升的命令提示符執行腳本：

1. 切換到系統管理模式
2. 按一下 [開始點選圖示，輸入 **命令提示** 符，然後選取 **[以系統管理員角色執行**
3. 執行下列命令，其中包含腳本的完整路徑和腳本 `<path to script>` 檔案名：

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

例如，如果腳本檔案位於 中，且指令檔名 `C:\Users\Admin\Downloads` 為 `MTR-Update-4.5.6.7.ps1` ，請執行下列命令：

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

允許腳本執行。 完成後，腳本會重新開機Teams 會議室裝置。

您也可以使用遠端 PowerShell 執行腳本。 有關在裝置上使用遠端 PowerShell Teams 會議室，請參閱[使用 PowerShell 進行遠端系統管理](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>步驟 3：確認應用程式已成功更新

如果腳本成功執行，裝置會重新開機至 Teams 會議室 App。

如果腳本遇到問題，它會指出命令列上的問題，並記錄其輸出至檔案。 請遵循腳本提供的任何指示。 如果您需要與 Microsoft 支援服務聯繫，請務必包含記錄檔案以及支援要求。 腳本會提供記錄檔案的路徑。
