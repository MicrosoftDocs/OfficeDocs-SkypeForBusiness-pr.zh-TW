---
title: 針對 Windows 上的 Microsoft 團隊安裝和更新問題進行疑難排解
author: lanachin
ms.author: v-lanac
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何針對 Windows 上的小組桌面用戶端應用程式的安裝與更新問題進行疑難排解。
ms.openlocfilehash: f47edf351d6a55f57977fee823d670b749896049
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837623"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>針對 Windows 上的 Microsoft 團隊安裝和更新問題進行疑難排解

本文提供如何診斷和疑難排解 Windows 上執行之小組桌面用戶端應用程式的安裝與更新問題的指導方針。

## <a name="check-whether-teams-is-updated-successfully"></a>檢查團隊是否已順利更新

請依照下列步驟檢查是否已成功安裝團隊更新。

1. 在 [團隊] 中，選取您的個人檔案圖片，然後按一下 [**關於** > **版本**]。
2. 在相同的功能表上，按一下 [**檢查更新**]。
3. 請等候應用程式頂端的橫幅，指出需要小組的 [重新整理]。 此程式會在此程式下載新的團隊版本之後，大約一分鐘就會顯示該連結。 [橫幅] 也會讓您知道是否已執行最新版本（在這種情況下），不需要進行任何更新。
4. 按一下橫幅中的 [重新整理] 連結。
5. 等到小組重新開機之後，再重複步驟1，查看應用程式是否已更新。

如果您看到失敗訊息，或版本號碼與步驟4中的相同，則更新程式失敗。

## <a name="troubleshoot-installation-and-update-issues"></a>安裝和更新問題疑難排解

### <a name="troubleshoot-installation-issues"></a>疑難排解安裝問題

安裝團隊後，小組安裝程式會將事件順序記錄到%LocalAppData%\SquirrelTemp\SquirrelSetup.log。 您要尋找的第一件事是在記錄結尾附近出現錯誤訊息或呼叫堆疊。 請注意，記錄開頭的呼叫堆疊可能並不表示存在安裝問題。 您可以更輕鬆地將記錄與記錄（即使在另一部電腦上）進行比較，以查看預期情況。

