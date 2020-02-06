---
title: 裝置更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft 會定期針對商務用 Skype Phone Edition 發行一組新的裝置固件更新，您可以匯入到伺服器並散佈給使用者。 您可以移至 Microsoft 網站上的 [說明及支援] 頁面，並搜尋 forPhone Edition，以取得最新的裝置更新規則組。下載最新的更新套件，並將檔案解壓縮至電腦上要上傳更新的資料夾。 解壓縮檔案後，接著可以使用 Import-CsDeviceUpdate Cmdlet 匯入解壓縮後之 .CAB 檔案 (其名稱為 UCUpdates.cab) 中的裝置更新規則。 如需詳細資訊，請參閱匯入-CsDeviceUpdate。
ms.openlocfilehash: ad296ebc3b8ade977884a925180dbb3639855f76
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822886"
---
# <a name="device-update"></a>裝置更新

Microsoft 會定期針對商務用 Skype Phone Edition 發行一組新的裝置固件更新，您可以匯入到伺服器並散佈給使用者。 前往 Microsoft 網站的「說明及支援」頁面並搜尋 "Phone Edition" (電話版) 可取得最新的裝置更新規則組合。 下載最新的更新套件，將檔案解壓縮至要上載之更新所在的電腦資料夾內。 解壓縮檔案後，接著可以使用 **Import-CsDeviceUpdate** Cmdlet 匯入解壓縮後之 .CAB 檔案 (其名稱為 UCUpdates.cab) 中的裝置更新規則。 如需詳細資訊，請參閱匯[入-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。

在已匯入裝置更新規則之後，您可以使用 [**裝置更新**] 頁面來查看及管理貴組織裝置的這些規則。

> [!TIP]
> 您可以測試韌體更新，假設測試成功，再接著讓組織中使用的所有相關裝置使用此更新。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可在「裝置更新」**** 頁面上執行下列工作：

- 核准清單中的裝置更新。

- 取消或回復擱置的裝置更新。

- 從清單刪除裝置更新。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- [**編輯**]您可以使用這個選項來執行下列動作：

  - **選取全部**此選項會選取清單中的所有裝置更新。

  - **刪除**這個選項會刪除所有選取的裝置更新。

- **動作**您可以在清單中選取一或多個更新，並執行下列動作：

  - **解除擱置**中的更新這個選項可防止將選取的更新部署到貴組織的裝置上。

  - **核准**這個選項可讓選取的更新部署到貴組織的裝置上。

  - **還原**這個選項可讓先前核准的更新部署到貴組織的裝置上

- **更新**您可以重新整理清單，以驗證所有裝置更新的狀態。

如需裝置更新 Web 服務的詳細資訊，請參閱規劃文件中的〈[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)〉。
## <a name="see-also"></a>另請參閱

[匯入-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
