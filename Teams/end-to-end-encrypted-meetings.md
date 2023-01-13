---
title: 需要端對端加密才能進行敏感的 Teams 會議
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 瞭解如何啟用 Teams 會議的端對端加密。
ms.openlocfilehash: 091da268e8042707dd7e27094fde33d957a52d79
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800137"
---
# <a name="require-end-to-end-encryption-for-sensitive-teams-meetings"></a>需要端對端加密才能進行敏感的 Teams 會議

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

端對端加密是其原始資訊的加密，其預定目的地的解密功能不需要中繼節點解密。 當 Teams 中的會議是端對端加密時，除了會議中的參與者以外，沒有人能聽到或看到通訊。 任何其他對象 (包括 Microsoft) 都可存取解密後的交談。

當兩方使用最新版 Windows 或 Mac 版 Teams 桌面用戶端、行動裝置上有 iOS 和 Android 的最新更新，或是在使用最新更新的 Windows 裝置上Teams 會議室時，雙方可以進行端對端加密會議。 不支援透過瀏覽器參與的會議端對端加密。

> [!Note]
> 端對端會議加密需要Teams 進階版。

如果您不啟用端對端加密，Teams 仍會根據業界標準使用加密來保護會議。 在會議期間交換的資料在傳輸期間和在休息時一律是安全的。 如需詳細資訊，請參閱 [適用於 Teams 的媒體加密](teams-security-guide.md#media-encryption)。

在端對端加密會議期間，Teams 會保護下列功能：

- 音訊

- 影片

- 共用螢幕

[Microsoft 365 中的加密](/microsoft-365/compliance/encryption) 可保護會議中的聊天、檔案共用、目前狀態和其他內容。 應用程式、虛擬人偶、圖釋、聊天和 Q&A 不會受到端對端加密。

在端對端加密會議期間無法使用下列功能：

- 即時輔助字幕和轉錄

- 錄製

- 共聚模式、小幫手模式、大型圖庫

- 分組會議室

如果貴組織使用合規性記錄，則無法使用端對端加密。 如需 Teams 如何支援合規性錄製的詳細資訊，請參閱 [通話和會議記錄的 Teams 原則型錄製](teams-recording-policy.md)。

## <a name="enable-end-to-end-encryption-for-meetings"></a>啟用會議的端對端加密

根據預設，不會啟用會議的端對端加密。 您可以使用 Teams 系統管理員增強的加密原則來啟用這項功能。

啟用端對端加密後，會議召集人可以選擇端對端加密，然後建立會議。 您也可以使用會議範本或敏感度標籤來強制執行端對端加密。

啟用會議的端對端加密

1. 在 Teams 系統管理中心，選取 **[增強加密原則]**。

1. 選取您要更新的原則。

1. 將 **[端對端會議加密**] 設定為 **[未啟用]，但使用者可以覆寫**。

1. 選取 [儲存 **]**。

## <a name="related-topics"></a>相關主題

[設定具有三層保護層級的 Teams 會議](configure-meetings-three-tiers-protection.md)

[針對端對端 Microsoft Teams 通話使用端對端加密](teams-end-to-end-encryption.md)
