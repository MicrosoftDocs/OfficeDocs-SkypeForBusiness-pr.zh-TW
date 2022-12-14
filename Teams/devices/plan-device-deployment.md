---
title: 規劃您的 Teams 手機裝置和顯示器部署
ms.author: dstrome
author: dstrome
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
description: 本文提供在貴組織中部署 Teams 手機和顯示器的工作與步驟概觀。
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
ms.openlocfilehash: 4ba5c1a9ab59765a5a0af2ac145baf69fc4a8a9a
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392513"
---
# <a name="plan-your-deployment-for-teams-phone-devices-and-displays"></a>規劃您的 Teams 手機裝置和顯示器部署

從規劃開始，成功部署 Teams 手機裝置和 Teams 顯示器。 本文將引導您完成在組織中部署這些裝置的工作與步驟。 它也會提供有關裝置使用方式、授權、與您的環境、觸控點和管理整合的指導方針。

> [!TIP]
> [Microsoft 365 採用中](https://adoption.microsoft.com/)樞是使用 Microsoft Teams 開始採用旅程的絕佳位置。

## <a name="task-1-what-are-your-deployment-objectives"></a>工作 1：您的部署目標為何？

規劃在貴組織中推出 Teams 手機和顯示器，會從您的部署目標開始。 Teams 裝置支援會議室、辦公室及其他功能空間的混合式工作。 您必須判斷這些裝置的使用位置以及消費者。

### <a name="objective-identify-your-device-personas"></a>目標：識別您的裝置角色

Teams 手機和顯示器可符合下列兩個角色的其中之一： 

- 個人裝置
- 共用空間裝置

個人和共用裝置有不同的角色和使用方式。 

**個人裝置：** 

- 一般指派給一個使用者、使用該使用者的帳戶登入，並啟用 Teams 功能授權來存取服務。
- 將個人裝置視為具有一對一關聯性，且每個使用者有一部裝置。
- 可以與 Teams 桌面用戶端配對，並使用更好搭配的功能
- 可能連線到耳機、有線或無線
- 個人裝置上的其他功能包括桌上型電腦和主畫面。 

**共用空間裝置：**

- 執行特定功能，例如常見區域電話或會議室裝置，並且需要專用帳戶和功能授權才能存取服務。
- 將共用裝置視為具有一對多關聯性：一個由許多使用者共用的裝置。
- 部署在會議室、接收區或製造樓層等共用空間。 
- 使用者介面 (UI) 是其功能特有的，例如常見區域電話 UI 或會議室 UI 取決於共用裝置的功能和位置。
- 需要設定和選擇性的硬化，以確保設定不會變更，或是防止帳戶登出。 
- 共用空間裝置上的其他功能包括搜尋常見區域手機和使用空閒逾時的桌上電話

### <a name="objective-how-many-personal-and-shared-space-devices-do-you-need"></a>目標：您需要多少個個人和共用空間裝置？

現在您已經識別出裝置角色，您必須判斷要使用哪些認證裝置，以及您需要多少部裝置。 若要協助您做出此決定，請考慮下列問題： 

- 需要多少個人裝置，以及誰擁有一部裝置？
- 需要共用裝置的會議室或空間數目？ 每個空間是否都有相同類型的裝置？ 
- 您的裝置需要符合特定需求嗎？
    - 範例包括螢幕大小、表單階和製造商或型號？ 如需已認證手機和顯示器的清單，請[參閱Microsoft Teams 認證裝置](teams-ip-phones.md)。
-  您需要 Teams 手機或 Teams 顯示器嗎？ 如需 Teams 手機支援的功能清單，請參[閱 Teams Microsoft電話](phones-for-teams.md#features-supported-by-teams-phones)。 如需 Teams 顯示器支援的功能清單，請[參閱 teams 顯示Microsoft](teams-displays.md#features-supported-by-teams-displays)。
- 您是否擁有足夠的裝置供新使用者使用，或是新訂單和遞送的處理常式？
- 您是否有可供維護的備用裝置，或裝置遇到硬體問題？ 能夠快速交換裝置可避免干擾使用者體驗。

## <a name="task-2-what-are-your-licensing-requirements"></a>工作 2：您的授權需求為何？ 

現在您知道需要多少部裝置，下一步是決定需要多少個授權。 Teams 手機和顯示器需要授權才能存取 Microsoft Teams 和 Microsoft 365。

共用和個人裝置需要不同的授權。 對於個人裝置，可以使用指派給使用者帳戶的授權。 共用裝置需要其功能的特定授權。 對於手機和顯示器，適用的授權為[Microsoft Teams 共用裝置授權](/microsoftteams/teams-add-on-licensing/teams-shared-device-license)和[Microsoft Teams 會議室授權](../rooms/rooms-licensing.md)。

如需詳細資訊並比較您的授權選項，請參[閱Microsoft 365 授權方案](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)。

## <a name="task-3-what-are-your-dependencies"></a>工作 3：您的相依性為何？ 

### <a name="objective-plan-your-device-identities"></a>目標：規劃您的裝置身分識別

身分識別可讓裝置存取 Microsoft 365 服務，而且應該讓裝置更容易在貴組織內探索、管理和連線。 若要達成此目標，請在規劃裝置身分識別時考慮下列事項：

- 使用者主體名稱及其格式和網域
- 顯示名稱
- 通訊錄可搜尋性
- 個人與共享空間裝置類型
- 群組與使用者獲指派的授權

### <a name="objective-review-conditional-access-policies"></a>目標：檢閱條件式存取原則

Azure Active Directory 條件式存取原則是必須滿足的額外需求，裝置才能登入。

在您規劃部署時

- 檢閱可能會影響 Teams 手機和顯示器的現有條件式存取原則。 您可以在 Azure AD 管理員中心使用 What [If 工具](/azure/active-directory/conditional-access/what-if-tool)和登[入記錄](/azure/active-directory/reports-monitoring/concept-sign-ins)檔執行此動作

- 視需要規劃新規則

- 使用裝置篩選等條件式存取功能，將規則套用至 Teams 手機和顯示器。

>[!NOTE]
>Android 裝置不支援一些條件式存取原則。 如需指導方針和最佳做法，請參閱 Android 裝置，請參閱 [Teams Android 裝置的驗證最佳做法](authentication-best-practices-for-android-devices.md)。

## <a name="task-4-prepare-your-environment"></a>工作 4：準備您的環境

### <a name="objective-plan-network-basics"></a>目標：規劃網路基本概念

Teams Phone 裝置和顯示器需要存取網際網路，才能如預期連線到 Teams 並正常運作。 若要讓您的網路準備好進行部署，請考慮下列事項：

- 您的網路基礎結構是否有足夠的容量？ 考慮切換埠、無線存取點及其他涵蓋範圍。
- 如果您使用 VLAN 和 DHCP，您的範圍是否相應地調整大小？
- 評估及測試從裝置部署到 Microsoft 365 的網路路徑。 
- 根據指引，開啟 Microsoft 365 所需的防火牆埠和 URL。
- 檢閱及測試 E911 需求和設定，以瞭解位置準確性和合規性。 
- 避免使用 Proxy 伺服器，並針對可靠性和品質優化媒體路徑。

### <a name="objective-physical-considerations"></a>目標：實體考慮

請考慮您的 Teams 手機和顯示器將使用的實體空間。

主要層麵包括

- **權力：** 您是否有足夠的電源插座？ 如果裝置需要外部電源，您可以將它放置到插座的近一點嗎？
- **裝置位置：** 您的裝置實際位置為何？ 檢閱原始設備製造商 (OEM) 的桌面支架、掛牆架及其他配件。
- **安全：** 您的裝置是否需要在特定空間中鎖定？
- **協助工具：** 裝置是否符合其主要使用者的協助工具需求？ 請考慮放置位置、連接線長度，以及聽筒或耳機的可用性。

### <a name="task-5-how-will-you-manage-deployed-devices"></a>工作 5：您將如何管理已部署的裝置？

Teams 手機和顯示器是由兩個到三個Microsoft 365 入口網站及其各自的 PowerShell 模組管理： 

#### <a name="azure-active-directory-admin-center"></a>Azure Active Directory 管理員中心

使用 Azure AD 管理員中心管理

- Teams 手機和顯示器的所有身分識別相關工作
- 條件式存取原則 
- 密碼重設

#### <a name="teams-admin-center"></a>Teams 管理員中心

使用 Teams 管理員中心管理

- [Teams 的裝置設定](../business-voice/manage-devices.md)
- [組態設定檔](device-management.md#use-configuration-profiles-in-teams)
- [裝置標記](manage-device-tags.md)
- [遠端登入和登出](remote-sign-in-and-sign-out.md)
- 通話分析  
- 固件
- 疑難排解及下載記錄

#### <a name="endpoint-manager-admin-center-if-you-use-intune-for-device-management"></a>端點管理員管理員中心 (如果您使用Intune來管理裝置) 

使用端點管理員管理員中心來管理： 

- 裝置合規性原則
- 註冊限制
- 公司裝置識別碼
- 裝置篩選
