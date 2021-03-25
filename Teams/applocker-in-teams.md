---
title: AppLocker 控制項策略
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何使用 AppLocker 應用程式控制項策略啟用 Teams 桌面用戶端應用程式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d6e6040956ba5e5469076b4fbbab337f58268c68
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120845"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft Teams 中的 AppLocker 應用程式控制政策

本文說明如何使用 AppLocker 應用程式控制項策略啟用 Teams 桌面用戶端應用程式。 AppLocker 的使用是專為限制非系統管理使用者執行程式與腳本所設計。 有關 AppLocker 的資訊與指引，請參閱 [什麼是 AppLocker？](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。

使用 AppLocker 啟用 Teams 的流程需要建立 AppLocker 型允許清單策略。 使用群組原則管理軟體和/或使用 Windows PowerShell Cmdlet for AppLocker 建立 (請參閱 [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) 技術參考，以) 。 AppLocker 策略會以 XML 格式儲存，而且可以使用任何文字或 XML 編輯器進行編輯。

## <a name="teams-allow-list-with-applocker"></a>使用 AppLocker 的 Teams 允許清單

AppLocker 規則會整理成規則集合。 AppLocker 規則會適用于目標應用程式，而這些規則是構成 AppLocker 原則的元件。  

若要允許 Teams，建議您使用發行者 [條件規則](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) ，因為所有 Teams 應用程式檔案都是數位簽章。
  
我們不建議使用路徑規則，因為 Teams 安裝目錄是使用者可寫入的。 我們不建議使用雜湊規則，因為每次 Teams 用戶端應用程式更新時，規則必須更新。

由於 Teams 桌面可執行檔是數位簽章，因此發行者條件會根據應用程式的數位簽章和內嵌版本屬性來識別應用程式檔案。 數位簽章包含建立應用程式檔案的公司資訊， (發行者) 。 從二進位資源取得的版本資訊包括檔案屬於其中一部分的產品名稱，以及應用程式檔案的版本號碼。

### <a name="example-of-publisher-condition-rules"></a>發行者條件規則範例

針對 Teams 用戶端應用程式 (所有檔案，所有版本) 新增下列專案至 DLL 規則的可執行&規則：

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>相關主題
[什麼是 AppLocker？](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
[AppLocker 技術參考](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)