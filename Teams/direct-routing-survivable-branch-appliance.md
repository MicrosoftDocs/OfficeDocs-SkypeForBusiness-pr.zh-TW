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
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解直接路由，例如設定、必要的核心部署決策，以及語音路由考慮。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc250b0506614ef658ade9a491c5561a65b98800
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269668"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a>適用于直接路由的可更新分支設備 (SBA) 


有時候，使用直接路由連線到 Microsoft Phone System 的客戶網站可能會發生網際網路中斷。

假設客戶網站稱為分支，暫時無法透過直接路由連線至 Microsoft 雲端。 不過，分支內的內部網路仍可完全運作，且使用者可以連線至會話框線控制器 (SBC) ，以提供 PSTN 連線能力。

本文說明如何使用可更新的分支設備 (SBA) 讓 Microsoft Phone System 在發生中斷時繼續撥打和接聽公用交換電話網路 (PSTN) 通話。

## <a name="prerequisites"></a>必要條件

SBA 是由 Microsoft 提供給 SBC 廠商的可偵錯工具代碼，供其將程式碼內嵌至韌體或個別發佈，讓 SBA 在另一個 VM 或硬體上執行。 

若要取得內嵌可更新分支設備的最新會話框線控制器韌體，請連絡您的 SBC 廠商。 此外，也需要下列專案：

- 必須針對 Media Bypass 設定 SBC，以確保分支網站中的 Microsoft Teams 用戶端可以讓媒體直接與 SBC 一起運作。 

- TLS1.2 應該會在 SBA VM OS 上啟用。
- 埠 3443、4444 和 8443 是 Microsoft SBA Server 用來與 Teams 用戶端通訊，應允許在防火牆上使用。 
- Microsoft SBA Server 會使用埠 5061 (或 SBC) 上設定的埠來與 SBC 通訊，應允許在防火牆上使用。 
- Microsoft SBA Server 會使用 UDP 埠 123 與 NTP 伺服器通訊，應允許在防火牆上使用 UDP 埠。
- Microsoft SBA Server 會使用埠 443 與 Microsoft 365 通訊，應允許在防火牆上使用。
- 應根據下列所述指導方針定義公用雲端的 Azure IP 範圍和服務標籤： https://www.microsoft.com/download/details.aspx?id=56519

## <a name="supported-teams-clients"></a>支援的 Teams 用戶端

下列 Microsoft Teams 用戶端支援 SBA 功能： 

- Microsoft Teams Windows 電腦版 

- Microsoft Teams macOS 電腦版
- Teams 行動裝置版 
- Teams 手機

## <a name="how-it-works"></a>運作方式

在網際網路中斷期間，Teams 用戶端應該會自動切換到 SBA，進行中的通話應該不會中斷。 使用者不需要採取任何動作。 當 Teams 用戶端偵測到網際網路已啟動且任何撥出電話都完成時，用戶端就會回復到正常運作模式，並聯機到其他 Teams 服務。 SBA 會將收集的通話資料記錄上傳到雲端，通話記錄將會更新，讓租使用者系統管理員能夠檢閱這項資訊。 

當 Microsoft Teams 用戶端處於離線模式時，可以使用下列通話相關功能： 

- 透過本機 SBA/SBC 撥打 PSTN 通話，並讓媒體流經 SBC。

- 透過本機 SBA/SBC 接收 PSTN 通話，並讓媒體流經 SBC。 

- 保留和繼續 PSTN 通話。

## <a name="configuration"></a>設定

若要讓 SBA 功能正常運作，Teams 用戶端必須知道每個分支網站提供哪些 SBA，以及將哪些 SBA 指派給該網站中的使用者。 設定步驟如下所示：

1. 建立 SBA。
2. 建立 Teams 分支可用性原則。
3. 將原則指派給使用者。
4. 使用 Azure Active Directory 註冊 SBA 應用程式。

所有設定都是使用 商務用 Skype Online PowerShell Cmdlet 來完成。  (Teams 系統管理中心尚未支援直接路由 SBA 功能。)  

 (如需設定 SBC 的相關資訊，以及 SBC 廠商檔的連結，請參閱本文結尾的會話框線控制器設定。) 

