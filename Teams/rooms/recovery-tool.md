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
localization_priority: Normal
description: 本文討論如何使用 Microsoft Teams 會議室的修復工具，這項工具會用於將過期的系統帶至支援的狀態。
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117491"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a>使用 Microsoft Teams 會議室修復工具

本文討論如何使用 Microsoft Teams 會議室的修復工具，這項工具會用於將過期的系統帶至支援的狀態。 當 Microsoft Teams 會議室主控台顯示「系統設定已過期」錯誤，或在執行按鈕重設出廠還原之前，應先使用 [此工具](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。

## <a name="prerequisites"></a>必要條件

下載最新的 [Microsoft Teams 會議室安裝套件](https://go.microsoft.com/fwlink/?linkid=851168) ，然後解壓縮到 Microsoft Teams 會議室裝置易於訪問的 USB 記憶棒或網路共用。

> [!NOTE]
> 從 MSI 解壓縮檔案有許多方法可以完成。 任何能解壓縮所有檔案並保留其目錄結構的機制都是可接受的。 其中一個方法就是使用命令，其中代表 Microsoft Teams Room 安裝套件的完整路徑，並代表要解壓縮檔案之資料夾 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 的完整路徑。

## <a name="running-the-tool"></a>執行工具

1) 在 Microsoft Teams 會議室裝置上，登錄系統管理員帳戶，然後啟動提升的命令提示。
2) 請從 Microsoft Teams 會議室裝置確認您能夠存取 ，該裝置包含在從 Microsoft Teams 會議室安裝套件中解壓縮的 `RecoveryTool.ps1 file` 檔案中。 您可以在準備先決條件時所使用的網路共用或 USB 磁碟機上找到套件。
3) 執行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。
4) 若要執行出廠還原：
   1. 當腳本提示時，請選取選項 2： **重設**。
   2. 如果 BitLocker 已啟動，請遵循腳本輸出結尾所提供的指示來停用。
   3. 執行出廠還原。
      1. 開啟設定 **應用程式** ，然後選取 & **安全性**
      2. 流覽至修復 **定位** 點。
      3. 在 **重設此電腦** 底下，選取 **開始**
      4. 選取 **移除所有專案**，然後選取下 **一步** 和 **重設**
        > [!WARNING]
        > 如果在 Windows 重設程式期間選取了保留我的檔案 **-** 移除應用程式和設定，但保留您的個人檔案選項，Microsoft Teams 會議室裝置可能會無法使用。 請勿選取此選項。
      5. 系統會重新開機多次。 重設完成後，系統會在 Windows 的 「開箱使用體驗」畫面 (OOBE) 畫面。



## <a name="see-also"></a>另請參閱

[Microsoft Teams 會議室協助](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[管理 Microsoft Teams 會議室](rooms-manage.md)