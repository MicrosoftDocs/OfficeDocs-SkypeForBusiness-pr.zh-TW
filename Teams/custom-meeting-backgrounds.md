---
title: Teams 會議的自訂會議背景
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.localizationpriority: medium
search.appverid: MET150
description: 使用經核准的公司資產，例如背景，為組織內的 Teams 會議建立自訂背景。
ms.openlocfilehash: f274165a24db2988cb95ad5900220168d0d60fdc
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800226"
---
# <a name="custom-meeting-backgrounds-for-teams-meetings"></a>Teams 會議的自訂會議背景

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

## <a name="overview"></a>概觀

Teams 會議中的自訂功能可讓組織在整個會議體驗中擴展其視覺身分識別。 使用自訂的會議背景有助於促進內部企業文化，並提高內部和外部會議參與者的整體品牌意識。 在組織品牌管理和公司通訊小組的協助下，系統管理員可以輕鬆地為單一租使用者內的各種業務單位和部門，設定和建立自訂會議背景。

根據預設，身為系統管理員或已獲指派會議自訂原則的 Teams 進階授權使用者可以建立具有自訂會議背景的會議。 這些自訂背景僅供您組織內擁有Teams 進階版授權的使用者使用。

## <a name="prerequisites"></a>必要條件

在設定 Teams 會議的自訂會議背景之前，請先檢查以確認您有下列專案：

- 存取 Teams 進階版 SKU
- 您是具有 Teams 系統管理中心存取權的系統管理員，或您已獲指派自訂原則
- 您已啟用 [自訂背景原則](#enabling-the-custom-background-policy)
- 您的背景影像符合 [必要的規格](#adding-custom-background-images)

## <a name="setting-up-custom-meeting-backgrounds"></a>設定自訂會議背景

系統管理員可以在 Teams 系統管理中心上傳及管理 Teams 會議的自訂會議背景。

### <a name="enabling-the-custom-background-policy"></a>啟用自訂背景原則

身為系統管理員，若要建立自訂背景，您必須建立新的會議自訂原則或修改組織的全域預設原則。
若要啟用自訂背景原則，系統管理員將執行下列步驟：

1. 開啟 Teams 系統管理中心
2. 從功能窗格選取 **[會議** ]
3. 在 [會議] 底下，有兩種方式可以存取自訂背景原則。 您可以選取 **[自訂原則** ] 來選取現有原則或建立新原則。 或者，您可以選取 **[會議原則** ]，然後選取右上角的 [ **自訂會議影像** ] 按鈕。
4. 在您所選的原則中，流覽至 [ **自訂會議背景]** 區段
5. 將 **[自訂背景** ] 設定從關閉切換為開啟以啟用設定
6. 選取 **[儲存]**

### <a name="adding-custom-background-images"></a>新增自訂背景影像

現在您已啟用自訂背景原則，可以上傳自訂背景影像。 這些影像會顯示在使用者的介面上，依照上傳時的排序。

上傳必須遵守下列參數。 系統管理員可以上傳：

- PNG 和 JPEG 影像的影像格式
- 最小尺寸為 360 px X 360 px 的影像
- 最小尺寸為 3840 px X 2160 px 的影像
- 最多 50 個自訂背景影像

若要上傳影像，請流覽至 **[會議**  >  **自訂原則**]，然後從上一個步驟選取您的原則。 向下捲動至 [ **自訂會議背景** ] 區段，並在含有自訂背景切換開關的表格底下，選取 **[+新增]**。 選取 [+新增] 後，會開啟一個名為 **[管理背景] 的** 窗格，讓您能夠新增影像。

> [!NOTE]
> 只有擁有Teams 進階版授權的使用者才會在他們的 [背景設定] 面板中看到這些影像。

### <a name="saving-custom-background-images"></a>儲存自訂背景影像

您可以在 [ **自訂會議背景** ] 區段下的新資料表中找到上傳影像的預覽。 此表格也會顯示影像的名稱和解析度。 確認您選擇上傳的影像後，請選取預覽表格下方的 [儲存 **] 按鈕。** 現在您已選取 [儲存]，擁有Teams 進階版授權的使用者就能看到您上傳的背景。

## <a name="where-are-custom-backgrounds-visible"></a>可看見自訂背景的位置

下列清單顯示可看見自訂背景的支援用戶端：

- Web 用戶端
- 桌面版用戶端
- Android
- iOS

### <a name="who-can-select-and-apply-custom-meeting-backgrounds"></a>誰可以選取並套用自訂會議背景

只有Teams 進階版授權的使用者可以在其 [背景設定] 面板中使用會議背景。

> [!NOTE]
> 外部或匿名使用者無法使用自訂會議背景。

### <a name="who-can-view-custom-meeting-backgrounds"></a>誰可以檢視自訂會議背景

雖然只有授權的使用者可以選取他們所選擇的上傳背景，但任何人都可以檢視已套用至會議的背景。 這些使用者包括：

- 租使用者Teams 進階版授權使用者
- 租使用者中未授權的使用者
- 外部使用者
- 匿名使用者
