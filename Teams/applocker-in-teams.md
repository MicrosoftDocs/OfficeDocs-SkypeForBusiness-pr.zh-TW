---
title: AppLocker 控制原則
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何啟用 AppLocker 應用程式控制原則的小組桌面用戶端應用程式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3bcb75eb28730b4387ebcee0be869f1f91cc31c5
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137423"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Microsoft 團隊中的 AppLocker 應用程式控制原則

本文說明如何使用 AppLocker 應用程式控制策略來啟用團隊桌面用戶端應用程式。 AppLocker 的用途是專門用來限制非系統管理使用者的程式及腳本執行。 如需有關 AppLocker 的詳細資訊和指導方針，請參閱[什麼是 applocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)。

啟用具有 AppLocker 的團隊的程式需要建立 AppLocker whitelisting 原則。 原則是使用群組原則管理軟體及/或用於 AppLocker 的 Windows PowerShell Cmdlet 來建立（請參閱[AppLocker 技術參考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)以取得詳細資訊）。 AppLocker 原則會儲存為 XML 格式，而且可以使用任何文字或 XML 編輯器進行編輯。

## <a name="teams-whitelisting-with-applocker"></a>與 AppLocker whitelisting 的團隊

AppLocker 規則會組織成集合規則。 AppLocker 規則會套用至目標應用程式，而它們是組成 AppLocker 原則的元件。  

若要使用白名單小組，我們建議您使用[發行者條件規則](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker)，因為所有團隊應用程式檔案都經過數位簽章。
  
我們不建議使用路徑規則，因為小組安裝目錄是使用者可寫入的。 我們也不建議使用雜湊規則，因為每次更新團隊用戶端應用程式時，都會需要更新規則。

由於團隊桌面可執行檔是經過數位簽章，所以發行者條件會根據其數位簽章和內嵌版本屬性來識別應用程式檔。 數位簽章包含建立應用程式檔案（發行者）之公司的相關資訊。 從二進位資源取得的版本資訊，包括該檔案所屬的產品名稱，以及應用程式檔案的版本號碼。

### <a name="example-of-publisher-condition-rules"></a>Publisher 條件規則範例

對於團隊用戶端應用程式（所有檔案，所有版本），請將下列專案新增至可執行檔規則 & DLL 規則：

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>相關主題
[什麼是 AppLocker？](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)
 [AppLocker 技術參考](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
