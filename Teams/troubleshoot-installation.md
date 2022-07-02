---
title: 針對 Windows 上的 Microsoft Teams 安裝和更新問題進行疑難排解
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: 瞭解如何針對 Windows 上的 Teams 桌面用戶端應用程式進行安裝和更新問題的疑難排解。
ms.openlocfilehash: d01c67c58a67ab0c52becdd54f0298ec0196704c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605852"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>針對 Windows 上的 Microsoft Teams 安裝和更新問題進行疑難排解

本文提供如何針對在 Windows 上執行的 Teams 桌面用戶端應用程式的安裝和更新問題進行診斷和疑難排解的指導方針。 如需其他疑難排解資訊，請參閱 [Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)。

## <a name="check-whether-teams-is-updated-successfully"></a>檢查 Teams 是否已順利更新

按照這些步驟檢查是否已順利安裝 Teams 更新。

1. 在 Teams 中，選取您個人資料圖片旁邊的省略符號(**...**)，然後點擊 **關於** > **版本**. 將出現橫幅，顯示您目前的 Teams 版本以及上次更新的時間。 例如，**您擁有 Microsoft Teams 版本 1.5.00.3806 (64 位元)-E。它上次更新時間為 2022 年 2 月 16 日**。
2. 再次開啟省略符號功能表，然後點擊 **[檢查更新]**。
3. 等候應用程式上方的橫幅指出需要「重新整理」 Teams。 此程序下載新版 Teams 後大約一分鐘應該會顯示連結。 橫幅也會讓您知道您是否執行最新的版本，如果是，就不需要更新。
4. 按一下橫幅中的重新整理連結。
5. 請等候 Teams 重新啟動，然後重複步驟 1 以查看應用程式是否已更新。

如果您看到失敗訊息，或版本號碼與步驟 4 的相同，表示更新程序失敗。

## <a name="troubleshoot-installation-and-update-issues"></a>安裝和更新問題的疑難排解

### <a name="troubleshoot-installation-issues"></a>安裝問題的疑難排解

Teams 安裝好後，Teams 安裝程式會將事件順序記錄到 `%LocalAppData%\SquirrelTemp\SquirrelSetup.log`。 首先要尋找的是錯誤訊息或位於記錄結尾附近的呼叫堆疊。 請注意，記錄開頭的呼叫堆疊不一定表示安裝有問題。 將您的記錄與成功安裝的記錄 (即使是在另一部電腦上) 做比較，會比較容易看出預期的結果。

