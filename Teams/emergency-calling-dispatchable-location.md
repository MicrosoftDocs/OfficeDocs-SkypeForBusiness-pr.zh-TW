---
title: 遠端位置的緊急位址
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 瞭解 Microsoft 如何支援可調度的位置資訊以支援緊急通話。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9efa5f6e9ad5b5f2434efb95265f58c9a603fdd5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272068"
---
# <a name="emergency-addresses-for-remote-locations"></a>遠端位置的緊急位址

本文將說明 Microsoft 支援美國中的 911 緊急通話位置資訊。 此支援可確保為進行緊急通話的 Teams 使用者提供最精確的可分派位置資訊。 無論來電者的位置為何，無論是在網站上或是在家工作，來電者的位置資訊傳送到 [安全接聽點] (PSAP) 都必須正確無誤。

本文包含 Microsoft 遵守 RAY BAUM 的多行電話系統法 (MLTS) 的相關資訊。 RAY BAUM'S Act 會延伸在 2021 年初生效的 Kari's Law 要求。 如需有關 RAY BAUM 法案和 Kari's Law 的詳細資訊，請參閱 [適用于 911 通話](https://www.fcc.gov/911-dispatchable-location) 和 [多線電話系統的可分派位置 – Kari 的法律和 RAY BAUM 的 911 直接撥號、通知和可派派位置需求](https://www.fcc.gov/mlts-911-requirements)。 

如果適用，在家工作的使用者現在可以設定自己的緊急位址。 本文說明如何設定使用者原則，讓使用者可以設定他們的緊急位址。

雖然這項資訊適用于美國中的緊急 911 通話，使用者輸入的位置也會傳送至加拿大的篩選中心。

本文包含下列各節：

- [支援緊急通話位置資訊](#support-for-emergency-calling-location-information)
- [位置優先順序](#location-precedence)
- [緊急位址分類和路由](#emergency-address-classification-and-routing)
- [讓使用者能夠設定其緊急位址](#enable-end-users-to-configure-their-emergency-address)
- [附注和限制](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>支援緊急通話位置資訊

為了支援這些需求，如果系統管理員或使用者授與許可權，Teams 會使用個別作業系統所提供的位置服務來建議位址。 使用者可以確認建議位址的位置、進行編輯，或手動輸入新位址。 系統會將已確認、編輯或手動輸入的位址儲存在 Teams 用戶端，這樣當用戶端連線到該網路時，就會自動使用使用者確認的位址。 當 Teams 用戶端登出時，系統會自動清除使用者儲存的位址。


## <a name="location-precedence"></a>位置優先順序

Teams 的緊急位址可依不同類型分類。 下列清單顯示撥打緊急號碼時所使用的位置優先順序：

1. 由位置資訊服務中的租使用者管理者定義的動態取得位址。

2. 使用者確認、編輯或手動輸入且與 Teams 用戶端連線的區域網路相關聯的位址。

3. 作業系統自動建議的位址。

4. 系統管理員以靜態方式指派給使用者的位址。


## <a name="emergency-address-classification-and-routing"></a>緊急位址分類和路由

下表顯示每種類型的緊急網址類別型以及相關聯的路由方法：通話是自動路由至送達 PSAP，還是在轉接至送達 PSAP 之前經過篩選以取得正確性。 美國支援此路由行為給所有通話方案使用者、運算子連線合作夥伴和直接路由認證的緊急電話服務提供者。


| 緊急網址類別型 | 緊急路由方法 |
| :------------| :-------|
| 由系統管理員定義的動態取得緊急位址。 | 直接前往 PSAP。 |
| 從作業系統取得的緊急位址 **，但未確認使用者的正確性** 。 | 已篩選並移轉至 PSAP。 |
| 從作業系統取得的緊急位址 **，並確認使用者的正確性** 。| 直接前往 PSAP。 |
| 從作業系統取得的緊急位址，並由使用者編輯並確認。 | 已篩選並移轉至 PSAP。 |
| 使用者輸入並確認緊急位址。 | 已篩選並移轉至 PSAP。 |
| 以靜態方式指派給使用者/號碼的緊急位址。 | 已篩選並移轉至 PSAP。 |
| 空 | 已篩選並移轉至 PSAP。 |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>讓使用者能夠設定其緊急位址

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **語音**  >  **緊急原則**。
2. 選取 [新增 **]**。
3. 輸入緊急通話原則的名稱，例如「E911WFH」。
4. 開啟 **外部位置查閱模式**。
5. 選取 [ **套用]**。

#### <a name="assign-a-custom-emergency-calling-policy-to-users"></a>指派自訂緊急通話原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="using-powershell"></a>使用 PowerShell

若要為您的使用者啟用此功能，請使用 New-CsTeamsEmergencyCallingPolicy PowerShell Cmdlet，並將 ExternalLocationLookupMode 參數設定為 [啟用]。 請參閱下列範例： 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

為使用者啟用此功能後，使用者可從 [通話] 索引標籤新增、編輯或確認緊急位址，並在設定後顯示位址。 如需使用者如何設定定位服務的詳細資訊，請參閱 [從家用緊急版 911 工作：啟用定位服務](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)。

在 Windows 上，您可以使用群組原則或使用行動 [裝置管理 (MDM ](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)) 來管理 Windows 位置服務，以及應用程式是否可以存取該位置。

如需 Windows 定位服務的詳細資訊，請參閱 [Windows 定位服務與隱私權](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。



## <a name="notes-and-restrictions"></a>附注和限制

請記住下列事項：

- 說明的家用工作體驗適用于 Windows 和 Mac 版 Teams 電腦版。

- Teams 手機不支援在家工作體驗。

- Teams 行動裝置支援自動定位偵測，但不支援描述的使用者輸入體驗。

- 隱私權設定可能會與自動位置偵測發生衝突 - 可以使用行動裝置裝置管理系統。


## <a name="related-topics"></a>相關主題

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)

- [從家用緊急版 911 工作：啟用定位服務](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

