---
title: 手動更新 Microsoft 團隊聊天室裝置
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
description: 瞭解如何手動將您的 Microsoft 團隊聊天室裝置更新為特定版本。
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731389"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a>手動更新 Microsoft 團隊聊天室裝置

Microsoft 團隊聊天室 app 是透過 Microsoft Store 發佈。 在夜間維護期間，會自動從 Microsoft Store 安裝應用程式的更新。這是取得更新的建議方法。 不過，在某些情況下，小組機房裝置無法從 Microsoft 網上商店接收更新。 例如，安全性原則可能不允許裝置連線至網際網路，或可能不允許從 Microsoft 網上商店下載 app。 或者，您可能會想要在執行安裝程式之前更新裝置，在此期間無法使用 Microsoft Store。

如果您無法從 Microsoft 網上商店取得更新，您可以使用離線 app 更新 PowerShell 腳本，將團隊機房裝置手動更新為較新版本的團隊聊天室 app。 請依照本文所述的步驟，手動更新您的小組聊天室裝置。

> [!NOTE]
> 這個程式只能更新已安裝 [小組室] app 的小組會議室裝置。 無法用來執行新的安裝。 它也無法用來將應用程式降級至較舊的版本。 若要執行 [團隊聊天室] app 的新安裝，請與您的裝置製造商聯繫，以取得其專用的媒體，或參閱 [準備安裝媒體](console.md#prepare-the-installation-media)。

## <a name="step-1-download-the-offline-app-update-script"></a>步驟1：下載離線 app 更新腳本

首先，請下載最新版本的離線 app 更新腳本。 若要下載腳本，請按一下 <https://go.microsoft.com/fwlink/?linkid=2151817> 。 此腳本將會下載到您裝置上的預設 [下載] 資料夾。

已下載的檔案可能會標示為 Windows 所封鎖。 如果您需要執行腳本而不進行任何互動，您必須解除封鎖腳本。 若要解除封鎖腳本，請執行下列動作：

1. 在檔案資源管理器中以滑鼠右鍵按一下檔案
2. 按一下 [**屬性**]
3. 選取 [**解除封鎖**]
4. 按一下 **[確定]**

若要使用 PowerShell 解除封鎖腳本，請參閱 [解除封鎖](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)檔案。

下載離線 app 更新腳本之後，請將檔案轉接至小組聊天室裝置。 您可以使用 USB 磁片磁碟機或從網路檔案共用（在裝置上為 [系統管理] 模式）存取檔案，以將檔案傳輸到裝置。 請務必注意您在裝置上儲存檔案的位置。

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a>步驟2：執行腳本以更新團隊聊天室應用程式

離線 app 更新腳本需要從提升許可權的命令提示字元執行，而 Skype 使用者 (應用程式所使用的使用者) 仍已登入。 如需如何登入管理員帳戶以在 Skype 使用者仍登入時使用提升的命令提示字元的詳細資訊，請參閱在 [Microsoft 團隊聊天室 app 執行時，切換到 [管理員模式] 並返回 [返回]](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。

請執行下列動作，從提升許可權的命令提示字元執行腳本：

1. 切換到 [管理員模式]
2. 按一下 [開始] 圖示，輸入 **命令提示** 字元，然後選取 [以 **系統管理員身分執行**]
3. 執行下列命令，其中 `<path to script>` 包含腳本的完整路徑和腳本檔案的名稱：

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

例如，如果腳本檔案位於中 `C:\Users\Admin\Downloads` ，而指令檔名是 `MTR-Update-4.5.6.7.ps1` ，請執行下列命令：

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

允許腳本執行。 完成後，腳本會重新開機小組聊天室裝置。

您也可以使用遠端 PowerShell 來執行腳本。 如需有關將遠端 PowerShell 與團隊聊天室裝置結合使用的詳細資訊，請參閱 [使用 PowerShell 進行遠端系統管理](rooms-operations.md#remote-management-using-powershell)。

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a>步驟3：驗證 app 已順利更新

如果腳本順利執行，裝置將會重新開機至 [小組室] app。

如果腳本遇到問題，會在命令列上指出問題，並將其輸出記錄到檔案中。 依照腳本提供的任何指示進行。 如果您需要與 Microsoft 支援人員取得聯繫，請務必將記錄檔與支援要求一起隨附。 此腳本將提供記錄檔的路徑。
