---
title: 手動更新 Microsoft Teams 會議室裝置
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
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 瞭解如何手動將 Microsoft Teams 會議室裝置更新至特定版本。
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117511"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>手動更新 Microsoft Teams 會議室裝置

Microsoft Teams 會議室應用程式會透過 Microsoft Store 發佈。 應用程式更新會在夜間維護期間自動從 Microsoft Store 安裝;這是取得更新的建議方法。 不過，在某些情況下，Teams 會議室裝置無法從 Microsoft Store 接收更新。 例如，安全性原則可能不允許裝置連接到網際網路，或可能不允許從 Microsoft Store 下載應用程式。 或者，在執行設定之前，您可能會想要先更新裝置，在此期間 Microsoft Store 無法使用。

如果您無法從 Microsoft Store 取得更新，您可以使用離線應用程式更新 PowerShell 腳本，將 Teams 會議室裝置手動更新至較新版本的 Teams 會議室應用程式。 請遵循本文中的步驟，手動更新 Teams 會議室裝置。

> [!NOTE]
> 此程式只能更新已安裝 Teams 會議室應用程式的 Teams 會議室裝置。 它無法用來執行新安裝。 它也無法用來將應用程式降級為較舊版本。 若要執行 Teams 會議室應用程式的新安裝，請針對裝置的特定媒體，與裝置製造商聯繫，或參閱準備 [安裝媒體](console.md#prepare-the-installation-media)。

## <a name="step-1-download-the-offline-app-update-script"></a>步驟 1：下載離線應用程式更新腳本

首先，下載最新版本的離線應用程式更新腳本。 若要下載腳本，請按一下 <https://go.microsoft.com/fwlink/?linkid=2151817> 。 腳本會下載到您裝置上的預設下載資料夾。

下載的檔案可能會標示為 Windows 封鎖。 如果您需要執行腳本而不進行任何互動，則需要解除封鎖腳本。 若要解除封鎖腳本，請執行下列操作：

1. 在檔案檔案管理器中以滑鼠右鍵按一下檔案
2. 按一下 **[屬性**
3. 選取 **取消封鎖**
4. 按一下 **[確定**

若要使用 PowerShell 解除封鎖腳本，請參閱 [解除封鎖-檔案](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。

下載離線應用程式更新腳本之後，將檔案傳輸至 Teams 會議室裝置。 您可以在裝置上的系統管理模式中，使用 USB 磁碟機或從網路檔案共用存取檔案，將檔案傳輸至裝置。 請務必記下檔案儲存在裝置上的位置。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>步驟 2：執行腳本以更新 Teams 會議室應用程式

離線應用程式更新腳本必須從提升的命令提示符執行，而 Skype 使用者 (應用程式執行程式的使用者) 仍然會登錄。 若要進一步瞭解如何登入系統管理員帳戶，以在 Skype 使用者仍登入時使用提升的命令提示，請參閱切換至系統管理模式，以及 [Microsoft Teams 會議室](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)應用程式執行時返回 。

執行下列操作，從提升的命令提示符執行腳本：

1. 切換到系統管理模式
2. 按一下 [開始點選圖示，輸入 **命令提示** 符，然後選取 **[以系統管理員角色執行**
3. 執行下列命令， `<path to script>` 其中包含腳本的完整路徑和指令檔名：

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

例如，如果腳本檔案位於 中，且指令檔名 `C:\Users\Admin\Downloads` 為 `MTR-Update-4.5.6.7.ps1` ，請執行下列命令：

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

允許腳本執行。 完成後，腳本會重新開機 Teams 會議室裝置。

您也可以使用遠端 PowerShell 執行腳本。 有關使用遠端 PowerShell 與 Teams 會議室裝置有關的資訊，請參閱 [使用 PowerShell 進行遠端系統管理](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>步驟 3：確認應用程式已成功更新

如果腳本成功執行，裝置會重新開機至 Teams 會議室應用程式。

如果腳本遇到問題，它會指出命令列上的問題，並記錄其輸出至檔案。 請遵循腳本提供的任何指示。 如果您需要與 Microsoft 支援服務聯繫，請務必包含記錄檔案以及支援要求。 腳本會提供記錄檔案的路徑。