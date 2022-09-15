---
title: 使用Microsoft Teams 會議室修復工具
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文討論如何使用Microsoft Teams 會議室的復原工具，您會使用此工具將過期系統帶入支援的狀態。
ms.openlocfilehash: 70b2d199c4fe13138e2f46fd0b49e95efbd18e9c
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706162"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用Microsoft Teams 會議室修復工具

本文討論如何使用Microsoft Teams 會議室的復原工具，您會使用此工具將過期系統帶入支援的狀態。 當Microsoft Teams 會議室主機顯示「系統設定過期」錯誤，或在執行按鍵重設[原廠還](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)原之前，應該套用此工具。

## <a name="prerequisites"></a>必要條件

下載最新的[Microsoft Teams 會議室安裝套件](https://go.microsoft.com/fwlink/?linkid=851168)，然後將它解壓縮到可供Microsoft Teams 會議室存取的 USB 隨身碟或網路共用。

> [!NOTE]
> 從 MSI 擷取檔案可以透過許多方式完成。 任何擷取所有檔案並保留其目錄結構的機制都是可接受的。 其中一個方法是使用代表Microsoft Teams 會議室安裝套件完整路徑的命令 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` ，並 `PathToTarget` 代表您想要擷取檔案之資料夾的完整路徑。

## <a name="running-the-tool"></a>執行工具

1) 在您的Microsoft Teams 會議室裝置上登入系統管理員帳戶，並啟動提升許可權的命令提示字元。
2) 從Microsoft Teams 會議室裝置確認您是否能夠存取 `RecoveryTool.ps1` 檔案，檔案會包含在從Microsoft Teams 會議室安裝套件解壓縮的檔案中。 您可以在準備先決條件時使用的網路共用或 USB 磁片磁碟機上找到套件。
3) 執行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。
4) 若要執行原廠還原：
   1. 當腳本出現提示時，選取選項 2： **重設**。
   2. 如果 BitLocker 已開啟，請依照腳本輸出結尾處提供的指示來停用它。
   3. 執行原廠還原。
      1. 開啟 **[設定]** 應用程式，然後選 **取 [更新&安全性]**
      2. 流覽至 [ **復原] 索引** 標籤。
      3. 在 **[重設此電腦]** 底下，選 **取 [開始使用]**
      4. 選 **取 [移除所有專案**]，然後選取 [ **下一步** ] 和 **[重設]**
        > [!WARNING]
        > 如果在 Windows 重設程式期間選取 [**保留我的檔案 - 移除應用程式和設定，但保留您的個人檔案**] 選項，Microsoft Teams 會議室裝置就無法使用。 請勿選取此選項。
      5. 系統會重新開機多次。 當重設完成時，系統會在 Windows 的「全新體驗」 (OOBE) 畫面。



## <a name="see-also"></a>另請參閱

[Microsoft Teams 會議室說明](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 會議室](rooms-manage.md)
