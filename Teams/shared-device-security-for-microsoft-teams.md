---
title: Microsoft Teams 的安全性指南：在公用電腦上安全地使用 Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 在工作場所中從共用電腦安全地使用 Microsoft Teams 的指導方針。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc886b2783d1398a85e00927a224968d65a9539b
ms.sourcegitcommit: 5c59f9bf5a9477607b378c23fa3c8670930dc428
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2021
ms.locfileid: "53646004"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>在共用電腦上安全地使用 Microsoft Teams

如果可能，*建議* 企業對用戶端裝置使用「零信任」方法，運用裝置管理功能、裝置健康情況檢查和原則強制執行、裝置層級加密及其他安全性功能。

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="零信任的圖片，在藍色圓形中顯示明確驗證、最低權限以及承擔入侵 (零信任原則的核心)。":::

系統管理員可以透過 *堅持* 驗證、最低權限，以及承擔入侵 (即會對使用者和資料造成最低風險動作的標準)，藉此建立非常安全的條件。

> [!TIP]
> 若要更深入檢查零信任原則，請參閱[這些影片](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537)。

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>從共用電腦安全地使用 Microsoft Teams 安全的秘訣

我們意識到此做法可能並非在所有情況下都可行，但安全性系統管理員仍務必遵循從共用電腦或非管理裝置使用 Teams 的指導方針。

應該開發方案，以盡快、盡可能遵守指導方針。

1. 使用作業系統平台安全性功能。
    1. 確保作業系統已設定為透過作業系統提供者安裝自動更新 (若為 Microsoft 系統，可透過 [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq) 來完成此動作)。 
    1. 確保已啟用任何裝置加密功能 (例如 [**bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-overview))，以及用來存取裝置的金鑰受到保護。請注意，大部分新式 [**Windows 10 裝置都支援 bitlocker**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10)。 
    1. 在您的裝置上使用防毒功能，例如 [**Windows Defender**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) 提供的功能。
    1. 強烈建議對系統的每個使用者使用[個別使用者帳戶](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)。
    1. *請勿* 對非系統管理功能 (例如瀏覽網頁、執行 Teams 等) 授與或使用系統管理員權限。

如果不符合上述指導方針，我們建議使用額外的瀏覽器安全性最佳做法：

1. 套用瀏覽器的安全性功能。
    1. 使用私人瀏覽工作階段，將保存到磁碟的資料和歷程記錄最小化。 例如，[在 Microsoft Edge 中使用 inPrivate 瀏覽](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate)、[在 Google Chrome中進行無痕式瀏覽](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en)，或使用您的特定瀏覽器用於私人瀏覽的功能。 
    1. 建議將系統行為變更為 *預設* 採用私人瀏覽。 

2. 瀏覽至並使用 [Teams Web 應用程式](https://teams.microsoft.com) (有時稱為 *Web* 用戶端)，而非可下載的Teams 用戶端。

3. 使用共用系統完成之後，您必須： 
    1. [登出 Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487)。
    1. 關閉所有瀏覽器索引標籤和視窗。
    1. 從裝置登出。

上述項目並非涵蓋所有情況的最佳做法或安全性控制項的完整清單，且可能會在您的環境中採取額外的動作 (例如，如果您有 [Office 365 ATP 方案 1 或 2](/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)，安全性系統管理員可以選擇對 Teams 使用安全連結和安全附件)。不過，這些步驟可做為建立從共用裝置使用 Teams 指導方針的起點。

## <a name="more-information"></a>詳細資訊

[Configuration Manager 中的 Bitlocker](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[Intune 中 Windows 10 的 BitLocker 原則](/mem/intune/protect/encrypt-devices)

[Intune 中的端點安全性](/mem/intune/protect/endpoint-security)

在您的 Windows 安全性中[啟用](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender 防毒軟體，並[執行掃描](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Microsoft Defender 安全性中心文章](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Teams Web 用戶端/Teams Web 應用程式](./get-clients.md#web-client)

[安全性和 Microsoft Teams](./teams-security-guide.md)
