---
title: 規劃手機Teams和顯示器的部署
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: tony.woodruff
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
search.appverid: MET150
description: 本文提供並概觀在組織中部署手機Teams顯示的任務和步驟。
ms.openlocfilehash: 2ad9840d6ebd1ac6973027dedf6be294704f5326
ms.sourcegitcommit: 73d12d90fc20e3d943301f57ee434379d0b0e91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2021
ms.locfileid: "61577791"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>規劃手機Teams和顯示器的部署

成功部署手機Teams和Teams顯示器會從規劃開始。 本文將介紹在貴組織中部署這些裝置的工作和步驟。 它也提供裝置使用方式、授權、與環境、觸控點和管理整合的指引。

> [!TIP]
> [這個Microsoft 365採用中心](https://adoption.microsoft.com/)是開始使用您的採用旅程Microsoft Teams。

## <a name="task-1-what-are-your-deployment-objectives"></a>任務 1：您的部署目標是什麼？

規劃您組織中Teams手機和顯示器的推出，是從您的部署目標開始。 Teams裝置支援會議室、辦公室及其他功能空間的混合式工作。 您必須判斷這些裝置將在何處使用，以及由誰使用。

### <a name="objective-identify-your-device-personas"></a>目標：識別您的裝置角色

Teams和顯示器會符合兩個角色之一： 

- 個人裝置
- 共用空間裝置

個人裝置和共用裝置的角色和使用方式不同。 

**個人裝置：** 

- 一般指派給一位使用者，使用該使用者的帳戶進行登錄，並啟用Teams授權存取服務。
- 將個人裝置想像成具有一對一關聯性，每一個使用者有一個裝置。
- 可以與桌面用戶端Teams搭配使用功能，例如更好搭配
- 可連接到耳機，有線或無線
- 個人裝置上的其他功能包括桌上型電腦和主畫面。 

**共用空間裝置：**

- 執行特定功能，例如公用區域電話或會議室裝置，並需要專用帳戶和功能授權才能存取服務。
- 將共用裝置想像成具有一對多關聯性：由許多使用者共用的一個裝置。
- 部署在會議室、接待區或製造樓面等共用空間中。 
- 其使用者介面 (UI) 功能所特定，例如共同區域 電話 UI 或會議室 UI 取決於共用裝置的功能和位置。
- 需要設定和選擇性強化，以確保不會變更設定，或防止帳戶退出。 
- 共用空間裝置上的其他功能包括搜尋一般地區的電話，以及閒置超時的辦公桌

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>目標：您需要多少個人及共用空間裝置？

現在，您已經識別您的裝置角色，您需要決定要使用哪些認證裝置，以及您需要的裝置數。 為了協助您做出這個決定，請考慮下列問題： 

- 需要多少個人裝置，以及誰將擁有？
- 需要共用裝置的房間或空間數？ 每個空間都會有相同類型的裝置嗎？ 
- 您的裝置是否需要符合特定需求？
    - 範例包括螢幕大小、表單要素，以及製造商或模型？ 有關認證電話和顯示器的清單，請參閱[Microsoft Teams裝置](teams-ip-phones.md)。
-  您是否需要Teams手機或Teams顯示器？ 有關手機支援的功能Teams，請參閱手機Microsoft Teams，以及螢幕顯示支援[](phones-for-teams.md#features-supported-by-teams-phones)的功能Teams，請參閱Microsoft Teams[顯示](teams-displays.md#features-supported-by-teams-displays)。
- 您有足夠的裝置供新使用者使用，或是新訂單和遞送程式嗎？
- 您是否有可供維護或發生硬體問題的備用裝置？ 能夠快速交換裝置，可防止使用者體驗中斷。

## <a name="task-2-what-are-your-licensing-requirements"></a>工作 2：您的授權需求是什麼？ 

現在，您瞭解您需要的裝置數量，下一步就是決定需要多少授權。 Teams手機和顯示器需要授權，Microsoft Teams Microsoft 365。

共用和個人裝置需要不同的授權。 對於個人裝置，可以使用指派給使用者帳戶的授權。 共用裝置需要特定功能授權。 針對手機和顯示器，適用的授權為適用于手機和電話[的](../set-up-common-area-phones.md#step-1---buy-the-licenses)公用區域Microsoft Teams授權[Microsoft Teams 會議室標準版授權](../rooms/rooms-licensing.md#licensing-solutions-for-shared-communication-devices)。

若要瞭解詳細資訊並比較授權選項，請參閱Microsoft 365[方案](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。 

## <a name="task-3-what-are-your-dependencies"></a>工作 3：您的相依性是什麼？ 

### <a name="objective-plan-your-device-identities"></a>目標：規劃您的裝置身分

身分標識可讓裝置存取Microsoft 365服務，而且應該可讓裝置更容易在貴組織中探索、管理及連接。 若要達成此目的，在規劃裝置身分時，請考慮下列事項：

- 使用者主體名稱及其格式和網域
- 顯示名稱
- 通訊錄的可探索性
- 個人與共享空間裝置類型
- 群組與使用者指派的授權

### <a name="objective-review-conditional-access-policies"></a>目標：審查條件式 Access 政策

Azure Active Directory條件式 Access 政策是必須先符合的其他需求，才能在裝置上登錄。

規劃部署時

- 檢查可能會影響您手機和顯示器Teams條件式 Access 政策。 您可以在系統管理中心Azure AD使用[What If 工具和](/azure/active-directory/conditional-access/what-if-tool)登錄[記錄來執行此工作](/azure/active-directory/reports-monitoring/concept-sign-ins)

- 如有必要，規劃新規則

- 使用條件式 Access 功能 ，例如裝置篩選，將規則Teams手機和顯示器。

>[!NOTE]
>Android 裝置不支援某些條件式 Access 政策。 有關指南和最佳做法，請參閱 Android 裝置，請參閱 Android 裝置Teams[最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="task-4-prepare-your-environment"></a>工作 4：準備您的環境

### <a name="objective-plan-network-basics"></a>目標：規劃網路基本功能

Teams 電話裝置和顯示器需要存取網際網路，Teams如預期運作。 若要準備好您的網路進行部署，請考慮下列事項：

- 您的網路基礎結構是否有足夠的容量？ 請考慮切換埠、無線存取點及其他涵蓋範圍。
- 如果您使用 VLANs 和 DHCP，您的範圍大小是否也一樣？
- 評估及測試部署裝置至Microsoft 365。 
- 根據指引開啟所需的防火牆埠Microsoft 365 URL。
- 檢閱和測試 E911 需求與組組，以確保位置正確性與合規性。 
- 避免使用 Proxy 伺服器，並優化媒體路徑以提升可靠性和品質。

### <a name="objective-physical-considerations"></a>目標：實體考慮

請考慮手機和Teams中將會使用的物理空間。

關鍵方面包括

- **權力：** 您有足夠的電源插座嗎？ 如果裝置需要外部電源，您可以將它放置到電源插座的位置有多近？
- **裝置位置：** 您的裝置實際會在哪裡？ 從原始設備製造商或 OEM (審查桌架、牆面安裝) 。
- **安全：** 您的裝置是否需要鎖定特定空間？
- **協助工具：** 裝置是否符合其主要使用者的協助工具需求？ 請考慮其放置位置、電線長度，以及聽筒或耳機的可用性。

### <a name="task-5-how-will-you-manage-deployed-devices"></a>工作 5：您將如何管理部署的裝置？

Teams手機和顯示器是由兩到三個入口網站Microsoft 365及其各自的 PowerShell 模組管理： 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory系統管理中心

使用 Azure AD系統管理中心管理

- 手機和顯示器Teams身分識別相關工作
- 條件式 Access 政策 
- 密碼重設

#### <a name="teams-admin-center"></a>Teams系統管理中心

使用 Teams系統管理中心管理

- [裝置設定Teams](../business-voice/manage-devices.md)
- [組組設定檔](device-management.md#use-configuration-profiles-in-teams)
- [裝置標記](manage-device-tags.md)
- [遠端登入和登出](remote-sign-in-and-sign-out.md)
- 通話分析  
- 固件
- 疑難排解和下載記錄

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>端點管理員管理中心 (使用 Intune 進行裝置管理) 

使用 端點管理員系統管理中心來管理： 

- 裝置合規性政策
- 註冊限制
- 公司裝置識別碼
- 裝置篩選