### <a name="create-the-sbas"></a>建立 SBA

若要建立 SBA，您將使用 New-CsTeamsSurvivableBranchAppliance Cmdlet。 此 Cmdlet 具有下列參數：

| 參數| 描述 |
| :------------|:-------|
| Identity  | SBA 身分識別  |
| Fqdn | SBA 的 FQDN |
| 網站 | SBA 所在的 TenantNetworkSite |
| 描述 | 文字自由格式 |
|||

例如：

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a>建立 Teams 分支可用性原則 

若要建立原則，請使用New-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。 此 Cmdlet 具有下列參數。 請注意，原則可以包含一或多個 SBA。

| 參數| 描述 |
| :------------|:-------|
| Identity | 原則的身分識別 |
| BranchApplianceFqdns  | 網站中 SBA () 的 FQDN |
||

例如：

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

您可以使用Set-CsTeamsSurvivableBranchAppliancePolicy Cmdlet，從原則中新增或移除 SBA。 例如： 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a>指派原則給使用者

若要將原則指派給個別使用者，您將使用Grant-CsTeamsSurvivableBranchAppliancePolicy Cmdlet。 此 Cmdlet 具有下列參數：

| 參數| 描述 |
| :------------|:-------|
| Identity | 使用者的身分識別 |
| 原則名稱 | 原則的身分識別 |
||

例如：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

您可以透過授與$Null原則的方式，從使用者移除原則，如下列範例所示：

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a>使用 Azure Active Directory 註冊 SBA 應用程式

若要允許租使用者內使用的不同 SBA 讀取 Microsoft 365 的必要資料，您必須向 Azure Active Directory 註冊 SBA 的應用程式。 

如需應用程式註冊的詳細資訊，請參閱下列內容：

- [開發適用于 Azure Active Directory 的企業營運應用程式](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- [向Microsoft 身分識別平臺註冊應用程式](/azure/active-directory/develop/quickstart-register-app)。  

您只需要註冊一個應用程式，供租使用者中的所有 SBA 使用。 

對於 SBA 註冊，您需要註冊所建立的下列值： 

- 應用程式 (用戶端) 識別碼 
- 用戶端機密 

對於 SBA 應用程式，請記住下列事項： 

- 名稱可以是您決定的。  
- 支援的帳戶類型 = 僅此組織目錄中的帳戶。 
- Web 重新導向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient .
- 隱含授與權杖 = Access 權杖和 ID 權杖。 
- API 許可權 = Skype 和 Teams 租使用者管理員 Access ->應用程式許可權 -> application_access_custom_sba_appliance。
- 用戶端機密：您可以使用任何描述和到期日。 
- 建立用戶端機密之後，請記得立即複製。 
- 應用程式 (用戶端) 識別碼會顯示在 [概觀] 索引標籤上。

然後遵循下列步驟：

1. 註冊應用程式。
2. 設定隱含的授與權杖。
3. 設定 API 許可權。
4. 建立用戶端機密。


## <a name="session-border-controller-configuration"></a>會話框線控制器設定 

如需有關如何使用內嵌的輔助分支設備來設定會話框線控制器的逐步指導方針，請參閱您的 SBC 廠商所提供的檔： 

- [AudioCodes](https://www.audiocodes.com/library/technical-documents?query=sba)

- [功能區](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [TE-Systems](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a>報告問題

向您的 SBC 廠商支援組織回報任何問題。 回報問題時，表示您已設定了可更新的分支設備。

## <a name="known-issues"></a>已知的問題

- 當您新增新的可更新分支設備時，可能需要一些時間才能在可更新的分支設備原則中使用。

- 當您將可更新的分支設備原則指派給使用者時，可能需要一些時間才會在 Get-CsOnlineUser 輸出中顯示 SBA。 

- 系統不會對 Azure AD 連絡人執行反向號碼查閱。 

- SBA 不支援來電轉接設定。 

- 不支援撥打緊急電話至設定為動態緊急電話 (E911) 的緊急號碼。
