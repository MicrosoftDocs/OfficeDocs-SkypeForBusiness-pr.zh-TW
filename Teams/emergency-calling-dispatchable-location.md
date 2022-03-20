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
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 瞭解 Microsoft 如何支援可分派位置資訊以支援緊急電話。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d80854fc36e6914ba48e8993d298c75b136bd06f
ms.sourcegitcommit: 4af3638637456f21bc97f510ed9d2f7ff2da07e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2022
ms.locfileid: "63660708"
---
# <a name="emergency-addresses-for-remote-locations"></a>遠端位置的緊急位址

本文將說明 Microsoft 支援美國 911 緊急電話位置資訊。 此支援可確保為撥打緊急電話的使用者Teams最精確的可分派位置資訊。 無論來電者的位置 ，無論是現場或在家中工作，來電者的位置資訊必須正確無誤， (PSAP) 位置資訊。

本文包含 Microsoft 遵守 RAY BAUM 多線電話系統與 MLTS (法規) 。 RAY BAUM 的法令延伸了 Kari 的法律需求，于 2021 年初生效。 有關 RAY BAUM 法和 Kari 法律的資訊，請參閱 [911](https://www.fcc.gov/911-dispatchable-location) 通話和多線電話系統的可分派位置 [- Kari 的法規和 RAY BAUM 的 Act 911](https://www.fcc.gov/mlts-911-requirements)直接撥號、通知和可分派位置需求。 

在家工作的使用者現在可以設定自己的緊急位址 ，如果適用的話。 本文將說明如何設定使用者政策，讓使用者能夠設定其緊急位址。

雖然這項資訊適用于美國的緊急 911 通話，但使用者輸入的位置也會傳送至加拿大的篩選中心。

本文包含下列各節：

- [支援緊急通話位置資訊](#support-for-emergency-calling-location-information)
- [位置優先順序](#location-precedence)
- [緊急位址分類和路由](#emergency-address-classification-and-routing)
- [啟用使用者設定其緊急位址](#enable-end-users-to-configure-their-emergency-address)
- [附注和限制](#notes-and-restrictions)


## <a name="support-for-emergency-calling-location-information"></a>支援緊急通話位置資訊

若要支援這些要求，Teams使用各自作業系統提供的位置服務來建議位址 ，如果系統管理員或使用者已授予許可權。 使用者可以確認建議位址的位置、編輯該位址，或手動輸入新位址。 確認、編輯或手動輸入的位址會儲存到 Teams 用戶端上，這樣當用戶端連接到該網路時，就會自動使用使用者確認的位址。 使用者儲存的位址會在用戶端Teams時自動清除。


## <a name="location-precedence"></a>位置優先順序

您可以根據Teams分類緊急位址。 下列清單顯示撥打緊急號碼時所使用的位置優先順序：

1. 由租使用者在位置資訊服務中定義的動態取得位址。

2. 使用者確認、編輯或手動輸入的位址，該位址與用戶端Teams網路相關聯。

3. 作業系統自動建議的位址。

4. 系統管理員靜態指派給使用者的位址。


## <a name="emergency-address-classification-and-routing"></a>緊急位址分類和路由

下表顯示每種類型的緊急網址類別型和相關路由方法：在轉接至服務 PSAP 之前，是否要自動將通話路由至服務 PSAP 或篩選準確性。 美國支援此路由行為，適用于所有通話方案使用者、接線連線合作夥伴，以及直接路由認證的緊急電話服務提供者。


| 緊急網址類別型 | 緊急路由方法 |
| :------------| :-------|
| 由系統管理員定義的動態取得緊急位址。 | 直接至 PSAP。 |
| 從作業系統取得緊急位址，但使用者 **未** 確認其正確性。 | 已篩選並傳送到 PSAP。 |
| 從作業系統取得緊急位址， **使用者確認** 其正確性。| 直接至 PSAP。 |
| 從作業系統取得且由使用者編輯及確認的緊急位址。 | 已篩選並傳送到 PSAP。 |
| 使用者輸入並確認的緊急位址。 | 已篩選並傳送到 PSAP。 |
| 靜態指派給使用者/號碼的緊急位址。 | 已篩選並傳送到 PSAP。 |
| 空 | 已篩選並傳送到 PSAP。 |


## <a name="enable-end-users-to-configure-their-emergency-address"></a>啟用使用者設定其緊急位址

若要為使用者啟用這項功能，請使用 powerShell Cmdlet New-CsTeamsEmergencyCallingPolicy，並設定 ExternalLocationLookupMode 參數為啟用。 請參閱下列範例： 


``` PowerShell
New-CsTeamsEmergencyCallingPolicy -Identity E911WFH -ExternalLocationLookupMode Enabled
```

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -PolicyName E911WFH -Identity user@contoso.com
```

為使用者啟用這項功能後，使用者可以在設定好緊急位址後，從通話標籤新增、編輯或確認緊急位址並顯示位址。 若要進一步瞭解使用者如何設定位置服務，請參閱從家用緊急電話 [911 工作：啟用位置服務](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)。

在 Windows，您可以使用群組原則或使用行動裝置管理 (MDM) 管理 Windows 位置服務，以及應用程式是否具有位置[的存取權](/windows/client-management/mdm/policy-csp-privacy#privacy-letappsaccesslocation)。

有關位置服務Windows，請參閱Windows[服務和隱私權](https://support.microsoft.com/windows/windows-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。



## <a name="notes-and-restrictions"></a>附注和限制

請記住下列事項：

- 描述的在家工作體驗適用于 Teams 和 Mac Windows桌面。

- Teams手機不支援在家工作的體驗。

- Teams行動版支援自動位置偵測，但無法支援所述使用者輸入的體驗。

- 隱私權設定可能會與自動位置偵測發生衝突 - 您可以使用行動裝置管理系統。


## <a name="related-topics"></a>相關主題

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)

- [從家用緊急電話 911 工作：啟用位置服務](https://support.microsoft.com/office/work-from-home-emergency-911-enable-location-services-583dd649-87fc-4b23-aed6-f4e2279297f9?storagetype=live)

