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
- Teams_ITAdmin_Rooms
description: 瞭解如何手動將Microsoft Teams 會議室裝置更新為特定版本。
ms.openlocfilehash: c3128f5b909901da0eb5578f1586aaad785b49a6
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267638"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>手動更新Microsoft Teams 會議室裝置

Microsoft Teams 會議室應用程式會透過 Microsoft Store 散發。 更新應用程式會在夜間維護期間自動從 Microsoft Store 安裝;這是取得更新的建議方法。 不過，在某些情況下，Teams 會議室裝置無法從 Microsoft Store 接收更新。 例如，安全性原則可能不允許裝置連線到網際網路，或可能不允許從 Microsoft Store 下載應用程式。 或者，您可能會想要在執行設定之前更新裝置，而在該裝置上無法使用 Microsoft Store。

如果您無法從 Microsoft Store 取得更新，您可以使用離線應用程式更新 PowerShell 腳本，將您的Teams 會議室裝置手動更新為較新版本的 Teams 會議室 應用程式。 請依照本文中的步驟手動更新您的Teams 會議室裝置。

> [!NOTE]
> 此程式只能使用已安裝Teams 會議室應用程式來更新Teams 會議室裝置。 它無法用來執行新的安裝。 也無法用來將應用程式降級為較舊的版本。 若要執行Teams 會議室應用程式的新安裝，請連絡您裝置的製造商，瞭解其特定媒體。

## <a name="step-1-download-the-offline-app-update-script"></a>步驟 1：下載離線應用程式更新腳本

首先，下載最新版本的離線應用程式更新腳本。 若要下載腳本，請按一下 <https://go.microsoft.com/fwlink/?linkid=2151817> 。 腳本將會下載到您裝置上的預設下載資料夾。

下載的檔案可能會被 Windows 標示為已封鎖。 如果您需要執行腳本而不進行任何互動，您將需要解除封鎖腳本。 若要解除封鎖腳本，請執行下列動作：

1. 以滑鼠右鍵按一下 檔案總管 中的檔案
2. 按一下 **[內容]**
3. 選取 **[解除封鎖]**
4. 按一下 **[確定]**

若要使用 PowerShell 解除封鎖腳本，請參閱 [解除封鎖檔案](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。

下載離線應用程式更新腳本之後，將檔案傳輸到Teams 會議室裝置。 您可以使用 USB 磁片磁碟機或在裝置上以管理員模式存取網路檔案共用中的檔案，將檔案傳輸到裝置。 請務必記下您在裝置上儲存檔案的位置。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>步驟 2：執行腳本以更新Teams 會議室應用程式

離線應用程式更新腳本必須從提升許可權的命令提示字元執行，而 Skype 使用者 (應用程式執行的使用者) 仍然登入。 如需有關如何在 Skype 使用者仍然登入時登入系統管理員帳戶以使用提升許可權的命令提示字元的詳細資訊，請參閱切換[到管理員模式，並在Microsoft Teams 會議室應用程式當機時返回](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-crashes)。

請執行下列動作，從提升許可權的命令提示字元執行腳本：

1. 切換至管理員模式
2. 按一下 [開始] 圖示，輸入 **命令提示字元**，然後選 **取 [以系統管理員身分執行]**
3. 執行下列命令，其中 `<path to script>` 包含腳本的完整路徑和腳本檔案的名稱：

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

例如，如果腳本檔案位於 `C:\Users\Admin\Downloads` ，且指令檔名為 `MTR-Update-4.5.6.7.ps1` ，請執行下列命令：

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

允許執行腳本。 完成後，腳本會將Teams 會議室裝置重新開機。

您也可以使用遠端 PowerShell 執行腳本。 如需有關搭配Teams 會議室裝置使用遠端 PowerShell 的詳細資訊，請參閱[使用 PowerShell 進行遠端系統管理](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>步驟 3：確認應用程式已成功更新

如果腳本順利執行，裝置將會重新開機至Teams 會議室應用程式。

如果腳本發生問題，它會指出命令列上的問題，並將輸出記錄在檔案中。 依照腳本提供的任何指示操作。 如果您需要連絡Microsoft 支援服務，請務必在支援要求中包含記錄檔。 腳本會為您提供記錄檔的路徑。
