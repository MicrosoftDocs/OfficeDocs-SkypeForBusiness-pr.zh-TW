---
title: 用戶端版本配置建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
ROBOTS: NOINDEX, NOFOLLOW
description: 用戶端版本設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會與商務用 Skype Server 一起安裝, 並用於針對整個伺服器部署啟用或停用用戶端版本控制。 啟用全域設定時，任何既有的用戶端版本原則都會在使用者嘗試登入時生效。 若不想要執行用戶端版本控制，可以停用全域用戶端版本設定。
ms.openlocfilehash: 54a7929f91e4e944cbe431ae7a0193c50a12cfbd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193241"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>用戶端版本組態：建立新的或編輯現有

用戶端版本設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會與商務用 Skype Server 一起安裝, 並用於針對整個伺服器部署啟用或停用用戶端版本控制。 啟用全域設定時，任何既有的用戶端版本原則都會在使用者嘗試登入時生效。 若不想要執行用戶端版本控制，可以停用全域用戶端版本設定。

您也可以建立網站專用的用戶端版本設定，讓您能夠依網站啟用或停用用戶端版本控制。網站專用的設定優先於全域設定。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在 [新增用戶端版本設定] **** 或 [編輯用戶端版本設定] **** 頁面上執行下列工作：

- 新增或修改用戶端版本設定的名稱。

- 啟用或停用全域或特定網站的用戶端版本控制。

- 新增或修改用戶端版本設定的預設動作。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- **範圍**識別用戶端版本配置的範圍 (全域或網站)。

- **名稱**您可以新增或修改用戶端版本配置的名稱。

- **啟用版本控制**您可以在全域或針對網站啟用或停用用戶端版本控制, 視設定的範圍而定。

- **預設動作**當使用者嘗試使用沒有特定用戶端版本原則的用戶端應用程式登入時, 您可以選取要套用的預設動作。 您有下列選項:

  - **允許**如果用戶端版本與用戶端版本原則清單中的任何篩選器都不相符, 則允許用戶端登入。

  - **封鎖**如果用戶端版本與用戶端版本原則清單中的任何篩選器都不相符, 則可防止用戶端登入。

  - **使用 URL 的封鎖**如果用戶端版本與用戶端版本原則清單中的任何篩選器都不相符, 就會防止用戶端登入, 並包含一則錯誤訊息, 其中包含可下載較新用戶端的 URL。

  - **允許 URL**如果用戶端版本與用戶端版本原則清單中的任何篩選器都不相符, 則允許用戶端登入, 並包含一則錯誤訊息, 其中包含可下載較新用戶端的 URL。

  - **URL**如果您選取 [封鎖], 並選取 [**以 url**或**允許使用 url**], 您可以指定要包含在錯誤訊息中的用戶端下載 URL。

如需用戶端與用戶端版本之間的互通性詳細資料, 請參閱規劃檔中的[用戶端互用性](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。 如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的〈[Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)〉。

