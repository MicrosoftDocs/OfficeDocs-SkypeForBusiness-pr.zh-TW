---
title: 裝置更新
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 會定期為商務用 Skype 電話 Edition 發行一組新的裝置固件更新，您可以匯入伺服器並將其散佈給使用者。 您可以移至 Microsoft 網站上的 [說明與支援] 頁面，並搜尋 forPhone Edition，以取得最新的裝置更新規則集合。下載最新的更新套件，並將檔案解壓縮至要上傳更新的電腦資料夾。 解壓縮檔案後，接著可以使用 Import-CsDeviceUpdate Cmdlet 匯入解壓縮後之 .CAB 檔案 (其名稱為 UCUpdates.cab) 中的裝置更新規則。 如需詳細資訊，請參閱 Import-CsDeviceUpdate。
ms.openlocfilehash: a670e0b55c0e6f8f61cbe75ef2c51e49b2980787
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585483"
---
# <a name="device-update"></a>裝置更新

Microsoft 會定期為商務用 Skype 電話 Edition 發行一組新的裝置固件更新，您可以匯入伺服器並將其散佈給使用者。 前往 Microsoft 網站的「說明及支援」頁面並搜尋 "Phone Edition" 可取得最新的裝置更新規則組合。 下載最新的更新套件，將檔案解壓縮至要上載之更新所在的電腦資料夾內。 解壓縮檔案後，接著可以使用 **Import-CsDeviceUpdate** Cmdlet 匯入解壓縮後之 .CAB 檔案 (其名稱為 UCUpdates.cab) 中的裝置更新規則。 如需詳細資訊，請參閱 [Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。

在匯入裝置更新規則之後，您可以使用「 **裝置更新** 」頁面，為您組織的裝置查看及管理這些規則。

> [!TIP]
> 您可以測試韌體更新，假設更新成功之後，再接著讓組織中使用的所有相關裝置使用此更新。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可在「裝置更新」頁面上執行下列工作：

- 核准清單中的裝置更新。

- 取消或回復擱置的裝置更新。

- 從清單刪除裝置更新。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- **編輯** 您可以使用此選項執行下列動作：

  - **全選** 此選項會選取清單中的所有裝置更新。

  - **Delete** 此選項會刪除所有選取的裝置更新。

- **動作** 您可以在清單中選取一或多個更新，並採取下列動作：

  - **取消暫** 止的更新此選項可防止選取的更新部署至您組織的裝置。

  - **核准** 此選項允許將選取的更新部署至您組織的裝置。

  - **還原** 此選項允許將先前核准的更新部署至您組織的裝置

- **Refresh** 您可以重新整理清單，以確認所有裝置更新的狀態。

如需裝置更新 Web 服務的詳細資訊，請參閱規劃文件中的＜[View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)＞。
## <a name="see-also"></a>另請參閱

[Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)