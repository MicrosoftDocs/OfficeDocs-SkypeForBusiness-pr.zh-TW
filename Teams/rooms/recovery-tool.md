---
title: 使用 Microsoft Teams 會議室修復工具
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
ms.localizationpriority: medium
description: 本文討論如何使用復原工具Microsoft Teams 會議室，您將使用此工具將過期的系統帶至支援的狀態。
ms.openlocfilehash: 8b5f61ef3ebfc1ef08a1db6667159ff97c2cdd78
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597577"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft Teams 會議室修復工具

本文討論如何使用復原工具Microsoft Teams 會議室，您將使用此工具將過期的系統帶至支援的狀態。 當主機顯示「系統Microsoft Teams 會議室已過期」錯誤，或在執行按鈕重設出廠還原之前，應該會使用[此工具](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。

## <a name="prerequisites"></a>必要條件

下載最新的[Microsoft Teams 會議室套件](https://go.microsoft.com/fwlink/?linkid=851168)，然後解壓縮到 USB 記憶棒或可供裝置Microsoft Teams 會議室網路共用。

> [!NOTE]
> 從 MSI 解壓縮檔案有許多方法可以完成。 任何能解壓縮所有檔案並保留其目錄結構的機制都是可接受的。 其中一個方法就是使用命令，其中代表 Microsoft Teams 會議室安裝套件的完整路徑，並代表要解壓縮檔案之資料夾的完整 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 路徑。

## <a name="running-the-tool"></a>執行工具

1) 在裝置上Microsoft Teams 會議室系統管理員帳戶，然後啟動提升的命令提示。
2) 請從Microsoft Teams 會議室裝置確認您能夠存取 ，該裝置包含在從安裝套件Microsoft Teams 會議室 `RecoveryTool.ps1 file` 檔案中。 您可以在準備先決條件時所使用的網路共用或 USB 磁碟機上找到套件。
3) 執行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。
4) 若要執行出廠還原：
   1. 當腳本提示時，請選取選項 2： **重設**。
   2. 如果 BitLocker 已啟動，請遵循腳本輸出結尾所提供的指示來停用。
   3. 執行出廠還原。
      1. 開啟 **設定應用程式**，然後選取 **更新&安全性**
      2. 流覽至修復 **定位** 點。
      3. 在 **重設此電腦** 底下，選取 **開始**
      4. 選取 **移除所有專案**，然後選取下 **一步** 和 **重設**
        > [!WARNING]
        > 如果Microsoft Teams 會議室重設程式期間，選取了保留我的檔案 **-** 移除應用程式與設定，但保留您的個人檔案選項，Windows無法使用。 請勿選取此選項。
      5. 系統會重新開機多次。 重設完成後，系統會位於 OOBE Windows畫面的 「開箱 (」) 畫面。



## <a name="see-also"></a>另請參閱

[Microsoft Teams 會議室協助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 會議室](rooms-manage.md)