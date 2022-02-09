---
title: 裝置記錄組態
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: 裝置更新 Web 服務會自動建立記錄檔，記錄裝置更新活動。 在組織的資料管理原則中，您可能會想要設定記錄檔資料快取大小、記錄檔大小，或在清除記錄檔之前保留的時間長度閾值。 您可以根據組織的需求來變更這些設定。 如果您不想讓裝置更新 Web 服務自動清除記錄檔，您可以視需要手動清除記錄檔。 記錄設定可全域變更或每個網站。
ms.openlocfilehash: d62265e382d87b3d20f0c9ac0fe2a5dca869bfef
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401487"
---
# <a name="device-log-configuration"></a>裝置記錄組態

裝置更新 Web 服務會自動建立記錄檔，記錄裝置更新活動。 在組織的資料管理原則中，您可能會想要設定記錄檔資料快取大小、記錄檔大小，或在清除記錄檔之前保留的時間長度閾值。 您可以根據組織的需求來變更這些設定。 如果您不想讓裝置更新 Web 服務自動清除記錄檔，您可以視需要手動清除記錄檔。 記錄設定可全域變更或每個網站。

> [!NOTE]
> 您也可以設定一天中的哪一天，當您想要讓裝置更新 Web 服務自動刪除舊于您設定服務的記錄檔時，其記錄檔的保留天數會為預設值，即超過10天之舊) 記錄檔的記錄檔 (。 無法使用商務用 Skype Server 控制台] 修改此設定。 相反地，您必須使用商務用 Skype Server 管理命令介面。 若要指定一天中刪除過期記錄檔的時間，請使用 **New-CsDeviceUpdateConfiguration** Cmdlet 搭配-LogCleanUpTimeOfDay 參數。 如需詳細資訊，請參閱 [New-CsDeviceUpdateConfiguration](/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。

> [!CAUTION]
> 永久清除檔案會將檔案從檔案系統中移除。 清除檔案之後，便無法復原。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「 **裝置記錄** 檔設定」頁面上執行下列工作：

- 全域或針對特定網站或集區，新增裝置記錄檔設定。

- 修改現有裝置記錄檔設定的選項。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- **新增功能** 您可以使用下列範圍新增新的裝置記錄檔設定：

  - 全域

  - 網站

- **編輯** 您可以在清單中變更裝置記錄檔設定的選項。 使用此選項，您可以執行下列作業：

  - **顯示詳細資料** 此選項會開啟一個對話方塊，您可以在其中變更裝置記錄檔設定的選項。

  - **全選** 此選項會選取清單中的所有裝置記錄檔設定。

  - **刪除** 此選項會刪除所有選取的裝置記錄檔設定。

- **刷新** 您可以重新整理裝置記錄檔設定清單，以驗證所有裝置記錄檔設定的選項狀態。

## <a name="see-also"></a>另請參閱

[修改裝置更新活動之記錄檔的設定](/previous-versions/office/lync-server-2013/lync-server-2013-modify-settings-for-device-update-log-files)