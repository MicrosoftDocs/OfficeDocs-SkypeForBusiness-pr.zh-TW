---
title: 使用 Microsoft 團隊會議室恢復工具
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文討論如何使用 Microsoft 團隊聊天室的 [恢復工具]，讓您用來將已過期的系統變成受支援的狀態。
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021721"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft 團隊會議室恢復工具

本文討論如何使用 Microsoft 團隊聊天室的 [恢復工具]，讓您用來將已過期的系統變成受支援的狀態。 當 Microsoft 團隊聊天室主控台顯示「系統組態已過期」錯誤，或在執行推播按鈕重設[factory 還原](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)之前，應該套用此工具。

## <a name="prerequisites"></a>必要條件

下載最新的[Microsoft 團隊聊天室安裝套件](https://go.microsoft.com/fwlink/?linkid=851168)，並將其解壓縮至 Microsoft 團隊聊天室裝置可存取的 USB 記憶棒或網路共用。

> [!NOTE]
> 從 MSI 解壓縮檔案的方式有許多種。 提取所有檔案並保留其目錄結構的任何機制都是可接受的。 其中一個方法是使用命令來 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` 代表 Microsoft 團隊聊天室安裝套件的完整路徑，並代表您想要解壓縮檔案的目標 `PathToTarget` 資料夾的完整路徑。

## <a name="running-the-tool"></a>執行工具

1) 在 Microsoft 團隊聊天室裝置上登入系統管理員帳戶，然後啟動提升的命令提示字元。
2) 從 microsoft 團隊聊天室裝置驗證您可以存取的 Microsoft 小組聊天室裝置 `RecoveryTool.ps1 file` ，該裝置會包含在從 Microsoft 小組聊天室安裝套件提取的檔案中。 您可以在使用網路共用或 USB 磁片磁碟機上的 [準備必備元件] 中找到套件。
3) 執行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。
4) 若要執行工廠還原：
   1. 當腳本出現提示時，選取選項2：**重設**。
   2. 如果 BitLocker 已開啟，請依照腳本輸出末端提供的指示來停用。
   3. 執行 factory 還原。
      1. 開啟 [**設定**] 應用程式，然後選取 [**更新 & 安全性**]
      2. 流覽至 [**恢復**] 索引標籤。
      3. 在 [**重設此電腦**] 底下，選取 [**開始**使用]
      4. 選取 [**移除所有專案**]，**然後選取**[移除 **]** 。
        > [!WARNING]
        > 如果您**保留我的檔案-移除 app 和設定，但**在 Windows 重設程式期間已選取 [保留您的個人檔案] 選項，Microsoft [小組聊天室] 裝置就無法使用。 請勿選取此選項。
      5. 系統會多次重新開機。 重設完成後，系統將會處於 Windows 的「不在盒外體驗」（OOBE）畫面中。



## <a name="see-also"></a>另請參閱

[Microsoft 團隊聊天室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 會議室](rooms-manage.md)
