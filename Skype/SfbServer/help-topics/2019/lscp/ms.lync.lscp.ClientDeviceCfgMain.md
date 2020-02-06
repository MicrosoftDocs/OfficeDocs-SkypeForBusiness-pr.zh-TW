---
title: 裝置記錄組態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
ROBOTS: NOINDEX, NOFOLLOW
description: 裝置更新 Web 服務可自動建立記錄檔，並記錄裝置的更新活動。 在組織的資料管理戰略中，您可能會想要針對記錄資料快取大小、記錄檔案大小，或在清除前的記錄檔案保留時間長度設定門限。 您可以根據組織的需求變更這些設定。 若您不希望裝置更新 Web 服務自動清除記錄檔，也可視需要手動加以清除。 您可以變更全域的記錄檔設定，或針對個別網站進行變更。
ms.openlocfilehash: 43fc784113a81038469099807770945ee2fbcc3b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794552"
---
# <a name="device-log-configuration"></a>裝置記錄組態

裝置更新 Web 服務可自動建立記錄檔，並記錄裝置的更新活動。 在組織的資料管理戰略中，您可能會想要針對記錄資料快取大小、記錄檔案大小，或在清除前的記錄檔案保留時間長度設定門限。 您可以根據組織的需求變更這些設定。 若您不希望裝置更新 Web 服務自動清除記錄檔，也可視需要手動加以清除。 您可以變更全域的記錄檔設定，或針對個別網站進行變更。

> [!NOTE]
> 您也可以設定在一天的時間，讓裝置更新 Web 服務自動刪除超過您設定服務保留記錄檔案之天數的記錄檔案（預設為超過10天的記錄檔案）。 此設定無法使用商務用 Skype Server [控制台] 進行修改。 相反地，您必須使用商務用 Skype Server 管理命令介面。 若要指定當天刪除過期記錄檔的時間，請使用**CsDeviceUpdateConfiguration** Cmdlet 搭配-LogCleanUpTimeOfDay 參數。 如需詳細資訊，請參閱[新 CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。

> [!CAUTION]
> 清除檔案會從檔案系統將檔案永久移除。因此清除檔案後，您便無法復原檔案。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「裝置記錄檔設定」**** 頁面上執行下列工作：

- 針對全域或特定網站或集區，新增裝置記錄檔設定。

- 修改現有裝置記錄檔設定的選項。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- **新增**您可以新增具有下列範圍的新裝置記錄配置：

  - 全域

  - 網站

- [**編輯**]您可以在清單中變更裝置記錄配置的選項。 使用此選項，您可以執行下列動作：

  - **顯示詳細資料**這個選項會開啟一個對話方塊，您可以在其中變更裝置記錄配置的選項。

  - **選取全部**此選項會選取清單中的所有裝置記錄配置。

  - **刪除**這個選項會刪除所有選取的裝置記錄配置。

- **更新**您可以重新整理裝置記錄配置清單，以驗證所有裝置記錄配置選項的狀態。

## <a name="see-also"></a>另請參閱

[Modify Settings for Log Files of Device Update Activity](https://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)