如果 SquirrelSetup 沒有指出原因，或者您需要進一步的資訊來排查問題，請參閱[收集及分析應用程式和系統記錄](#collect-and-analyze-application-and-system-logs)。

### <a name="troubleshoot-update-issues"></a>疑難排解更新問題

成功安裝團隊後，日誌位置會從%LocalAppData%\SquirrelTemp 切換為%AppData%\Microsoft\Teams。 在這個位置，有兩個 SquirrelSetup 記錄檔案： [感興趣]、[記錄] 和 [記錄 .txt]。

- 此位置的 SquirrelSetup 檔案是由 update.exe 所撰寫，後者是一個可供使用團隊 app 的可執行檔。
- [小組] 應用程式（特別是 "團隊 .exe]）會使用 [Logs] （記錄 .txt）來記錄重要的應用程式事件。 它可能會包含失敗資訊。

這些記錄檔包含個人可識別資訊（PII），因此不會傳送給 Microsoft。

小組可以自動啟動更新程式（視原則而定），或者，使用者可以移至他們的個人檔案圖片 >**檢查更新**，以手動檢查更新。 這兩種方法都使用下列事件順序。

1. **檢查更新**。 小組提出 web 要求，並包含目前的 app 版本和部署鈴聲資訊。 此步驟的目標是取得下載連結。 此步驟的失敗會記錄在 Logs 中。
2. **下載更新**。 團隊會使用從步驟1取得的下載連結來下載更新。 下載完成後，小組會呼叫 update.exe 來暫存下載。 您也會在 [readme.txt] 中記錄下載失敗。
3. **暫存更新**。 已下載的內容會驗證並解壓縮至中間資料夾（%LocalAppData%\Microsoft\Teams\stage），這是由 update.exe 完成。 此步驟的失敗會記錄在 SquirrelTemp 中。
4. **安裝更新**。 有多種方式可開始團隊。 當使用者登入時，系統會自動啟動小組，或者您可以透過快速鍵啟動團隊。 在這個步驟中，update.exe 會檢查暫存資料夾是否存在、再次驗證內容，並執行檔案作業來取消階段 app。 %LocalAppData%\Microsoft\Teams\current 中的舊應用程式資料夾會備份到%LocalAppData%\Microsoft\Teams\previous，而階段資料夾會重新命名為「目前」。 此步驟的失敗會記錄在 SquirrelTemp 中。

如果 SquirrelTemp 或 Logs 沒有足夠的資訊來判斷基本原因，而您需要更多的資訊來排查問題，請移至[收集及分析應用程式和系統記錄](#collect-and-analyze-application-and-system-logs)。

## <a name="collect-and-analyze-application-and-system-logs"></a>收集及分析應用程式與系統記錄

本節說明如何收集及分析應用程式和系統記錄，以取得更完整的資訊來排查問題。 您將會使用 Sysinternals 工具來完成這些步驟。 若要深入瞭解，請參閱[Windows Sysinternals](https://docs.microsoft.com/sysinternals/)。

### <a name="collect-logs"></a>收集記錄

1. 下載[Sysinternals 工具](https://download.sysinternals.com/files/SysinternalsSuite.zip)。
2. 將 zip 檔案解壓縮至本機磁片磁碟機上的% TEMP% 資料夾。
3. 開啟提升許可權的命令提示字元，然後執行下列動作：

    1. 執行下列動作，移至您的 TEMP 資料夾：

        ```
        cd /d %TEMP%
        ```
    2. 複製設定和應用程式記錄。 請注意，根據失敗的點，可能不會顯示部分記錄。

        ```
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. 執行下列動作來捕獲開啟的控點。

        ```
        handle > handles.txt
        ```

    4. 執行下列動作來捕獲開啟的 Dll。

        ```
        listdlls -v Teams > dlls.txt
        ```
    5. 執行下列動作來捕獲正在執行的驅動程式。

        ```
        driverquery /v > driverquery.txt
        ```

    6. 執行下列動作來捕獲 [小組] 資料夾的存取控制清單（Acl）。

        ``` 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>分析記錄（適用于高級使用者）

失敗的更新可能會導致無法預測的 app 行為。 例如，使用者可能無法結束團隊、擁有陳舊的團隊版本，或是無法啟動團隊。 如果您在更新期間遇到問題，我們首先要尋找的位置是 SquirrelTemp 記錄。 以下是不同類型的更新失敗（從最常見到最常見），以及如何使用記錄進行分析和疑難排解。

#### <a name="unable-to-exit-teams"></a>無法結束團隊

當團隊認為需要將本身更新為較新的版本時，它會下載並階段新的應用程式，然後在下次電腦空閒時等待商機自行重新開機。 這個程式的常見問題是，另一個進程或檔案系統驅動程式鎖定了團隊 .exe 進程，這會使球隊無法退出。 因此，新下載和暫存的應用程式無法取代團隊 app。

疑難排解秘訣：

- 若要確認是否為您遇到的問題，請結束小組（在工作列上按一下 [小組]，然後按一下 [結束 **]）。** 然後，在 Windows 中開啟 [工作管理員]，查看團隊的實例是否仍在執行。  
- 如果您不在遇到此問題的電腦上，請檢查從遇到此問題的電腦收集的 SquirrelTemp，並尋找「程式：無法終止記錄中的進程」專案。
- 若要判斷禁止團隊成員退出，請查看 Dll 並處理 .txt 記錄。 這些程式會告訴您禁止小組退出的進程。
- 可防止團隊退出的另一個原因是核心模式檔案系統篩選驅動程式。 您可以使用 SysInternals 工具（ [ProcDump](https://docs.microsoft.com/sysinternals/downloads/procdump)）來透過執行來收集核心模式進程轉儲```procdump -mk <pid>```，其中<pid> ，其中是從工作管理員取得的進程 ID。 您也可以檢查 Driverquery 記錄檔，以查看可能會干擾小組的活動篩選驅動程式。
- 若要從這種狀態復原，請重新開機電腦。

#### <a name="file-permissions"></a>檔案許可權

小組會在整個安裝和更新程式中，在使用者的設定檔中建立許多子資料夾和檔案。 因為應用程式和更新程式是以非提升的使用者身分執行，所以必須在下列資料夾上授予讀取和寫入權限：

|資料夾  |消費者  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | 在安裝階段中的團隊安裝程式（例如 Teams_Windows_x64 .exe）        |
|%LocalAppData%\Microsoft\Teams  | 小組更新程式（更新 .exe），以在更新程式期間提取並暫存應用程式套件        |
|%AppData%\Microsoft\Teams   |  [小組] app （團隊 .exe）來儲存設定、應用程式狀態及（預先暫存的）已下載的更新套件       |

如果團隊由於無法寫入檔案而遭到拒絕存取，可能會有另一個軟體應用程式受到干擾，或安全性描述項專案可能會限制對資料夾的寫入權。

疑難排解秘訣：

- 在 SquirrelTemp 或 Logs 中尋找「拒絕存取」證據。 檢查這些檔案，查看是否有人嘗試寫入失敗的檔案。
- 開啟 Icacls，並尋找有效的存取控制專案（ACE）來封鎖由非管理員的使用者寫入作業。這通常是在其中一個 DACL 專案中。 如需詳細資訊，請參閱[icacls 檔](https://docs.microsoft.com/windows-server/administration/windows-commands/icacls)。

#### <a name="file-corrupted"></a>檔損毀

在某些情況下，加密軟體可以變更%LocalAppData%\Microsoft\Teams 資料夾中的檔案，這可以避免小組的啟動。 即使沒有更新應用程式，也可能會發生這種情況。 遺憾的是，當檔案損毀時，從這種狀態復原的唯一方式就是卸載並重新安裝小組。

> [!NOTE]
> 如果您無法使用上述任何步驟來判斷問題的根本原因，您可能會想要嘗試[進程監視器](https://docs.microsoft.com/sysinternals/downloads/procmon)會話。 [進程監視器] 是一種 Sysinternals 工具，可記錄對註冊表和檔案系統的存取權。

## <a name="related-topics"></a>相關主題

- [取得 Teams 用戶端](get-clients.md)
- [Teams 用戶端更新](teams-client-update.md)