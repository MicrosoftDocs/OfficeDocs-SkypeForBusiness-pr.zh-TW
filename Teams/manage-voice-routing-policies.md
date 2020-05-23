---
title: 在 Microsoft 團隊中管理語音路由策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中建立及管理語音路由原則。
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350187"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a>在 Microsoft 團隊中管理語音路由策略

如果您已在組織中部署[電話系統直接路由](direct-routing-landing-page.md)，您可以使用 [語音路由策略]，讓小組和商務用 Skype Online 使用者透過您的內部部署電話結構接收並撥打電話給公開的交換電話網絡（PSTN）。

[語音路由策略] 是 PSTN 使用記錄的容器。 您可以移至**Voice**  >  Microsoft 團隊系統管理中心的語音**語音路由策略**，或使用 Windows PowerShell，來建立及管理語音路由原則。

您可以使用全域（組織範圍預設值）原則，或建立並指派自訂原則。 除非您建立並指派自訂原則，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。

請務必注意，將語音路由策略指派給使用者並不能讓他們在團隊中進行 PSTN 通話。 您也需要讓使用者使用 [電話系統直接路由]，並完成其他配置步驟。 若要深入瞭解，請參閱[設定直接路由](direct-routing-configure.md)。

## <a name="create-a-custom-voice-routing-policy"></a>建立自訂的語音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音**  >  **語音路由策略**]，然後按一下 [**新增**]。<br>
    ![Microsoft 團隊系統管理中心 [新增語音路由策略] 頁面的螢幕擷取畫面](media/manage-voice-routing-policies.png) 
2. 輸入原則的名稱和描述。
3. 在 [ **PSTN 使用記錄**] 底下，按一下 [**新增 PSTN 使用量**]，然後選取您要新增的記錄。 如果您需要建立新的 PSTN 使用記錄，請按一下 [**新增**]。
4. 如果您已新增多個 PSTN 使用記錄，請依您想要的順序排列它們。
5. 完成後，**請按一下 [** 套用]。
6. 按一下 [儲存]****。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[新-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

## <a name="edit-a-voice-routing-policy"></a>編輯語音路由策略

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或您建立的任何自訂原則。

1. 在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **語音路由策略**]。
2. 按一下原則名稱左邊的，然後按一下 [**編輯**]，選取原則。
3. 按一下 [**新增/移除 PSTN 使用記錄**]，進行您要的變更，然後按一下 [**儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[設定 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy)。

## <a name="assign-a-custom-voice-routing-policy-to-users"></a>指派自訂的語音路由策略給使用者

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

若要將原則指派給一個使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。
2. 按一下 [**原則**]，然後在 [**指派的原則**] 旁，按一下 [**編輯**]。
3. 在 [**語音路由策略**] 底下，選取您要指派的原則，然後按一下 [**儲存**]。

若要一次將原則指派給多位使用者：

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**使用者**]，然後搜尋使用者或篩選視圖，以顯示您想要的使用者。
2. 在 [ **&#x2713;** （核取符號）] 欄中，選取使用者。 若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713; （核取符號）。
3. 按一下 [**編輯設定**]，進行您想要的變更，然後按一下 [套用 **]。**  

或者，您也可以執行下列動作：

1. 在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **語音路由策略**]。
2. 按一下原則名稱的左側來選取原則。
3. 選取 [管理使用者]****。
4. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者後，請按一下 [**儲存**]。

### <a name="using-powershell"></a>使用 PowerShell

請參閱[授與 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [設定直接路由的語音路由](direct-routing-voice-routing.md)
- [啟用直接路由的依位置路由](location-based-routing-enable.md)
- [指派策略給小組中的使用者](assign-policies.md)