如果 `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` 沒有指出原因，或您需要更多疑難排解問題的資訊，請參閱 [收集和分析應用程式與系統記錄](#collect-and-analyze-application-and-system-logs)。

### <a name="troubleshoot-update-issues"></a>更新問題的疑難排解

成功安裝 Teams 後，記錄位置將從 `%LocalAppData%\SquirrelTemp` 切換到 `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`。 另一個興趣記錄檔是 `%AppData%\Microsoft\Teams\logs.txt`。

- `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` 檔案由 `Update.exe` 寫入，這是為 Teams 應用程式提供服務的可執行檔。
- `%AppData%\Microsoft\Teams\logs.txt` 檔案是 Teams 應用程式 (特別是 `Teams.exe`) 用來記錄重大的應用程式事件。 它可能會包含失敗資訊。

這些記錄檔包含個人識別資訊 (PII)，因此不會傳送給 Microsoft。

Teams 可自動啟動更新程序 (取決於原則)，或者使用者可以移至個人資料圖片旁邊的省略符號 (**...**) 功能表，手動檢查更新並選取 **[檢查更新]**。 這兩種方法都使用下列事件順序。

1. **檢查更新**。 Teams 提出 Web 要求，並包括目前的應用程式版本和部署環資訊。 此步驟的目標是取得下載連結。 此步驟的失敗記錄在 `%AppData%\Microsoft\Teams\logs.txt` 中。
2. **下載更新**。 Teams 使用步驟 1 取得的下載連結下載更新。 下載完成後，Teams 會呼叫 `Update.exe` 來暫存下載。 下載失敗也會記錄在 `%AppData%\Microsoft\Teams\logs.txt` 中。
3. **暫存更新**。 下載的內容會由 `Update.exe` 驗證並解壓縮到中閒資料夾 `%LocalAppData%\Microsoft\Teams\stage`。 此步驟的失敗會記錄在 `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` 中。
4. **安裝更新**。 有多種方式可以啟動 Teams。 使用者登入時，系統會自動啟動 Teams，或者您也可以透過快速鍵啟動 Teams。 在此步驟中，`Update.exe` 會檢查是否有暫存資料夾、再次驗證內容，以及執行檔案作業以取消暫存應用程式。 將 `%LocalAppData%\Microsoft\Teams\current` 中的舊應用程式資料夾備份到 `%LocalAppData%\Microsoft\Teams\previous`，並將階段資料夾重新命名為 `current`。 此步驟的失敗會記錄在 `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` 中。

如果 `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` 或 `%AppData%\Microsoft\Teams\logs.txt` 沒有足夠資訊可判斷問題的根本原因，而您需要更多疑難排解問題的資訊，請移至 [收集和分析應用程式與系統記錄](#collect-and-analyze-application-and-system-logs)。

## <a name="collect-and-analyze-application-and-system-logs"></a>收集和分析應用程式記錄與系統記錄

本節將說明如何收集和分析應用程式記錄與系統記錄，以便取得更全面的資訊來進行疑難排解。 您可以使用 Sysinternals 工具來完成這些步驟。 若要深入了解，請參閱 [Windows Sysinternals](/sysinternals/)。

### <a name="collect-logs"></a>收集記錄

1. 下載 [Sysinternals 工具](https://download.sysinternals.com/files/SysinternalsSuite.zip)。
2. 將 zip 檔解壓縮到本機磁碟機的 `%Temp%` 資料夾。
3. 開啟命令提示字元並提升權限，然後執行下列動作：

    1. 執行下列命令以移至您的 `%Temp%` 資料夾：

        ```console
        cd /d %Temp%
        ```

    2. 複製安裝與應用程式記錄。請注意，視失敗點而定，不一定會有其中某些記錄。

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```

    3. 執行下列命令可取得開啟的控制代碼。

        ```console
        handle > handles.txt
        ```

    4. 執行下列命令可取得開啟的 DLL。

        ```console
        listdlls -v Teams > dlls.txt
        ```

    5. 執行下列命令可取得正在執行的驅動程式。

        ```console
        driverquery /v > driverquery.txt
        ```

    6. 執行下列命令可取得 Teams 資料夾的存取控制清單 (ACL)。

        ```console
        icacls %LocalAppData%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>分析記錄 (適用於進階使用者)

失敗的更新會導致無法預期的應用程式行為。 例如，使用者可能無法結束 Teams、擁有的 Teams 版本過舊，或無法啟動 Teams。 如果您在更新期間中遇到問題，請首先從 `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` 尋找原因。 以下是幾種不同類型的更新失敗 (從最常見到最不常見)，以及如何使用記錄分析並進行疑難排解。

#### <a name="unable-to-exit-teams"></a>無法結束 Teams

當 Teams 認為必須將自己更新為較新版本時，就會下載並暫存新的應用程式，然後等待機會在下次電腦閒置時自行重新啟動。 此程序的一個常見問題是，當另一個處理序或某個檔案系統驅動程式鎖住 `Teams.exe` 處理序時，會導致 `Teams.exe` 無法結束。 此時，Teams 應用程式就無法被新下載並暫存的應用程式取代。

疑難排解提示：

- 若要確認這就是您遇到的問題，請結束 Teams (在工作列上以右鍵按一下 Teams，然後按一下 [結束])。 然後在 Windows 中開啟工作管理員，查看 Teams 執行個體是否仍在執行。  
- 如果您不在發生此問題的電腦上，請檢查從發生此問題之電腦處收集的 `%LocalAppData%\SquirrelTemp\SquirrelSetup.log`，並尋找 **Program: Unable to terminate the process in the log (程式: 無法終止記錄中的處理程序)**。
- 要確定阻止 `Teams.exe` 結束的原因，請查看在 [收集記錄](#collect-logs) 區段中建立的 `Dlls.txt` 和 `Handles.txt` 記錄。 這些記錄會告訴您導致 Teams 無法結束的處理程序。
- 導致 Teams 無法結束的另一個可能原因是核心模式檔案系統篩選器驅動程式。 您可以使用 SysInternals 工具 [ProcDump](/sysinternals/downloads/procdump)，執行 `procdump -mk <pid>` (其中 \<pid> 是從工作管理員取得的處理程序識別碼) 收集核心模式處理程序傾印。 您也可以檢查 `Driverquery.txt` 記錄檔，查看可能干擾 Teams 的作用中篩選器驅動程式。
- 若要從此狀態復原，請重新啟動電腦。

#### <a name="file-permissions"></a>檔案權限

在整個安裝和更新程序中，Teams 會在使用者設定檔中建立許多子資料夾和檔案。 由於應用程式和更新程式是以非提升權限的使用者身份執行，因此必須對下列資料夾授與讀取和寫入權限：

|資料夾  |使用者  |
|---------|---------|
|`%LocalAppData%\SquirrelTemp`    | 在安裝階段，Teams 安裝程式 (例如，`Teams_Windows_x64.exe`)        |
|`%LocalAppData%\Microsoft\Teams`  | Teams 更新程式 (`Update.exe`) 在更新程序中用來擷取並暫存應用程式套件        |
|`%AppData%\Microsoft\Teams`   |  Teams 應用程式 (`Teams.exe`) 用來儲存設定、應用程式狀態和 (預先暫存的) 已下載更新套件       |

如果 Teams 因為無法寫入檔案而遭到拒絕存取，另一個軟體應用程式可能會產生干擾，或者安全性描述元項目可能會限制資料夾的寫入存取權。

疑難排解提示：

- 在 `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` 或 `%AppData%\Microsoft\Teams\logs.txt` 中尋找 `access denied` 證據。 檢查這些檔案，查看是否曾經嘗試寫入檔案但失敗。
- 開啟 `Icacls.txt`，尋找由非系統管理員的使用者封鎖寫入作業的有效存取控制項目 (ACE)。這通常會在其中一個 DACL 項目中。 如需詳細資訊，請參閱 [icacls 文件](/windows-server/administration/windows-commands/icacls)。

#### <a name="file-corrupted"></a>檔案損毀

在某些情況下，加密軟體可以變更 `%LocalAppData%\Microsoft\Teams` 資料夾中的檔案，這可能會導致 Teams 無法啟動。 即使應用程式沒有更新，也可能會發生這個問題。 當檔案損毀時，從此狀態復原的唯一方法是解除安裝 Teams 後再重新安裝。

> [!NOTE]
> 如果您無法使用上述任何步驟判斷問題的根源，您可以嘗試使用 [Process Monitor](/sysinternals/downloads/procmon) 工作階段。 Process Monitor 是一種 Sysinternals 工具，可記錄對登錄和檔案系統的存取。

## <a name="related-topics"></a>相關主題

- [取得 Microsoft Teams 用戶端](get-clients.md)
- [Teams 用戶端更新](teams-client-update.md)
- [Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)
