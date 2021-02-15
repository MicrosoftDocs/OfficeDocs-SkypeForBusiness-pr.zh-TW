---
title: 直接路由 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解直接路由，例如組態、必要的核心部署決策，以及語音路由考慮。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9fb8812fd025317eb9c6e3c67ce1f5fcea094978
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196487"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>適用于直接路由之 SBA (的) 分支設備


有時候，使用直接路由來連接到 Microsoft Phone System 的客戶網站可能會遇到網際網路中斷。

假設客戶網站稱為分支，暫時無法透過直接路由連接至 Microsoft 雲端。 不過，分支內部網路仍完整運作，使用者可以連接到提供 PSTN (SBC) 會話邊界控制器。

本文說明如何使用可替代的分支設備 (SBA) ，讓 Microsoft Phone System 在中斷時繼續撥打和接聽公用交換電話網路 (PSTN) 通話。

## <a name="prerequisites"></a>必要條件

SBA 是 Microsoft 提供給 SBC 廠商的可分配程式碼，SBC 廠商接著將程式碼內嵌至其支體，或另行發佈，讓 SBA 在個別的 VM 或硬體上執行。 

若要使用內嵌的可替代分支設備取得最新的會話邊界控制器硬體，請與您的 SBC 廠商聯繫。 此外，需要下列專案：

- SBC 必須針對媒體旁路進行設置，以確保分支網站中的 Microsoft Teams 用戶端可以讓媒體直接與 SBC 一起流動。 

- SBA VM OS 上應啟用 TLS1.2。

## <a name="supported-teams-clients"></a>支援的 Teams 用戶端

下列 Microsoft Teams 用戶端支援 SBA 功能： 

- Microsoft Teams Windows 電腦版 

- Microsoft Teams macOS 電腦版 

## <a name="how-it-works"></a>運作方式

在網際網路中斷期間，Teams 用戶端應該會自動切換到 SBA，而持續通話應該不會中斷。 使用者不需要執行任何動作。 當 Teams 用戶端偵測到網際網路已上線且完成任何撥出通話時，用戶端就會恢復為一般作業模式，並連接到其他 Teams 服務。 SBA 會將收集的通話資料記錄上傳到雲端，通話記錄也會更新，以便租使用者系統管理員能夠查看此資訊。 

當 Microsoft Teams 用戶端處於離線模式時，可以使用下列通話相關功能： 

- 透過當地 SBA/SBC 撥打 PSTN 電話，媒體會透過 SBC 進行。

- 透過當地 SBA/SBC 接收 PSTN 通話，媒體會透過 SBC 進行。 

- PSTN 通話的保留和繼續。

## <a name="configuration"></a>配置

若要讓 SBA 功能能夠使用，Teams 用戶端需要知道每個分支網站中可用的 SBA，以及指派給該網站使用者哪些 SBA。 組組步驟如下：

1. 建立 SBA。
2. 建立 Teams 分支的可支援性政策。
3. 指派策略給使用者。
4. 向 Azure Active Directory 註冊 SBA 應用程式。

所有組式都使用商務用 Skype Online PowerShell Cmdlet 完成。  (Teams 系統管理中心尚未支援直接路由 SBA 功能。)  

 (有關安裝 SBC 的資訊，以及 SBC 廠商檔的連結，請參閱本文結尾的會話 Border Controller 組) 

### <a name="create-the-sbas"></a>建立 SBA

若要建立 SBA，您將使用 New-CsTeamsSurvivableBranchAppliance Cmdlet。 此 Cmdlet 具有下列參數：

| 參數| 說明 |
| :------------|:-------|
| Identity  | SBA 的身分識別  |
| Fqdn | SBA 的 FQDN |
| 網站 | SBA 所在的 TenantNetworkSite |
| 說明 | 文字格式免費 |
|||

例如：

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>建立 Teams 分支的可維護性政策 

若要建立策略，請使用 New-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。 此 Cmdlet 具有下列參數。 請注意，該策略可以包含一或多個 SBA。

| 參數| 說明 |
| :------------|:-------|
| Identity | 該策略的身分識別 |
| BranchApplianceFqdns  | 網站中 (SBA) 的 FQDN |
||

例如：

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

您可以使用 Cmdlet 從Set-CsTeamsSurvivableBranchAppliancePolicy SBA。 例如： 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>指派一個策略給使用者

若要將策略指派給個別使用者，您必須使用 Grant-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。 此 Cmdlet 具有下列參數：

| 參數| 說明 |
| :------------|:-------|
| Identity | 使用者的身分識別 |
| PolicyName | 該策略的身分識別 |
||

例如：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

您可以像下一個範例所示，將$Null移除使用者。

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>向 Azure Active Directory 註冊 SBA 應用程式

若要允許租使用者內使用的不同 SBA 從 Microsoft 365 讀取必要的資料，您必須向 Azure Active Directory 註冊 SBA 應用程式。 

有關應用程式註冊的資訊，請參閱下列內容：

- [為 Azure Active Directory 開發企業線應用程式](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [向 Microsoft 身分識別平臺註冊應用程式](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。  

您只需要註冊一個應用程式，才能供租使用者中所有的 SBA 使用。 

針對 SBA 註冊，您需要註冊所建立下列值： 

- 應用程式 (用戶端) 識別碼 
- 用戶端金鑰 

針對 SBA 應用程式，請記住下列事項： 

- 名稱可以是您決定的任何名稱。  
- 支援的帳戶類型 = 僅此組織目錄中的帳戶。 
- Web 重新導向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。
- 隱含的授予權杖 = Access 權杖和識別碼權杖。 
- API 許可權 = Skype 和 Teams 租使用者系統管理員存取 ->應用程式許可權 -> application_access_custom_sba_appliance。
- 用戶端秘訣：您可以使用任何描述和到期日。 
- 建立用戶端密碼之後，請記得立即複製。 
- 應用程式 (用戶端) 識別碼會顯示在概觀選項卡上。

然後遵循下列步驟：

1. 註冊應用程式。
2. 設定隱含的授予權杖。
3. 設定 API 許可權。
4. 建立用戶端密碼。


## <a name="session-border-controller-configuration"></a>會話邊界控制器組 

若要瞭解如何使用內嵌的可替代分支設備設定會話邊界控制器的逐步指引，請參閱 SBC 廠商提供的檔： 

- [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [絲帶](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [甲骨文](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>報告問題

向 SBC 廠商的支援組織報告任何問題。 報告問題時，請指出您擁有已配置的可替代分支設備。

## <a name="known-issues"></a>已知問題

- 當您新增新的可替代分支裝置時，可能需要一些時間，才能在可替代的分支設備策略中使用它們。

- 當您將可替代的分支設備策略指派給使用者時，可能需要一些時間，SBA 才能顯示在 Get-CsOnlineUser 的輸出中。 

- 系統不會針對 Azure AD 連絡人執行反向數位查找。 

- SBA 不支援呼叫轉場設定。 

- 不支援撥打緊急電話給針對 E911 (緊急) 撥打。

- 此圖表的輸出Get-CsOnlineUser TeamsBranchSurvivabilityPolicy。
